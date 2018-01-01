#!/bin/bash
########################################################################
# AUTHOR    : XENTA OS
# LICENSE   : GNU GPL 3.0
# WEBSITE   : http://www.xentaos.org/
########################################################################

# Mengubah Username dan Hostname Live CD
# Gunakan Perintah Dibawah ini

# 1. Membuat Kerangka Directory
cd $HOME/livecdtmp/extract-cd/casper
sudo su
mkdir temp
cd temp

# 2. Mengekstract file initrd.lz ke Kerangka directory
lzma -dc -S .lz ../initrd.lz | cpio -imvd --no-absolute-filenames

# 3. Mengubah Nama Username dan hostname
# Lokasi konfigurasinya ada di $HOME/livecdtmp/extract-cd/casper/temp/etc/
# cari dan buka file casper.conf sebagai user root dan edit

################################################################################
# This file should go in /etc/casper.conf
# Supported variables are:
# USERNAME, USERFULLNAME, HOST, BUILD_SYSTEM, FLAVOUR

export USERNAME="xenta"
export USERFULLNAME="Live session user"
export HOST="xenta"
export BUILD_SYSTEM="Ubuntu"

# USERNAME and HOSTNAME as specified above won't be honoured and will be set to
# flavour string acquired at boot time, unless you set FLAVOUR to any
# non-empty string.

export FLAVOUR="xenta"
################################################################################

# 4. Membangun initrd.lz lagi dari kerangka directory yang telah dimodifikasi
cd $HOME/livecdtmp/extract-cd/casper/temp
sudo su
find . | cpio --quiet --dereference -o -H newc | lzma -7 > ../initrd.lz
cd $HOME/livecdtmp/extract-cd/casper/
rm -rf temp
