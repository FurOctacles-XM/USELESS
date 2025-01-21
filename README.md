D:\pythonProject>python process_depends.py D:\pythonProject\HW_CloudLink.txt D:\pythonProject\result.txt
Traceback (most recent call last):
  File "process_depends.py", line 91, in <module>
    main()
  File "process_depends.py", line 86, in main
    process_depends_txt(args.input_file, args.output_file)
  File "process_depends.py", line 13, in process_depends_txt
    with open(input_file, 'r', encoding='utf-8') as infile:
TypeError: 'encoding' is an invalid keyword argument for this function
