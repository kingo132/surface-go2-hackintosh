# surface-go2-hackintosh
Install hackintosh into surface go 2



Currently working on the annoying sleep/awake issue.
After sleep, the type cover can wake the computer, also the USB mouse can not wake it too. It has to push the power button to wake it. But it will just show a surface logo on the screen. And I can certain the system is waked up already, except the screen. And also if I connect an external monitor, the external monitor will show up on the login screen too. No matter by sleep menu of left-top cornor or by close the type cover, the result is the same.
I have research for several days about this problem. Nearly tried all the methods about the awake black screen fix of hackintosh. No luck.
I can somewhat certain it is related to iGPU, built-in display or maybe the power button, other component seems fine after the wake.
What I have tried:
1. different framebuffer id and many other Whatevergreen fixes
2. After USB customization, still the same
3. Unlocked cfg-lock in BIOS, still the same
4. darkwake boot args, tried 0 ~ 11, all the same
5. SSDT-GPRW fix, no luck
6. HibernationFixup.kext, no luck
7. Played many combos with pmset, no luck
8. Tried many fixes in DSDT, no luck
9. Turned on the hidpi, no luck
10. Disabled discrete gpu, no luck
11. Compared the framebuffers info in ioreg before and after sleep, they are the same except the IOHibernateState and IOScreenREstoreState properties, as in the screenshot below
![QQ20210506-111250](https://user-images.githubusercontent.com/46492291/117236910-528b0980-ae5c-11eb-813a-6bf952054734.png)
![QQ20210506-111321](https://user-images.githubusercontent.com/46492291/117236913-5454cd00-ae5c-11eb-8e30-933f73f2379c.png)
Here is what I'm planning to do next:
1. Continue playing around pmset
2. Continue playing around DSDT debug and fixes
