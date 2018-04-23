# stupid-hacks
things i shouldn't have had to do to get things working like they should.

### SDRPlay RSP 2 under Arch Linux with CubicSDR:

- Download the official API/Driver from cubic's website.
- Run it with the preserve option, let it fail.
- edit the install_lib.sh, change `ARCH='arch'` to `ARCH='uname -m'`
- run the installer again, should work now.
- add /usr/local/lib to a file in /etc/ld.conf.d/
- install cubicsdr-git from the AUR
- install soapysdrplay-git or whatever it is from the AUR

things should work now.

### Telegram won't show up when running it under deepin?
- create /usr/bin/telegram with the following contents:
```bash
#!/bin/bash
unset XDG_CURRENT_DESKTOP
/usr/bin/telegram-desktop
```

- replace /usr/bin/telegram-desktop in the .desktop of the launcher with /usr/bin/telegram.

### HTC 10 RUU not running on a nice, fresh windows install?

yeah you're gonna need the Visual Studio 2008 redistributable library. I wish I was kidding.

### Use more than one GPU with the nvidia linux drivers
```bash
$ sudo nvidia-xconfig --multigpu=AUTO
```
