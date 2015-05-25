<h1>DELL xps13 2015 (9343) Linux Support</h1>
Tips and tricks to make XPS13 2015 work with linux.

~~BIOS A01 is [out] (http://www.dell.com/support/home/us/en/04/Drivers/DriversDetails?driverID=RHPC0&productCode=xps-13-9343-laptop)~~  
~~BIOS A02 is [out] (http://www.dell.com/support/home/en/en/nldhs1/Drivers/DriversDetails?driverId=F2PRR)~~  
BIOS A03 is [out] (http://www.dell.com/support/home/en/en/nldhs1/Drivers/DriversDetails?driverId=XY677&fileId=3444115068&osCode=WB64A&productCode=xps-13-9343-laptop&languageCode=EN&categoryId=BI)


## Other resources
[major.io website] (https://major.io/2015/02/03/linux-support-dell-xps-13-9343-2015-model/) ([@major] (https://github.com/major))  
[Barton's blog last update, announcing BIOS A01] (http://bartongeorge.net/2015/02/23/update-2-dell-xps-13-laptop-developer-edition-sputnik-gen-4/)  
[Kernel bug ticket for the sound issue] (https://bugzilla.kernel.org/show_bug.cgi?id=93361) by [@major] (https://github.com/major)    
[Patch for the touchpad] (http://lkml.iu.edu/hypermail/linux/kernel/1502.2/02389.html)  
[XPS13 2015 drivers page] (http://www.dell.com/support/home/us/en/04/product-support/product/xps-13-9343-laptop/drivers)  
[Dell XPS 13 2015 model 9343 on Ubuntu 15.04, dmidecode, lsusb, lspci] (https://gist.github.com/semenko/60015029e13c1de65ff6) by [@semenko] (https://github.com/semenko)  
[Patch that you can apply to 3.18 or 3.19 kernels that eliminates the trackpad freeze] (https://bugzilla.redhat.com/attachment.cgi?id=990188) by [@major] (https://github.com/major)  
[Installing ubuntu 14.04 on the new Dell XPS 13](http://forthescience.org/blog/2015/04/21/installing_ubuntu_14_04_on_the_new_dell_xps_13_v2)  
[Ubuntu 14.04 Touchpad Freezing Fix – XPS (2015)](http://en.community.dell.com/support-forums/software-os/f/3525/t/19631683?dgc=SM&cid=259487&lid=5521379)  
IRC : #xps13 (freenode)

**Quote about the repeating keystroke issue (Author ?)**  
``Someone asked about the fix for the repeating keypresses. Yes, it was traced back to the source and will be fixed on all affected Dell platforms soon. I just saw that the one for 9343 was promoted to our factories so should be up on support.dell.com any day now as BIOS A01``

## Actual situation
From **A01**, linux support is quite decent. The different encountered problems can be :
 - touchpad freezing (i2c / ps2 mode)
 - no sound (or sound after 2 cold reboots of some kernels, depending on boot options)
 - ~~repeating keystroke issue (should be fixed with BIOS A01)~~ (fixed with BIOS A01)
 - ?
 
From **A02**, boot options are not needed anymore. Sound will be ok (HDA mode by default) and touchpad will be in i2c mode as ``!Windows 2013`` is not needed anymore to make audio work!  
It's still recommended to have a recent kernel (3.17+). Verify your touchpad mode with ``xinput``.  
It should give you something like ``DLL0665:01 06CB:76AD UNKNOWN`` if i2c mode is on. You could have to blacklist psmouse too. See [here](config6/psmouse-blacklist.conf).

See the collected configurations [here](https://github.com/mpalourdio/xps13/blob/master/configurations.md)
 
## What about you ?
If you (are able to) use linux on this computer, please specify :
 - kernel version
 - boot options
 - pros/cons of this combo
 - applied patches
 - distribution
 - anything you think is useful to know  
 
Thanks to contributors !
