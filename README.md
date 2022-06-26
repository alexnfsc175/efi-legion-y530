# efi-legion-y530

## GenSMBIOS

Download [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS), usar iMac19,1

OpenCore for Lenovo Legion Y530

```bash
# macOS 12 Monterey
macrecovery.py -b Mac-E43C1C25D4880AD6 -m <real MLB> -os latest download
```

## Kexts

[AppleALC](https://github.com/acidanthera/AppleALC/releases)

[WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases)

[Lilu](https://github.com/acidanthera/Lilu/releases)

[AirportItlwm](https://github.com/OpenIntelWireless/itlwm/releases)

[BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM/releases)

[BrightnessKeys](https://github.com/acidanthera/BrightnessKeys/releases)

[IntelBluetoothFirmware](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases)

[CpuTscSync](https://github.com/acidanthera/CpuTscSync/releases)

[NVMeFix](https://github.com/acidanthera/NVMeFix/releases)

[RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X/releases)

[SMCBatteryManager.kext](https://github.com/acidanthera/VirtualSMC/releases)

[SMCProcessor.kext](https://github.com/acidanthera/VirtualSMC/releases)

[VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases)

[VoodooI2C](https://github.com/VoodooI2C/VoodooI2C/releases)

[VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2/releases)

[]()
[]()
[]()

## Mapeamento USB

[Intel Usb Mapping](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html)

[Usb Mapping](https://dortania.github.io/OpenCore-Post-Install/usb/manual/manual.html#usb-mapping-the-manual-way)

[USBMap](https://github.com/corpnewt/USBMap)

[Data](https://github.com/acidanthera/OcBinaryData)

## Teclado

<https://github.com/acidanthera/OpenCorePkg/blob/master/Utilities/AppleKeyboardLayouts/AppleKeyboardLayouts.txt>
<http://www.unit-conversion.info/texttools/hexadecimal/>
text to hex number
pt_BR:128 -> 70745F42 523A3132 38

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
 <key>PciRoot(0x0)/Pci(0x1b,0x0)</key>
 <dict>
  <key>layout-id</key>
  <data>AQAAAA==</data>
 </dict>
</dict>
</plist>
```

<https://www.youtube.com/watch?v=hDIC1aOAsyE&t=1232s>

## TEST

clear dictionary from NVRAM -> LegacySchema

## Formatando o pendrive

[link](https://www.techtarget.com/searchwindowsserver/tip/Using-Diskpart-to-create-extend-or-delete-a-disk-partition#:~:text=At%20the%20DISKPART%20prompt%2C%20type%20create%20partition%20primary%20size%3D10000,be%20used%20for%20the%20partition.)

Limpando as partições do pendrive

```dos
diskpart
diskpart> list disk
diskpart> select disk <X>
diskpart> clean
diskpart> convert gpt
```

Criando um nova partição

```dos
diskpart> create partition primary size=1000
diskpart> list partition
diskpart> select partition 1
diskpart> format fs=fat32 quick
# ou      format fs=ntfs quick
# ou      format fs=exFAT quick
diskpart> active
diskpart> ASSIGN LETTER=E
diskpart> exit
```

## Post-Installation

- Run following command in terminal to Fix Headphone Audio

```bash
sudo sh -c "$(curl -fsSL https://raw.githubusercontent.com/alexnfsc175/efi-legion-y530/main/AudioFix.sh)"

```
