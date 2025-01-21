D:\pythonProject>python process_depends.py "D:\pythonProject\HW_CloudLink.txt" "D:\pythonProject\result.txt"
Traceback (most recent call last):
  File "process_depends.py", line 92, in <module>
    main()
  File "process_depends.py", line 87, in main
    process_depends_txt(args.input_file, args.output_file)
  File "process_depends.py", line 58, in process_depends_txt
    import_functions.append(function_name)
UnboundLocalError: local variable 'import_functions' referenced before assignment
