=================================================
pastikan sudah masuk di mode chroot baca 
di Panduan Nome 3
=================================================
## issue
edit issue di /etc/issue  

> cd /etc
> nano issue  
Silahkan Ganti Isinya Contoh :  
Xenta OS 1.3 Arok \n \l

=================================================
 2. issue.net
edit issue di /etc/issue.net
cd /etc
nano issue.net
Silahkan Ganti Isinya Contoh :
Xenta OS 1.3 Arok

=================================================
 3. os-release
edit os-release di /etc/os-release
os release adalah symslink dari /usr/lib/os-release link > /etc/os-release
cd /etc
nano os-release
Silahkan Ganti Isinya Contoh :
NAME="Xenta OS"
VERSION="1.3 (Arok)"
ID=xentaos
ID_LIKE=ubuntu
PRETTY_NAME="Xenta OS 1.3"
VERSION_ID="1.3"
HOME_URL="http://www.xentaos.org/"
SUPPORT_URL="http://www.xentaos.org/"
BUG_REPORT_URL="http://www.xentaos.org/"
VERSION_CODENAME=arok
UBUNTU_CODENAME=xenial

=================================================
 4. HANYA untuk Linux Mint mengganti info
edit info di /etc/linuxmint/info
cd /etc/linuxmint/
nano info
Silahkan Ganti Isinya Contoh :
RELEASE=1.3
CODENAME=arok
EDITION="Cinnamon 32-bit"
DESCRIPTION="Xenta OS 1.3 Arok"
DESKTOP=Gnome
TOOLKIT=GTK
NEW_FEATURES_URL=http://www.xentaos.org/
RELEASE_NOTES_URL=http://www.xentaos.org/
USER_GUIDE_URL=help:xentaos
GRUB_TITLE=Xenta OS 1.3 Cinnamon 32-bit

=================================================
 5. os-release
 Edit Distributions Release
cd /etc/
nano os-release
Silahkan Ganti Isinya Contoh :
DISTRIB_ID=xentaos
DISTRIB_RELEASE=1.3
DISTRIB_CODENAME=arok
DISTRIB_DESCRIPTION="Xenta OS 1.3 LTS Arok"

=================================================
 6. 00-help-text
 Mengganti Ucapan Selamat datang di TTY 
edit info tty di /etc/update-motd.d/10-help-text 
cd /etc/update-motd.d/
nano 10-help-text
Silahkan Ganti Isinya Contoh :
'''
[ -r /etc/lsb-release ] && . /etc/lsb-release

if [ -z "$DISTRIB_RELEASE" ] && [ -x /usr/bin/lsb_release ]; then
 Fall back to using the very slow lsb_release utility
	DISTRIB_RELEASE=$(lsb_release -sr)
fi

URL="http://www.xentaos.org/"

printf "\n * Documentation:  %s\n" "$URL"
'''
