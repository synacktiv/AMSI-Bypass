# AMSI-Bypass

Lists of AMSI triggers (VBA, JScript / VBScript)  

__Reference__ : [MISC 104 - AMSI: Fonctionnement et Contournements](https://boutique.ed-diamond.com/en-kiosque/1399-misc-104.html)  

In VBA, JScript and VBScript, AMSI uses a circular buffer to log instructions and a list of believed suspicious functions. The use of one of those blacklisted functions triggers a scan of the circular buffer by registered AMSI providers.  

This repository contains the lists of triggers as CRC32 checksums, defined in VBE7.DLL, jscript.dll and vbscript.dll. Lists are in CSV format, with the checksums and the retrieved function names.  

__Note__: The logging format (case and encoding) may differ between VBA, JScript and VBScript and with the type of trigger (Win32 API, COM method, native method), affecting CRC32 checksums.  

## VBA:

| Type | Details | File |
| ---- | ------- | ---- |
| Win32 API | `UTF-8` and case preserved | [vba_win32.csv](vba_win32.csv)
| COM methods | `UTF-16LE` and lowercase | [vba_com.csv](vba_com.csv)

## JScript / VBScript

Both use the same blacklist.  
Checksums are computed on either DispID or regular COM function names.  

| Type | Details |
| ---- | ------- |
| DispID | `UTF-16LE` prefixed with `_` |
| Names | `UTF-16LE` and case preserved |

List in [jscript.csv](jscript.csv)  

