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


