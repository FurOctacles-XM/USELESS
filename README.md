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
                print("dangqian dll %s" % current_dll)
                print("daoru %s" % import_functions)
                print("daochu %s" % export_functions)


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
                if columns[3] not in ["N/A","-----------------------------"]:
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






dangqian dll API-MS-WIN-CORE-SYNCH-L1-2-0
daoru [u'-----------------------', u'N/A', u'N/A']
daochu []
dangqian dll KERNEL32
daoru [u'-----------------------', u'N/A', u'N/A']
daochu []
dangqian dll API-MS-WIN-CORE-SYNCH-L1-2-0


*****************************| System Information |*****************************

Dependency Walker:       2.2.6000 (64-bit)
Operating System:        Microsoft Windows NT/2000/XP/2003/Vista based Professional (64-bit)
OS Version:              6.02.9200
Processor:               Intel64 Family 6 Model 151 Stepping 2, GenuineIntel, ~2112MHz
Number of Processors:    20, Mask: 0x00000000000FFFFF
Computer Name:           DESKTOP-CNC9HGR
User Name:               y30070713
Local Date:              2025年1月21日
Local Time:              9:31:28  (GMT+08:00)
OS Language:             0x0804: Chinese (PRC)
Memory Load:             41%
Physical Memory Total:   34,049,679,360 (32473 MB)
Physical Memory Used:    14,166,077,440
Physical Memory Free:    19,883,601,920
Page File Memory Total:  44,974,395,392
Page File Memory Used:   17,810,927,616
Page File Memory Free:   27,163,467,776
Virtual Memory Total:    140,737,488,224,256
Virtual Memory Used:     4,647,104,512
Virtual Memory Free:     140,732,841,119,744
Page Size:               0x00001000 (4,096)
Allocation Granularity:  0x00010000 (65,536)
Min. App. Address:       0x0000000000010000 (65,536)
Max. App. Address:       0x00007FFFFFFEFFFF (140,737,488,289,791)

********************************| Search Order |********************************
*                                                                              *
* Legend: F  File                     E  Error (path not valid)                *
*                                                                              *
********************************************************************************

Side-by-Side components (Windows 2000/XP/2003/Vista/+)
   [F ] c:\windows\winsxs\amd64_microsoft.windows.common-controls_6595b64144ccf1df_6.0.22621.2070_none_2713e6537381f706\COMCTL32.DLL
   [F ] c:\windows\winsxs\amd64_microsoft.windows.gdiplus_6595b64144ccf1df_1.1.22621.1778_none_57fe2016ce1542ec\GDIPLUS.DLL
The system's "KnownDLLs" list
   [F ] c:\windows\system32\ADVAPI32.DLL


***************************| Module Dependency Tree |***************************
*                                                                              *
* Legend: F  Forwarded Module   ?  Missing Module        6  64-bit Module      *
*         D  Delay Load Module  !  Invalid Module                              *
*         *  Dynamic Module     E  Import/Export Mismatch or Load Failure      *
*                               ^  Duplicate Module                            *
*                                                                              *
*         O  Ordinal Function   E  Import/Export Error   F  Forwarded Function *
*         C  C Function         R  Called At Least Once  *  Dynamic Function   *
*         +  C++ Function                                                      *
*                                                                              *
********************************************************************************

[   ] HW CLOUDLINK.EXE

     Import  Ordinal  Hint  Function  Entry Point
     ------  -------  ----  --------  -----------

     Export  Ordinal  Hint  Function  Entry Point
     ------  -------  ----  --------  -----------

     [ E6] MSVCRT.DLL

          Import  Ordinal        Hint           Function                                                              Entry Point
          ------  -------------  -------------  --------------------------------------------------------------------  -----------
          [C  ]             N/A   489 (0x01E9)  _wcsdup                                                               Not Bound
          [C  ]             N/A   490 (0x01EA)  _wcsicmp                                                              Not Bound
          [C  ]             N/A   494 (0x01EE)  _wcsnicmp                                                             Not Bound

          Export  Ordinal        Hint           Function                                                              Entry Point
          ------  -------------  -------------  --------------------------------------------------------------------  -----------
          [+  ]      1 (0x0001)     0 (0x0000)  ??0__non_rtti_object@@QEAA@AEBV0@@Z                                   0x0000A850
          [+  ]      2 (0x0002)     1 (0x0001)  ??0__non_rtti_object@@QEAA@PEBD@Z                                     0x0000A880
          [ E6] NTDLL.DLL

               Import  Ordinal        Hint           Function                                               Entry Point
               ------  -------------  -------------  -----------------------------------------------------  -----------
               [C  ]             N/A   773 (0x0305)  RtlCaptureContext                                      Not Bound


               Export  Ordinal        Hint           Function                                               Entry Point
               ------  -------------  -------------  -----------------------------------------------------  -----------
               [OR ]      8 (0x0008)            N/A  N/A                                                    0x0007F660


          [ E6] API-MS-WIN-CORE-CONSOLE-L1-1-0.DLL

               Import  Ordinal      Hint         Function                       Entry Point
               ------  -----------  -----------  -----------------------------  --------------------------------------
               [C  ]           N/A   5 (0x0005)  GetConsoleCP                   Not Bound


               Export  Ordinal      Hint         Function                       Entry Point
               ------  -----------  -----------  -----------------------------  --------------------------------------
               [CRF]    1 (0x0001)   0 (0x0000)  AllocConsole                   kernel32.AllocConsole


