# WSA-Build
Automatic build Windows Subsystem for Android (WSA) with GitHub Actions
Run bash -e -x ./build_wsa.sh
+ set -e
+ RELEASE_TYPE_MAP=(['retail']='retail' ['release preview']='RP' ['insider slow']='WIS' ['insider fast']='WIF')
+ declare -A RELEASE_TYPE_MAP
+ [[ false == \t\r\u\e ]]
+ cd MagiskOnWSALocal/scripts
+ bash -x ./build.sh --arch x64 --release-type retail --magisk-ver stable --gapps-brand MindTheGapps --gapps-variant pico '' --root-sol none
+ '[' '!' '5.1.16(1)-release' ']'
++ uname -m
+ HOST_ARCH=x86_64
+ '[' x86_64 '!=' x86_64 ']'
++ dirname ./build.sh
+ cd .
+ '[' '' ']'
++ mktemp -d -t wsa-build-XXXXXXXXXX_
+ WORK_DIR=/tmp/wsa-build-LVQdI430ht_
+ ROOT_MNT_RO=/tmp/wsa-build-LVQdI430ht_/erofs
+ VENDOR_MNT_RO=/tmp/wsa-build-LVQdI430ht_/erofs/vendor
+ PRODUCT_MNT_RO=/tmp/wsa-build-LVQdI430ht_/erofs/product
+ SYSTEM_EXT_MNT_RO=/tmp/wsa-build-LVQdI430ht_/erofs/system_ext
+ ROOT_MNT_RW=/tmp/wsa-build-LVQdI430ht_/upper
+ VENDOR_MNT_RW=/tmp/wsa-build-LVQdI430ht_/upper/vendor
+ PRODUCT_MNT_RW=/tmp/wsa-build-LVQdI430ht_/upper/product
+ SYSTEM_EXT_MNT_RW=/tmp/wsa-build-LVQdI430ht_/upper/system_ext
+ SYSTEM_MNT_RW=/tmp/wsa-build-LVQdI430ht_/upper/system
+ ROOT_MNT=/tmp/wsa-build-LVQdI430ht_/system_root_merged
+ SYSTEM_MNT=/tmp/wsa-build-LVQdI430ht_/system_root_merged/system
+ VENDOR_MNT=/tmp/wsa-build-LVQdI430ht_/system_root_merged/vendor
+ PRODUCT_MNT=/tmp/wsa-build-LVQdI430ht_/system_root_merged/product
+ SYSTEM_EXT_MNT=/tmp/wsa-build-LVQdI430ht_/system_root_merged/system_ext
+ LOWER_PARTITION=(['zsystem']='/tmp/wsa-build-LVQdI430ht_/erofs' ['vendor']='/tmp/wsa-build-LVQdI430ht_/erofs/vendor' ['product']='/tmp/wsa-build-LVQdI430ht_/erofs/product' ['system_ext']='/tmp/wsa-build-LVQdI430ht_/erofs/system_ext')
+ declare -A LOWER_PARTITION
+ UPPER_PARTITION=(['zsystem']='/tmp/wsa-build-LVQdI430ht_/upper/system' ['vendor']='/tmp/wsa-build-LVQdI430ht_/upper/vendor' ['product']='/tmp/wsa-build-LVQdI430ht_/upper/product' ['system_ext']='/tmp/wsa-build-LVQdI430ht_/upper/system_ext')
+ declare -A UPPER_PARTITION
+ MERGED_PARTITION=(['zsystem']='/tmp/wsa-build-LVQdI430ht_/system_root_merged' ['vendor']='/tmp/wsa-build-LVQdI430ht_/system_root_merged/vendor' ['product']='/tmp/wsa-build-LVQdI430ht_/system_root_merged/product' ['system_ext']='/tmp/wsa-build-LVQdI430ht_/system_root_merged/system_ext')
+ declare -A MERGED_PARTITION
+ DOWNLOAD_DIR=../download
+ DOWNLOAD_CONF_NAME=download.list
++ dirname /home/runner/work/WSA-Build/WSA-Build/MagiskOnWSALocal/scripts
+ PYTHON_VENV_DIR=/home/runner/work/WSA-Build/WSA-Build/MagiskOnWSALocal/python3-env
+ EROFS_USE_FUSE=1
+ trap umount_clean EXIT
+ OUTPUT_DIR=../output
+ WSA_WORK_ENV=/tmp/wsa-build-LVQdI430ht_/ENV
+ '[' -f /tmp/wsa-build-LVQdI430ht_/ENV ']'
+ touch /tmp/wsa-build-LVQdI430ht_/ENV
+ export WSA_WORK_ENV
+ trap abort INT TERM
+ '[' -d /usr/sbin ']'
+ export PATH=/usr/sbin:/home/runner/.local/bin:/opt/pipx_bin:/home/runner/.cargo/bin:/home/runner/.config/composer/vendor/bin:/usr/local/.ghcup/bin:/home/runner/.dotnet/tools:/snap/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
+ PATH=/usr/sbin:/home/runner/.local/bin:/opt/pipx_bin:/home/runner/.cargo/bin:/home/runner/.config/composer/vendor/bin:/usr/local/.ghcup/bin:/home/runner/.dotnet/tools:/snap/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
+ '[' -f /etc/mtab ']'
+ ARCH_MAP=("x64" "arm64")
+ RELEASE_TYPE_MAP=("retail" "RP" "WIS" "WIF")
+ MAGISK_VER_MAP=("stable" "beta" "canary" "debug" "release")
+ GAPPS_BRAND_MAP=("OpenGApps" "MindTheGapps" "none")
+ GAPPS_VARIANT_MAP=("super" "stock" "full" "mini" "micro" "nano" "pico" "tvstock" "tvmini")
+ ROOT_SOL_MAP=("magisk" "kernelsu" "none")
+ COMPRESS_FORMAT_MAP=("7z" "zip")
+ GAPPS_PROPS_MSG1='\033[0;31mWARNING: Services such as the Play Store may stop working properly.'
+ GAPPS_PROPS_MSG2='We are not responsible for any problems caused by this!\033[0m'
+ GAPPS_PROPS_MSG3='Info: https://support.google.com/android/answer/10248227'
+ ARGUMENT_LIST=("arch:" "release-type:" "magisk-ver:" "gapps-brand:" "gapps-variant:" "nofix-props" "root-sol:" "compress-format:" "remove-amazon" "compress" "offline" "magisk-custom" "debug" "help" "skip-download-wsa")
+ default
+ ARCH=x64
+ RELEASE_TYPE=retail
+ MAGISK_VER=stable
+ GAPPS_BRAND=MindTheGapps
+ GAPPS_VARIANT=pico
+ ROOT_SOL=magisk
+++ printf %s, arch: release-type: magisk-ver: gapps-brand: gapps-variant: nofix-props root-sol: compress-format: remove-amazon compress offline magisk-custom debug help skip-download-wsa
+++ basename ./build.sh
++ getopt --longoptions arch:,release-type:,magisk-ver:,gapps-brand:,gapps-variant:,nofix-props,root-sol:,compress-format:,remove-amazon,compress,offline,magisk-custom,debug,help,skip-download-wsa, --name build.sh --options '' -- --arch x64 --release-type retail --magisk-ver stable --gapps-brand MindTheGapps --gapps-variant pico '' --root-sol none
+ opts=' --arch '\''x64'\'' --release-type '\''retail'\'' --magisk-ver '\''stable'\'' --gapps-brand '\''MindTheGapps'\'' --gapps-variant '\''pico'\'' --root-sol '\''none'\'' -- '\'''\'''
+ eval set '-- --arch '\''x64'\'' --release-type '\''retail'\'' --magisk-ver '\''stable'\'' --gapps-brand '\''MindTheGapps'\'' --gapps-variant '\''pico'\'' --root-sol '\''none'\'' -- '\'''\'''
++ set -- --arch x64 --release-type retail --magisk-ver stable --gapps-brand MindTheGapps --gapps-variant pico --root-sol none -- ''
+ [[ 14 -gt 0 ]]
+ case "$1" in
+ ARCH=x64
+ shift 2
+ [[ 12 -gt 0 ]]
+ case "$1" in
+ RELEASE_TYPE=retail
+ shift 2
+ [[ 10 -gt 0 ]]
+ case "$1" in
+ MAGISK_VER=stable
+ shift 2
+ [[ 8 -gt 0 ]]
+ case "$1" in
+ GAPPS_BRAND=MindTheGapps
+ shift 2
+ [[ 6 -gt 0 ]]
+ case "$1" in
+ GAPPS_VARIANT=pico
+ shift 2
+ [[ 4 -gt 0 ]]
+ case "$1" in
+ ROOT_SOL=none
+ shift 2
+ [[ 2 -gt 0 ]]
+ case "$1" in
+ shift
+ break
+ '[' '' ']'
+ check_list x64 Architecture x64 arm64
+ local input=x64
+ '[' -n x64 ']'
+ local name=Architecture
+ shift
+ arr=('Architecture' 'x64' 'arm64')
+ local arr
+ local list_count=3
+ for i in "${arr[@]}"
+ '[' x64 == Architecture ']'
+ (( list_count-- ))
+ (( 2 <= 0 ))
+ for i in "${arr[@]}"
+ '[' x64 == x64 ']'
+ echo 'INFO: Architecture: x64'
INFO: Architecture: x64
+ break
+ check_list retail 'Release Type' retail RP WIS WIF
+ local input=retail
+ '[' -n retail ']'
+ local 'name=Release Type'
+ shift
+ arr=('Release Type' 'retail' 'RP' 'WIS' 'WIF')
+ local arr
+ local list_count=5
+ for i in "${arr[@]}"
+ '[' retail == 'Release Type' ']'
+ (( list_count-- ))
+ (( 4 <= 0 ))
+ for i in "${arr[@]}"
+ '[' retail == retail ']'
+ echo 'INFO: Release Type: retail'
INFO: Release Type: retail
+ break
+ check_list stable 'Magisk Version' stable beta canary debug release
+ local input=stable
+ '[' -n stable ']'
+ local 'name=Magisk Version'
+ shift
+ arr=('Magisk Version' 'stable' 'beta' 'canary' 'debug' 'release')
+ local arr
+ local list_count=6
+ for i in "${arr[@]}"
+ '[' stable == 'Magisk Version' ']'
+ (( list_count-- ))
+ (( 5 <= 0 ))
+ for i in "${arr[@]}"
+ '[' stable == stable ']'
+ echo 'INFO: Magisk Version: stable'
INFO: Magisk Version: stable
+ break
+ check_list MindTheGapps 'GApps Brand' OpenGApps MindTheGapps none
+ local input=MindTheGapps
+ '[' -n MindTheGapps ']'
+ local 'name=GApps Brand'
+ shift
+ arr=('GApps Brand' 'OpenGApps' 'MindTheGapps' 'none')
+ local arr
+ local list_count=4
+ for i in "${arr[@]}"
+ '[' MindTheGapps == 'GApps Brand' ']'
+ (( list_count-- ))
+ (( 3 <= 0 ))
+ for i in "${arr[@]}"
+ '[' MindTheGapps == OpenGApps ']'
+ (( list_count-- ))
+ (( 2 <= 0 ))
+ for i in "${arr[@]}"
+ '[' MindTheGapps == MindTheGapps ']'
+ echo 'INFO: GApps Brand: MindTheGapps'
INFO: GApps Brand: MindTheGapps
+ break
+ check_list pico 'GApps Variant' super stock full mini micro nano pico tvstock tvmini
+ local input=pico
+ '[' -n pico ']'
+ local 'name=GApps Variant'
+ shift
+ arr=('GApps Variant' 'super' 'stock' 'full' 'mini' 'micro' 'nano' 'pico' 'tvstock' 'tvmini')
+ local arr
+ local list_count=10
+ for i in "${arr[@]}"
+ '[' pico == 'GApps Variant' ']'
+ (( list_count-- ))
+ (( 9 <= 0 ))
+ for i in "${arr[@]}"
+ '[' pico == super ']'
+ (( list_count-- ))
+ (( 8 <= 0 ))
+ for i in "${arr[@]}"
+ '[' pico == stock ']'
+ (( list_count-- ))
+ (( 7 <= 0 ))
+ for i in "${arr[@]}"
+ '[' pico == full ']'
+ (( list_count-- ))
+ (( 6 <= 0 ))
+ for i in "${arr[@]}"
+ '[' pico == mini ']'
+ (( list_count-- ))
+ (( 5 <= 0 ))
+ for i in "${arr[@]}"
+ '[' pico == micro ']'
+ (( list_count-- ))
+ (( 4 <= 0 ))
+ for i in "${arr[@]}"
+ '[' pico == nano ']'
+ (( list_count-- ))
+ (( 3 <= 0 ))
+ for i in "${arr[@]}"
+ '[' pico == pico ']'
+ echo 'INFO: GApps Variant: pico'
INFO: GApps Variant: pico
+ break
+ check_list none 'Root Solution' magisk kernelsu none
+ local input=none
+ '[' -n none ']'
+ local 'name=Root Solution'
+ shift
+ arr=('Root Solution' 'magisk' 'kernelsu' 'none')
+ local arr
+ local list_count=4
+ for i in "${arr[@]}"
+ '[' none == 'Root Solution' ']'
+ (( list_count-- ))
+ (( 3 <= 0 ))
+ for i in "${arr[@]}"
+ '[' none == magisk ']'
+ (( list_count-- ))
+ (( 2 <= 0 ))
+ for i in "${arr[@]}"
+ '[' none == kernelsu ']'
+ (( list_count-- ))
+ (( 1 <= 0 ))
+ for i in "${arr[@]}"
+ '[' none == none ']'
+ echo 'INFO: Root Solution: none'
INFO: Root Solution: none
+ break
+ check_list '' 'Compress Format' 7z zip
+ local input=
+ '[' -n '' ']'
+ '[' '' ']'
+ '[' -f /home/runner/work/WSA-Build/WSA-Build/MagiskOnWSALocal/python3-env/bin/activate ']'
+ RELEASE_NAME_MAP=(['retail']='Retail' ['RP']='Release Preview' ['WIS']='Insider Slow' ['WIF']='Insider Fast')
+ declare -A RELEASE_NAME_MAP
+ ANDROID_API_MAP=(['30']='11.0' ['32']='12.1' ['33']='13.0')
+ declare -A ANDROID_API_MAP
+ RELEASE_NAME=Retail
+ echo -e 'Build: RELEASE_TYPE=Retail'
Build: RELEASE_TYPE=Retail
+ WSA_ZIP_PATH=../download/wsa-retail.zip
+ vclibs_PATH=../download/Microsoft.VCLibs.140.00_x64.appx
+ UWPVCLibs_PATH=../download/Microsoft.VCLibs.140.00.UWPDesktop_x64.appx
+ xaml_PATH=../download/Microsoft.UI.Xaml.2.8_x64.appx
+ MAGISK_ZIP=magisk-stable.zip
+ MAGISK_PATH=../download/magisk-stable.zip
+ '[' '' ']'
+ ANDROID_API=33
+ WSA_MAJOR_VER=0
+ '[' -z ']'
+ require_su
++ id -u
+ test 1001 '!=' 0
++ sudo id -u
+ '[' 0 '!=' 0 ']'
+ '[' '' '!=' no ']'
+ echo 'Generate Download Links'
Generate Download Links
+ python3 generateWSALinks.py x64 retail ../download download.list
Generating WSA download link: arch=x64 release_type=Retail

