![Supported Python versions](https://img.shields.io/badge/python-3.7+-blue.svg) [![Twitter](https://img.shields.io/twitter/follow/skelsec?label=skelsec&style=social)](https://twitter.com/intent/follow?screen_name=skelsec)

## :triangular_flag_on_post: Sponsors

If you like this project, consider sponsoring it on GitHub! [Sponsors](https://github.com/sponsors/skelsec/)


# AARDWOLFGUI - Asynchronous RDP client in Python (GUI)
Qt5 based GUI for aardwolf RDP/VNC client


# Example scripts
 - `aardpclient` Basic RDP/VNC client running on top of Qt5. Can copy-paste text, handles keyboard and mouse.  

# URL format
As usual the scripts take the target/scredentials in URL format. Below some examples
 - `rdp+kerberos-password://TEST\Administrator:Passw0rd!1@win2016ad.test.corp/?dc=10.10.10.2&proxytype=socks5&proxyhost=127.0.0.1&proxyport=1080`  
 CredSSP (aka `HYBRID`) auth using Kerberos auth + password via `socks5` to `win2016ad.test.corp`, the domain controller (kerberos service) is at `10.10.10.2`. The socks proxy is on `127.0.0.1:1080`
 - `rdp+ntlm-password://TEST\Administrator:Passw0rd!1@10.10.10.103`  
 CredSSP (aka `HYBRID`) auth using NTLM auth + password connecting to RDP server `10.10.10.103`
 - `rdp+ntlm-password://TEST\Administrator:<NThash>@10.10.10.103`  
 CredSSP (aka `HYBRID`) auth using Pass-the-Hash (NTLM) auth connecting to RDP server `10.10.10.103`
 - `rdp+plain://Administrator:Passw0rd!1@10.10.10.103`  
 Plain authentication (No SSL, encryption is RC4) using password connecting to RDP server `10.10.10.103`
 - `vnc+plain://Passw0rd!1@10.10.10.103`  
 VNC client with VNC authentication using password connecting to RDP server `10.10.10.103`
 - `vnc+plain://Passw0rd!1@10.10.10.103`  
 VNC client with VNC authentication using password connecting to RDP server `10.10.10.103`
 - `vnc+plain://:admin:aaa@10.10.10.103`  
 VNC client with VNC authentication using password `admin:aa` connecting to RDP server `10.10.10.103`. Note that if the password contains `:` char you will have to prepend the password with `:`


# Additional info for Qt install.
 - installing in venv will require installing Qt6 outside of venv, then installing 'wheel' and 'vext.pyqt6' in the venv via pip first. then install pyqt5 in the venv
 - installing Qt6 can be a nightmare
 - On ubuntu you can use `apt install python3-pyqt6` before installing `aardwolf` and it will (should) work

# Kudos
 - Citronneur's ([@awakecoding](https://twitter.com/citronneur)) [`rdpy`](https://github.com/citronneur/rdpy). The decompression code and the QT image magic was really valuable.
 - Marc-André Moreau ([@awakecoding](https://twitter.com/awakecoding)) for providing suggestions on fixes


