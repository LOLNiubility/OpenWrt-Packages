# luci-app-3ginfo-lite

![GitHub release (latest by date)](https://img.shields.io/github/v/release/4IceG/luci-app-3ginfo-lite?style=flat-square)
![GitHub stars](https://img.shields.io/github/stars/4IceG/luci-app-3ginfo-lite?style=flat-square)
![GitHub forks](https://img.shields.io/github/forks/4IceG/luci-app-3ginfo-lite?style=flat-square)
![GitHub All Releases](https://img.shields.io/github/downloads/4IceG/luci-app-3ginfo-lite/total)

Luci-app-3ginfo-lite is fork from https://github.com/obsy/packages/tree/master/easyconfig/addon

### <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24"> Luci-app-3ginfo-lite is a simplified version of the 3ginfo project. Works with mPCI-E/M.2 and USB 3G/LTE modems.

### <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24"> Luci-app-3ginfo-lite jest uproszczoną wersją projektu 3ginfo. Działa z modemami mPCI-E/M.2 oraz USB 3G/LTE.


``` bash
Supported devices (tested devices):
 - Quectel EM12/EM160R-GL
 - Quectel EP06-E
 - Quectel EC20/EC25
 - Quectel RG502Q
 - ZTE MF821
 - ZTE MF286/MF286A/MF289F HW AT2
 - ZTE MF286D/MF289F HW AT1
 - ZTE MF286R (Modem comes in several versions, not all work stably)
 - Huawei E3372/E3276
 - Huawei E3276 HiLink
 - Huawei E5786 (mobile-wifi / HiLink)
 - Telit Ln940 / HP lt4220
 
Not tested devices (Not all data can be shown and scripts need to be corrected):
 - Sierra Wireless MC7710
 - Sierra Wireless EM7455
 - ASKEY WWHC050
 - BroadMobi BM806U
 - Mikrotik R11e-LTE
 - Mikrotik R11e-LTE6
 - HiLink modems (ZTE / Alcatel)

```

## <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24"> Installation / <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24"> Instalacja
``` bash
> For conventional modems.
Modem drivers are required for proper operation.
opkg install kmod-usb-serial kmod-usb-serial-option

> For Huawei HiLink modems.
opkg install wget-nossl

Dependency required.
opkg install sms-tool_2021-12-03-d38898f4-1_XXX.ipk

#The sms-tool package is not available in the OpenWrt core repository. 
#Sms-tool is only available in the eko.one.pl forum repository. 
#If you do not have an image from forum eko.one.pl you have to compile the package manually.

#For images from the eko.one.pl forum we proceed:
opkg update
opkg install sms-tool

#Package installation example
Latest version ➜ https://github.com/4IceG/luci-app-3ginfo-lite/releases/latest

wget https://github.com/4IceG/luci-app-3ginfo-lite/releases/download/1.0.17-20220701/luci-app-3ginfo-lite_1.0.17-20220701_all.ipk -O /tmp/luci-app-3ginfo-lite_1.0.17-20220701_all.ipk
opkg install /tmp/luci-app-3ginfo-lite_1.0.17-20220701_all.ipk

#The package can be added to Openwrt sources in two ways:

cd feeds/luci/applications/
git clone https://github.com/4IceG/luci-app-3ginfo-lite.git
cd ../../..
./scripts feeds update -a; ./scripts/feeds install -a
make menuconfig

or e.g.

cd packages/
git clone https://github.com/4IceG/luci-app-3ginfo-lite.git
git pull
make package/symlinks
make menuconfig

You may need to correct the file paths and the number of folders to look like this:
feeds/luci/applications/luci-app-3ginfo-lite/Makefile
or
packages/luci-app-3ginfo-lite/Makefile

Then you can compile the packages one by one, an example command:
make V=s -j1 feeds/luci/applications/luci-app-3ginfo-lite/compile
```


### <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24"> Preview / <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24"> Podgląd

![](https://github.com/4IceG/Personal_data/blob/master/zrzuty/tano_3ginfo3.png?raw=true)

## <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_United_Kingdom.png" height="24"> Thanks to / <img src="https://raw.githubusercontent.com/4IceG/Personal_data/master/dooffy_design_icons_EU_flags_Poland.png" height="24"> Podziękowania dla
- [obsy (Cezary Jackiewicz)](https://github.com/obsy)