WSA Build Version=2306.40000.4.0

download link: http://tlu.dl.delivery.mp.microsoft.com/filestreamingservice/files/28edaebf-8019-4844-ba32-8ab019bc9391?P1=1691913290&P2=404&P3=2&P4=bXAMgUqdbEGgCJq7zD6UqdnhOgpZnJQwFvWlD6bjIR6SDCBT5LxTdjYtLJrjC5wjxC9x3DRMdYE00VbEfXo2Aw%3d%3d
path: ../download/Microsoft.VCLibs.140.00_x64.appx

download link: http://tlu.dl.delivery.mp.microsoft.com/filestreamingservice/files/21a6f30d-0ec0-46da-92cf-04e35cf18efc?P1=1691913395&P2=404&P3=2&P4=nPSRXW4oh3cFhLGbRghLTIOk7O%2fpo4yTNBrCOJAiqoqNTXUsZ4W9Esn8aApkrmWetISTK3MKtn%2fqwALDV4Snkw%3d%3d
path: ../download/Microsoft.UI.Xaml.2.8_x64.appx

download link: http://tlu.dl.delivery.mp.microsoft.com/filestreamingservice/files/986a8270-404c-4470-871d-5c4090dcaa79?P1=1691913410&P2=404&P3=2&P4=cZJUcWWUCRln6edka2GmNqeD5H%2fODPVhGh1B%2f8kNYbvDhoyMuDlszZEcaMZ%2fNspSKrIC8hrytEBGgI7kn0NRog%3d%3d
path: ../download/Microsoft.VCLibs.140.00.UWPDesktop_x64.appx

