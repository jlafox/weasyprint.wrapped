# Usage

TODO

# Create test package

Windows:
```
.\build-on-windows.ps1
Move-Item -Path .\assets\standalone-windows-64.zip -Destination .\src\Weasyprint.Wrapped\contentFiles\standalone-windows-64.zip
cd .\src\Weasyprint.Wrapped\
dotnet pack -p:PackageVersion=0.0.1 --output nupkgs
```

# Building assets

## Windows (build-on-windows.ps1 does approximately this)

* Download https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer/releases and install to C:\weasyprint.wrapped\standalone-win-64\gtk
* Download https://github.com/indygreg/python-build-standalone/releases (correct release, eg: cpython-3.10.4+20220502-x86_64-pc-windows-msvc-shared-install_only.tar.gz for windows) and extract to c:\weasyprint.wrapped\standalone-win-64\python
* Add gtk3 to path (in current session) 
``` powershell
$Env:PATH += ";C:\weasyprint.wrapped\standalone-win-64\gtk3\bin"
```
* Install weasyprint in the standalone python
```
cd c:\weasyprint.wrapped\standalone-win-64\python
.\python.exe -m pip install weasyprint
.\python.exe -m weasyprint --info
```

## Linux (build-on-linux.ps1 does approximately this)

* Install powershell on ubuntu (https://docs.microsoft.com/en-us/powershell/scripting/install/install-ubuntu?view=powershell-7.2)
* Download https://github.com/indygreg/python-build-standalone/releases (correct release, eg: cpython-3.10.4+20220502-x86_64-unknown-linux-gnu-install_only.tar.gz for Linux) and extract to c:\weasyprint.wrapped\standalone-linux-64\python
* Install weasyprint in the standalone python
```
cd c:\weasyprint.wrapped\standalone-linux-64\python\bin\
python3 -m pip install weasyprint
python3 -m weasyprint --info
```

## Help

* Check PATH in python
```
.\python.exe -c "import os; print(*os.environ['PATH'].split(os.pathsep), sep='\n')"
```

# Externals

* https://github.com/balbarak/WeasyPrint-netcore
* https://github.com/Kozea/WeasyPrint
* https://wiki.python.org/moin/EmbeddedPython
* https://github.com/tschoonj/GTK-for-Windows-Runtime-Environment-Installer/releases