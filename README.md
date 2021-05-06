# surface-go2-hackintosh
Install hackintosh into surface go 2

## Computer Spec

| Component        | Brank                              |
| ---------------- | ---------------------------------- |
| CPU              | Intel Core m3 8100Y (Amber Lake Y) |
| iGPU             | Intel® UHD Graphics 615            |
| Audio            | Realtek ALCxxx                     |
| Ram              | 8 GB DDR4 xxxx Mhz                |
| Wifi + Bluetooth |              |
| Storage             | 128GB SSD       |
| TF Card reader | Realtek PCI-E Card Reader, 152D:1237 |
|Front&Rear camera|Intel(R) AVStream Camera 2500, ISP Interface, 8086:591c|
|Type cover trackpad|Microsoft type cover, 045E:096F|
|Touch Screen|ELAN9038, \_SB.PCI0.I2C1.TPL1, 8086:9d61|
|Screen|BOE CQ NV105WAM-N31, BOE088B|
|NFC|NXP NFC Client Device, NXP3001|
|Battery|26.81Wh 7.66v 3500mAh|
|LTE(if available)|Surface Mobile Boradband, USB device, 045E:09A5|
|GPS(if available)|MSHW0142|

## Todo list
- [ ] Trackpad often mistouch when typing
- [ ] Sleep/wake doesn't work
- [ ] Ambient sensor doesn't work
- [ ] Speaker seems a little quiet

## Current progress
Things will work
- [x] Internal Speakers
- [x] Internal microphone
- [ ] Combojack headphones (haven't test)
- [x] SpeedStep
- [x] Touch screen
- [x] Surface type cover, both keyboard and trackpad Multi-Touch gestures
- [x] TF Card reader (Partially work, read/write speed is limited at 8MB/s)
- [x] Type-c to HDMI
- [x] Type-c to USB3 & USB2
- [ ] Power, volume down and up button
- [ ] Sleep/wake, will stuck at surface logo when wake
- [ ] Ambient sensor

Things won't work
- [ ] Front & rear camera (won't work)
- [ ] Ir camera (won't work)
- [ ] NFC (won't work)

## Lower the temperature
By default, the long term TDP is set to 8 watt, you can lower it to 7 watt to maintain the temp below 80c. Also, offset the cpu voltage by 115mv also help cool the device.
```
sudo ./voltageshift buildlaunchd -115 0 0 0 0 0 7 28 18 0.002 60
```
You can remove this by using:
```
./voltageshift removelaunchd
```
Or manual remove by:
 ```
sudo rm /Library/LaunchDaemons/com.sicreative.VoltageShift.plist
sudo rm -R /Library/Application\ Support/VoltageShift
```
Please notice if you cannot boot the system after installing, you need to:
1. Fully turn off Computer (not reboot):
2. Boot start by Command-R to recovery mode :
3. In "Terminal" Enable the CSR protection to stop undervoltage running when boot 
```
csrutil enable    
```
4. Reboot and Remove all file above

## BIOS option address

* CFG Lock: VarStoreInfo (VarOffset/VarName): 0x3C, VarStore: 0x3 (CpuSetup)
* VT-d: VarStoreInfo (VarOffset/VarName): 0xE3, VarStore: 0x2 (SaSetup)

## Related issues
* https://github.com/VoodooI2C/VoodooI2CHID/pull/48
* https://www.reddit.com/r/hackintosh/comments/mwrzxg/intel_igpu_hdmiinternal_screen_problem/
* https://github.com/linux-surface/linux-surface/wiki/Surface-Go-2

## Disable the sleep first
https://gist.github.com/pwnsdx/2ae98341e7e5e64d32b734b871614915

## Useful links
* https://www.anandtech.com/show/6355/intels-haswell-architecture/3
