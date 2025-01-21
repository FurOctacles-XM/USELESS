*****************************| System Information |*****************************

Dependency Walker:       2.2.6000 (64-bit)
Operating System:        Microsoft Windows NT/2000/XP/2003/Vista based Professional (64-bit)


********************************| Search Order |********************************
*                                                                              *
* Legend: F  File                     E  Error (path not valid)                *
*                                                                              *
********************************************************************************

Side-by-Side components (Windows 2000/XP/2003/Vista/+)
   [F ] c:\windows\system32\WS2_32.DLL
The application directory
   [  ] D:\HW CloudLink\
The 32-bit system directory
   [  ] C:\Windows\system32\
The 16-bit system directory (Windows NT/2000/XP/2003/Vista/+)
   [  ] C:\Windows\system\
The system's root OS directory
   [  ] C:\Windows\
The application's registered "App Paths" directories
The system's "PATH" environment variable directories
   [  ] C:\Windows

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
          Export  Ordinal        Hint           Function                                                              Entry Point
          ------  -------------  -------------  --------------------------------------------------------------------  -----------
          [+  ]      1 (0x0001)     0 (0x0000)  ??0__non_rtti_object@@QEAA@AEBV0@@Z                                   0x0000A850


          [ E6] NTDLL.DLL

               Import  Ordinal        Hint           Function                                               Entry Point
               ------  -------------  -------------  -----------------------------------------------------  -----------
               [C  ]             N/A   773 (0x0305)  RtlCaptureContext                                      Not Bound
               [C  ]             N/A  1289 (0x0509)  RtlLookupFunctionEntry                                 Not Bound
               [C  ]             N/A  1330 (0x0532)  RtlPcToFileHeader                                      Not Bound
               [C  ]             N/A  1587 (0x0633)  RtlUnwind                                              Not Bound
               [C  ]             N/A  1588 (0x0634)  RtlUnwindEx                                            Not Bound
               [C  ]             N/A  1614 (0x064E)  RtlVirtualUnwind                                       Not Bound

               Export  Ordinal        Hint           Function                                               Entry Point
               ------  -------------  -------------  -----------------------------------------------------  -----------
               [OR ]      8 (0x0008)            N/A  N/A                                                    0x0007F660
               [CR ]      9 (0x0009)     0 (0x0000)  A_SHAFinal                                             0x0000E6E0
               [CR ]     10 (0x000A)     1 (0x0001)  A_SHAInit                                              0x0000E810
               [CR ]     11 (0x000B)     2 (0x0002)  A_SHAUpdate                                            0x0000E850
               [FE6] KERNEL32.DLL

                    Import  Ordinal  Hint  Function                       Entry Point
                    ------  -------  ----  -----------------------------  -----------
                    [C  ]       N/A   N/A  GetConsoleCP                   Not Bound
                    [C  ]       N/A   N/A  GetNumberOfConsoleInputEvents  Not Bound
                    [C  ]       N/A   N/A  WriteConsoleW                  Not Bound
                    [C  ]       N/A   N/A  ReadConsoleW                   Not Bound
                    [C  ]       N/A   N/A  SetConsoleMode                 Not Bound
                    [C  ]       N/A   N/A  GetConsoleMode                 Not Bound
                    [C  ]       N/A   N/A  SetConsoleCtrlHandler          Not Bound
                    [C  ]       N/A   N/A  ReadConsoleInputW              Not Bound
                    [C  ]       N/A   N/A  ReadConsoleInputA              Not Bound

          [ ? ] API-MS-WIN-CORE-CONSOLE-L1-2-0.DLL

               Import  Ordinal  Hint        Function           Entry Point
               ------  -------  ----------  -----------------  -----------
               [CE ]       N/A  9 (0x0009)  PeekConsoleInputA  Not Bound

               Export  Ordinal  Hint        Function           Entry Point
               ------  -------  ----------  -----------------  -----------

          [ E6] API-MS-WIN-CORE-DATETIME-L1-1-0.DLL

               Import  Ordinal     Hint        Function        Entry Point
               ------  ----------  ----------  --------------  -----------------------
               [C  ]          N/A  0 (0x0000)  GetDateFormatA  Not Bound
               [C  ]          N/A  2 (0x0002)  GetDateFormatW  Not Bound

               Export  Ordinal     Hint        Function        Entry Point
               ------  ----------  ----------  --------------  -----------------------
               [CRF]   1 (0x0001)  0 (0x0000)  GetDateFormatA  kernel32.GetDateFormatA
               [CRF]   2 (0x0002)  1 (0x0001)  GetDateFormatW  kernel32.GetDateFormatW
