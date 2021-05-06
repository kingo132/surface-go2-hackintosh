# surface-go2-hackintosh
Install hackintosh into surface go 2

## Computer Spec:

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

## Current progress
- [x] Internal Speakers
- [x] Internal microphone
- [ ] Combojack headphones (haven't test)
- [x] SpeedStep
- [x] Touch screen
- [x] Surface type cover, both keyboard and trackpad Multi-Touch gestures
- [ ] Front & read camera (won't work)
- [ ] Ir camera (won't work)
- [x] TF Card reader (Partially work, read/write speed is limited at 8MB/s)
- [x] Type-c to HDMI
- [x] Type-c to USB3 & USB2
- [ ] Power, volume down and up button
- [ ] NFC (won't work)
- [ ] Sleep/wake, will stuck at surface logo when wake

## Related issues
* https://github.com/VoodooI2C/VoodooI2CHID/pull/48
* https://www.reddit.com/r/hackintosh/comments/mwrzxg/intel_igpu_hdmiinternal_screen_problem/
* https://github.com/linux-surface/linux-surface/wiki/Surface-Go-2

## Disable the sleep first
https://gist.github.com/pwnsdx/2ae98341e7e5e64d32b734b871614915

## Useful links
* https://www.anandtech.com/show/6355/intels-haswell-architecture/3