download link: http://tlu.dl.delivery.mp.microsoft.com/filestreamingservice/files/00cb3c53-e0d9-41d2-ac9f-8f92343e13b6?P1=1691941181&P2=404&P3=2&P4=ZAEWjI6Z87MXykOKedypPrfZmFH%2fyAU35HuD1NX4ErzOddcZxzD6y2LpzbDvdfiKlB1%2bJGW5RtrCQdPXAHEJ5Q%3d%3d
path: ../download/wsa-retail.zip

+ source /tmp/wsa-build-LVQdI430ht_/ENV
++ WSA_VER=2306.40000.4.0
++ WSA_MAJOR_VER=2306
+ [[ 2306 -lt 2211 ]]
+ '[' none = magisk ']'
+ '[' MindTheGapps '!=' none ']'
+ '[' -z ']'
+ python3 generateMagiskLink.py stable ../download download.list
Generating Magisk download link: release type=stable
download link: https://cdn.jsdelivr.net/gh/topjohnwu/magisk-files@26.1/app-release.apk
+ '[' none = kernelsu ']'
+ '[' MindTheGapps '!=' none ']'
+ update_gapps_zip_name
+ '[' MindTheGapps = OpenGApps ']'
+ GAPPS_ZIP_NAME=MindTheGapps-x64-13.0.zip
+ GAPPS_PATH=../download/MindTheGapps-x64-13.0.zip
+ python3 generateGappsLink.py x64 MindTheGapps pico ../download download.list 33 MindTheGapps-x64-13.0.zip
Generating MindTheGapps download link: arch=x64 variant=pico
download link: https://downloads.sourceforge.net/project/wsa-mtg/x86_64/20230812/MindTheGapps-13.0.0-x86_64-20230812.zip
+ echo 'Download Artifacts'
Download Artifacts
+ aria2c --no-conf --log-level=info --log=../download/aria2_download.log -x16 -s16 -j5 -c -R -m0 --async-dns=false --check-integrity=true --continue=true --allow-overwrite=true --conditional-get=true -d../download -i../download/download.list

