# Hackintosh-Z490H-10900KF-6650XT
It's work stable on Ventura(13). adequate for daily usage.

Anyway, don’t forget to edit file `EFI/OC/config.plist`, you should generate your own [SMBIOS](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html) info.

![Using](https://github.com/LTHS20/Hackintosh-ROG-Z490H-10900KF-6650XT/blob/master/Images/Screenshot%202023-04-07%20at%2019.31.57.png)

## Hardware
* Motherboard: ASUS ROG STRIX Z490H
    * Ethernet: Intel I225-V 2.5Gbit
    * Audio: SupremeFX S1220A CODEC (Realtek ALCS1220A)
* CPU: Intel 10th 10900KF
* GPU: AMD Radeon RX 6650XT (deceived)
* RAM: Crucial Micron DDR4 3200 32GB * 4
* SSD:
    * NVME: ZhiTai PC005 Active 1TB
    * NVME: Samgsung 980 500GB
    * SATA: WD Blue SATA 1024GB
* HDD: WD Ultrastar DC HA210 1TB
* Wi-Fi/BT: DW1560_DELL

## Software
* OpenCore: 0.9.1-RELEASE
* MacOS: Ventura(13) latest

## Working
* [x] AMD Radeon RX 6650XT (dGPU)
* [x] Audio Realtek ALCS1220A
* [x] Intel I225-V 2.5Gb Ethernet
* [x] Wi-Fi/BT (DW1560_DELL)
* [x] USB (3.2Gen2-C/3.2Gen2-A/3.2Gen1-A*4)
* [x] Restart/Shutdown
* [x] Sleep/Wake
* [x] Power Management (Native support)

## Custom

### SMBIOS
```xml
<key>PlatformInfo</key>
<dict>
    <key>Generic</key>
    <dict>
        <key>AdviseFeatures</key>
        <false/>
        <key>MLB</key>
        <string>XXXXXXXXXXXXXXXXXXXX</string>
        <key>MaxBIOSVersion</key>
        <false/>
        <key>ProcessorType</key>
        <integer>0</integer>
        <key>ROM</key>
        <data></data>
        <key>SpoofVendor</key>
        <true/>
        <key>SystemMemoryStatus</key>
        <string>Auto</string>
        <key>SystemProductName</key>
        <string>iMacPro1,1</string>
        <key>SystemSerialNumber</key>
        <string>XXXXXXXXXXXXXXXXXXXX</string>
        <key>SystemUUID</key>
        <string>XXXXXXXXXXXXXXXXXXXX</string>
    </dict>
</dict>
```
You need to generate with `iMacPro1,1` and fill in the `MLB`, `SystemSerialNumber`, `SystemUUID`

### BIOS
#### Disable
* Fast Boot
* VT-d
* CSM
* Intel SGX

#### Enable
* Above 4G decoding
* Hyper-Threading
* EHCI/XHCI Hand-off

OS type choose `Other` type
Clear Secure Boot Keys

## Referenced from
* https://github.com/douglas85rj/Hackintosh---ASUS-Z490H_intel-i910900_RX6800-
* https://github.com/tiomars/Hackintosh-ROG-STRIX-Z490I
