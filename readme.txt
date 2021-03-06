LowPower_Teensy3 Library v1.1

If you are not using Teensyduino 1.14 or greater then there is one edit you need to make
to the mk20dx128.c core file: Add -> "PMC_REGSC |= 0x08;" just under "SCB_VTOR = 0;" just
under the ResetHandler function. This allows the mcu to release hold of the I/O when
waking from sleep.

ChangeLog Beta2:
1.  Added struct to store sleep configurations
2.  Added RTC Alarm wake
3.  Added TSI wake
4.  Put usb regulator in standby for VLPR
5.  Got rid of stand alone LPTMR timer fucntions
6.  Cleaned up the library and example codes
7.  New examples added
8.  Defined GPIO wake pin names

ChangeLog Stable v1.0:
1.  Fixed where VLPR was not being retained becase of LPWUI bit not being set right
2.  Added feature to enable LPWUI bit to exit VLPR with any interrupt
3.  Fixed issue with VLPR locking up system if being called before exiting VLPR
4.  Disabled USB Regulator Standby mode during Low Power
5.  Cleaned up library code.

ChangeLog Stable v1.1:
1.  Added all digital wakeup capable pins for DeepSleep and Hibernate function
2.  User can now use callback function for DeepSleep and Hibernate
3.  Added Sleep function, now any interrupt can wake the processor
4.  Improved code performance
5.  New example for Sleep function