08/13 07:45:02 [NOTICE] Downloading 6 item(s)

08/13 07:45:02 [NOTICE] Download complete: ../download/Microsoft.VCLibs.140.00_x64.appx

08/13 07:45:02 [NOTICE] Download complete: ../download/magisk-stable.zip

08/13 07:45:02 [NOTICE] CUID#12 - Redirecting to https://newcontinuum.dl.sourceforge.net/project/wsa-mtg/x86_64/20230812/MindTheGapps-13.0.0-x86_64-20230812.zip

08/13 07:45:02 [NOTICE] Download complete: ../download/Microsoft.UI.Xaml.2.8_x64.appx

08/13 07:45:02 [NOTICE] Download complete: ../download/Microsoft.VCLibs.140.00.UWPDesktop_x64.appx
[DL:376MiB][#4a5d8e 317MiB/1.3GiB(22%)][#de4064 1.0MiB/188MiB(0%)]
[DL:421MiB][#4a5d8e 731MiB/1.3GiB(52%)][#de4064 45MiB/188MiB(24%)]

08/13 07:45:04 [NOTICE] CUID#52 - Redirecting to https://netactuate.dl.sourceforge.net/project/wsa-mtg/x86_64/20230812/MindTheGapps-13.0.0-x86_64-20230812.zip
[DL:417MiB][#4a5d8e 1.0GiB/1.3GiB(77%)][#de4064 103MiB/188MiB(55%)]
[DL:350MiB][#4a5d8e 1.1GiB/1.3GiB(87%)][#de4064 119MiB/188MiB(63%)]
[DL:290MiB][#4a5d8e 1.2GiB/1.3GiB(92%)][#de4064 119MiB/188MiB(63%)]
[DL:246MiB][#4a5d8e 1.2GiB/1.3GiB(94%)][#de4064 119MiB/188MiB(63%)]

08/13 07:45:08 [NOTICE] CUID#58 - Redirecting to https://netactuate.dl.sourceforge.net/project/wsa-mtg/x86_64/20230812/MindTheGapps-13.0.0-x86_64-20230812.zip
[DL:215MiB][#4a5d8e 1.3GiB/1.3GiB(96%)][#de4064 130MiB/188MiB(69%)]
[DL:191MiB][#4a5d8e 1.3GiB/1.3GiB(97%)][#de4064 141MiB/188MiB(75%)]
[DL:165MiB][#4a5d8e 1.3GiB/1.3GiB(98%)][#de4064 141MiB/188MiB(75%)]
[DL:121MiB][#4a5d8e 1.3GiB/1.3GiB(98%)][#de4064 141MiB/188MiB(75%)]

08/13 07:45:13 [NOTICE] Download complete: ../download/wsa-retail.zip
[#de4064 141MiB/188MiB(75%) CN:2 DL:6.2MiB ETA:7s]

08/13 07:45:14 [NOTICE] CUID#57 - Redirecting to https://newcontinuum.dl.sourceforge.net/project/wsa-mtg/x86_64/20230812/MindTheGapps-13.0.0-x86_64-20230812.zip
[#de4064 143MiB/188MiB(76%) CN:2 DL:3.8MiB ETA:11s]
[#de4064 146MiB/188MiB(77%) CN:2 DL:3.7MiB ETA:11s]

08/13 07:45:16 [NOTICE] CUID#54 - Redirecting to https://phoenixnap.dl.sourceforge.net/project/wsa-mtg/x86_64/20230812/MindTheGapps-13.0.0-x86_64-20230812.zip
[#de4064 168MiB/188MiB(89%) CN:1 DL:5.8MiB ETA:3s]
[#de4064 170MiB/188MiB(90%) CN:1 DL:5.4MiB ETA:3s]
[#de4064 172MiB/188MiB(91%) CN:1 DL:6.6MiB ETA:2s]
[#de4064 174MiB/188MiB(92%) CN:1 DL:5.7MiB ETA:2s]
[#de4064 176MiB/188MiB(93%) CN:1 DL:5.2MiB ETA:2s]
[#de4064 178MiB/188MiB(94%) CN:1 DL:4.8MiB ETA:2s]
[#de4064 179MiB/188MiB(95%) CN:1 DL:4.4MiB ETA:2s]
[#de4064 181MiB/188MiB(96%) CN:1 DL:4.1MiB ETA:1s]

08/13 07:45:25 [NOTICE] Download complete: ../download/MindTheGapps-x64-13.0.zip

Download Results:
gid   |stat|avg speed  |path/URI
======+====+===========+=======================================================
186e51|OK  |    40MiB/s|../download/Microsoft.VCLibs.140.00_x64.appx
876308|OK  |    69MiB/s|../download/magisk-stable.zip
d9f995|OK  |    13MiB/s|../download/Microsoft.UI.Xaml.2.8_x64.appx
b7d5fb|OK  |    16MiB/s|../download/Microsoft.VCLibs.140.00.UWPDesktop_x64.appx
4a5d8e|OK  |   128MiB/s|../download/wsa-retail.zip
de4064|OK  |   8.4MiB/s|../download/MindTheGapps-x64-13.0.zip

Status Legend:
(OK):download completed.
+ echo 'Extract WSA'
Extract WSA
+ '[' -f ../download/wsa-retail.zip ']'
+ python3 extractWSA.py x64 ../download/wsa-retail.zip /tmp/wsa-build-LVQdI430ht_ /tmp/wsa-build-LVQdI430ht_/ENV
unzipping WsaPackage_2306.40000.4.0_x64_Release-Nightly.msix to /tmp/wsa-build-LVQdI430ht_/wsa
unzipping from /tmp/wsa-build-LVQdI430ht_/wsa/WsaPackage_2306.40000.4.0_x64_Release-Nightly.msix
+ echo -e 'Extract done\n'
Extract done

+ source /tmp/wsa-build-LVQdI430ht_/ENV
++ WSA_VER=2306.40000.4.0
++ WSA_MAJOR_VER=2306
++ WSA_REL=Release-Nightly
+ '[' MindTheGapps '!=' none ']'
+ echo 'Extract Magisk'
Extract Magisk
+ '[' -f ../download/magisk-stable.zip ']'
+ MAGISK_VERSION_NAME=
+ MAGISK_VERSION_CODE=0
+ python3 extractMagisk.py x64 ../download/magisk-stable.zip /tmp/wsa-build-LVQdI430ht_
Magisk version: 26.1 (26100)
+ source /tmp/wsa-build-LVQdI430ht_/ENV
++ WSA_VER=2306.40000.4.0
++ WSA_MAJOR_VER=2306
++ WSA_REL=Release-Nightly
++ MAGISK_VERSION_NAME=26.1
++ MAGISK_VERSION_CODE=26100
+ '[' 26100 -lt 26000 ']'
+ sudo chmod +x ../linker/x86_64/linker64
+ sudo patchelf --set-interpreter ../linker/x86_64/linker64 /tmp/wsa-build-LVQdI430ht_/magisk/magiskpolicy
+ chmod +x /tmp/wsa-build-LVQdI430ht_/magisk/magiskpolicy
+ echo -e 'done\n'
done

+ '[' none = kernelsu ']'
+ '[' MindTheGapps '!=' none ']'
+ update_gapps_zip_name
+ '[' MindTheGapps = OpenGApps ']'
+ GAPPS_ZIP_NAME=MindTheGapps-x64-13.0.zip
+ GAPPS_PATH=../download/MindTheGapps-x64-13.0.zip
+ echo 'Extract MindTheGapps'
Extract MindTheGapps
+ mkdir -p /tmp/wsa-build-LVQdI430ht_/gapps
+ '[' -f ../download/MindTheGapps-x64-13.0.zip ']'
+ '[' MindTheGapps = OpenGApps ']'
+ unzip ../download/MindTheGapps-x64-13.0.zip 'system/*' -x 'system/addon.d/*' 'system/system_ext/priv-app/SetupWizard/*' -d /tmp/wsa-build-LVQdI430ht_/gapps
Archive:  ../download/MindTheGapps-x64-13.0.zip
signed by SignApk
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/app/GoogleCalendarSyncAdapter/GoogleCalendarSyncAdapter.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/app/GoogleContactsSyncAdapter/GoogleContactsSyncAdapter.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/app/PrebuiltExchange3Google/PrebuiltExchange3Google.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/default-permissions/default-permissions-google.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/default-permissions/default-permissions-mtg.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/permissions/com.google.android.dialer.support.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/permissions/privapp-permissions-google-product.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/security/fsverity/gms_fsverity_cert.der  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/sysconfig/d2d_cable_migration_feature.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/sysconfig/google-hiddenapi-package-allowlist.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/sysconfig/google.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/etc/sysconfig/google_build.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/framework/com.google.android.dialer.support.jar  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/lib/libjni_latinimegoogle.so  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/lib64/libjni_latinimegoogle.so  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/overlay/GmsOverlay.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/overlay/GmsSettingsProviderOverlay.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/priv-app/AndroidAutoStub/AndroidAutoStub.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/priv-app/GmsCore/GmsCore.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/priv-app/GooglePartnerSetup/GooglePartnerSetup.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/priv-app/GoogleRestore/GoogleRestore.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/priv-app/Phonesky/Phonesky.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/product/priv-app/Velvet/Velvet.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/system_ext/etc/permissions/privapp-permissions-google-system-ext.xml  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/system_ext/priv-app/GoogleFeedback/GoogleFeedback.apk  
  inflating: /tmp/wsa-build-LVQdI430ht_/gapps/system/system_ext/priv-app/GoogleServicesFramework/GoogleServicesFramework.apk  
+ mv /tmp/wsa-build-LVQdI430ht_/gapps/system/product /tmp/wsa-build-LVQdI430ht_/gapps/system/system_ext /tmp/wsa-build-LVQdI430ht_/gapps
+ rm -rf /tmp/wsa-build-LVQdI430ht_/gapps/system
+ cp -r ../x64/gapps/product /tmp/wsa-build-LVQdI430ht_/gapps
+ echo -e 'Extract done\n'
Extract done

+ [[ 2306 -ge 2302 ]]
+ echo 'Convert vhdx to RAW image'
Convert vhdx to RAW image
+ vhdx_to_raw_img /tmp/wsa-build-LVQdI430ht_/wsa/x64/system_ext.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/system_ext.img
+ qemu-img convert -q -f vhdx -O raw /tmp/wsa-build-LVQdI430ht_/wsa/x64/system_ext.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/system_ext.img
+ rm -f /tmp/wsa-build-LVQdI430ht_/wsa/x64/system_ext.vhdx
+ vhdx_to_raw_img /tmp/wsa-build-LVQdI430ht_/wsa/x64/product.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/product.img
+ qemu-img convert -q -f vhdx -O raw /tmp/wsa-build-LVQdI430ht_/wsa/x64/product.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/product.img
+ rm -f /tmp/wsa-build-LVQdI430ht_/wsa/x64/product.vhdx
+ vhdx_to_raw_img /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.img
+ qemu-img convert -q -f vhdx -O raw /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.img
+ rm -f /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.vhdx
+ vhdx_to_raw_img /tmp/wsa-build-LVQdI430ht_/wsa/x64/vendor.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/vendor.img
+ qemu-img convert -q -f vhdx -O raw /tmp/wsa-build-LVQdI430ht_/wsa/x64/vendor.vhdx /tmp/wsa-build-LVQdI430ht_/wsa/x64/vendor.img
+ rm -f /tmp/wsa-build-LVQdI430ht_/wsa/x64/vendor.vhdx
+ echo -e 'Convert vhdx to RAW image done\n'
Convert vhdx to RAW image done

+ [[ 2306 -ge 2304 ]]
+ echo 'Mount images'
Mount images
+ sudo mkdir -p -m 755 /tmp/wsa-build-LVQdI430ht_/erofs
+ sudo chown 0:0 /tmp/wsa-build-LVQdI430ht_/erofs
+ sudo setfattr -n security.selinux -v u:object_r:rootfs:s0 /tmp/wsa-build-LVQdI430ht_/erofs
+ mount_erofs /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.img /tmp/wsa-build-LVQdI430ht_/erofs
+ '[' 1 ']'
+ sudo ../bin/x86_64/fuse.erofs /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.img /tmp/wsa-build-LVQdI430ht_/erofs
disk: /tmp/wsa-build-LVQdI430ht_/wsa/x64/system.img
offset: 0
mountpoint: /tmp/wsa-build-LVQdI430ht_/erofs
dbglevel: 0
<E> erofs: cannot find valid erofs superblock
failed to read erofs super block
fuse.erofs 1.6-g689372cd
+ return 1
+ abort
+ '[' '' ']'
+ echo 'Build: an error has occurred, exit'
Build: an error has occurred, exit
+ '[' -d /tmp/wsa-build-LVQdI430ht_ ']'
+ echo -e '\nCleanup Work Directory'

Cleanup Work Directory
+ umount_clean
+ '[' -d /tmp/wsa-build-LVQdI430ht_/system_root_merged ']'
+ '[' -d /tmp/wsa-build-LVQdI430ht_/erofs ']'
+ echo 'Cleanup Mount Directory'
Cleanup Mount Directory
+ for PART in "${LOWER_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/erofs/vendor
umount: /tmp/wsa-build-LVQdI430ht_/erofs/vendor: no mount point specified.
+ for PART in "${LOWER_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/erofs/system_ext
umount: /tmp/wsa-build-LVQdI430ht_/erofs/system_ext: no mount point specified.
+ for PART in "${LOWER_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/erofs/product
umount: /tmp/wsa-build-LVQdI430ht_/erofs/product: no mount point specified.
+ for PART in "${LOWER_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/erofs
umount: /tmp/wsa-build-LVQdI430ht_/erofs: not mounted.
+ for PART in "${UPPER_PARTITION[@]}"
+ sudo rm -rf /tmp/wsa-build-LVQdI430ht_/upper/vendor
+ for PART in "${UPPER_PARTITION[@]}"
+ sudo rm -rf /tmp/wsa-build-LVQdI430ht_/upper/system_ext
+ for PART in "${UPPER_PARTITION[@]}"
+ sudo rm -rf /tmp/wsa-build-LVQdI430ht_/upper/product
+ for PART in "${UPPER_PARTITION[@]}"
+ sudo rm -rf /tmp/wsa-build-LVQdI430ht_/upper/system
+ for PART in "${MERGED_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/system_root_merged/vendor
umount: /tmp/wsa-build-LVQdI430ht_/system_root_merged/vendor: no mount point specified.
+ for PART in "${MERGED_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/system_root_merged/system_ext
umount: /tmp/wsa-build-LVQdI430ht_/system_root_merged/system_ext: no mount point specified.
+ for PART in "${MERGED_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/system_root_merged/product
umount: /tmp/wsa-build-LVQdI430ht_/system_root_merged/product: no mount point specified.
+ for PART in "${MERGED_PARTITION[@]}"
+ sudo umount -v /tmp/wsa-build-LVQdI430ht_/system_root_merged
umount: /tmp/wsa-build-LVQdI430ht_/system_root_merged: no mount point specified.
+ sudo rm -rf /tmp/wsa-build-LVQdI430ht_
+ '[' '' ']'
+ rm -f ../download/download.list
++ python3 -c 'import sys ; print( 1 if sys.prefix != sys.base_prefix else 0 )'
+ '[' 0 = 1 ']'
+ clean_download
+ '[' -d ../download ']'
+ echo 'Cleanup Download Directory'
Cleanup Download Directory
+ '[' '' ']'
+ '[' '' ']'
+ '[' '' ']'
+ '[' '' ']'
+ exit 1
+ umount_clean
+ '[' -d /tmp/wsa-build-LVQdI430ht_/system_root_merged ']'
+ '[' -d /tmp/wsa-build-LVQdI430ht_/erofs ']'
+ rm -rf /tmp/wsa-build-LVQdI430ht_
+ '[' '' ']'
+ rm -f ../download/download.list
++ python3 -c 'import sys ; print( 1 if sys.prefix != sys.base_prefix else 0 )'
+ '[' 0 = 1 ']'1
Error: Process completed with exit code 1.
