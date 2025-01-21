D:\pythonProject>python process_depends.py D:\pythonProject\HW_CloudLink.txt D:\pythonProject\result.txt
Traceback (most recent call last):
  File "process_depends.py", line 92, in <module>
    main()
  File "process_depends.py", line 87, in main
    process_depends_txt(args.input_file, args.output_file)
  File "process_depends.py", line 24, in process_depends_txt
    dll_match = re.match(r"^\[\s*.*\]\s+([\w\-.]+)\.DLL)", line, re.IGNORECASE)
  File "D:\Python27\lib\re.py", line 141, in match
    return _compile(pattern, flags).match(string)
  File "D:\Python27\lib\re.py", line 251, in _compile
    raise error, v # invalid expression
sre_constants.error: unbalanced parenthesis
