# -*- coding: utf-8 -*-

import argparse
import re
import codecs

def process_depends_txt(input_file, output_file):
    dll_info = {}
    current_dll = None
    import_functions = []
    export_functions = []
    is_export_section = False
    is_import_section = False

    # 读取depends的输出文件
    with codecs.open(input_file, 'r', encoding='utf-8') as infile:
        lines = infile.readlines()

    # 解析每一行
    for line in lines:
        line = line.strip()

        if line.startswith('*****') or line.startswith("Side-by-Side") or line.startswith("The System's"):
            continue
        # checkdll
        dll_match = re.match(r"^\[\s*.*\]\s+([\w\-.]+)\.DLL", line, re.IGNORECASE)
        if dll_match:
            if current_dll:
                # 保存前一个dll数据
                dll_info[current_dll] = {
                    'imports': import_functions,
                    'exports': export_functions,
                }

            current_dll = dll_match.group(1)
            import_functions = []
            export_functions = []
            is_export_section = False
            is_import_section = False
            continue

        if "Import" in line and "Function" in line:
            is_import_section = True
            is_export_section = False
            continue

        if "Export" in line and "Function" in line:
            is_import_section = False
            is_export_section = True
            continue

        if re.match(r"^-+$", line):
            continue

        if is_import_section or is_export_section:
            columns = line.split()
            if len(columns) >=4:
                function_name = columns[3]
                if is_import_section:
                    import_functions.append(function_name)
                elif is_export_section:
                    export_functions.append(function_name)

    if current_dll:
        dll_info[current_dll] = {
            'imports': import_functions,
            'exports': export_functions,
        }

    with codecs.open(output_file, 'w', encoding="utf-8") as outfile:
        for dll, functions in dll_info.items():
            exports = functions['exports']
            imports = functions['imports']

            if not exports:
                continue
            for imp_func in imports:
                if imp_func not in exports:
                    outfile.write("{} -> {}\n".format(dll, imp_func))


def main():
    parser = argparse.ArgumentParser(description="Process Dependency Walker output and find missing exported functions.")
    parser.add_argument("input_file", help="Path to the Dependency Walker output text file.")
    parser.add_argument("output_file", help="Path to the output text file.")

    args = parser.parse_args()

    process_depends_txt(args.input_file, args.output_file)
    print("Finish:{}".format(args.output_file))

# 按装订区域中的绿色按钮以运行脚本。
if __name__ == '__main__':
    main()

