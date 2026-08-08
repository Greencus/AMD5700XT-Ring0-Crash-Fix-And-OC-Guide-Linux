# AMD RX 5700 XT Ring0 Crash Fix and safe overclock guide for Linux
Guide for troubleshooting. Specifically for the Gigabyte RX 5700 XT Gaming OC, but may work elsewhere. I will also be including overclock profiles and some information on clocking this card. With the original repo this is forked from, I still had crashes on some demanding games. I've finally managed to address that and get everything completely stable!!

**Things to check first:**
- GPU must have 2 dedicated power lanes, be sure there is not a loose cable.
- Check GPU fans for dust, check thermal paste, and just make sure the gpu isn't running into thermal issues.

## **LACT HAS MORE PROFILES FOR OVERCLOCKS**

**STEPS TO FOLLOW (CoreCtrl):**
- Replace the GRUB_CMDLINE_LINUX_DEFAULT line in /etc/default/grub with: `GRUB_CMDLINE_LINUX_DEFAULT='quiet splash amdgpu.noretry=0 amdgpu.lockup_timeout=0 iommu=pt amdgpu.gpu_recovery=1 amdgpu.runpm=0 amdgpu.mcbp=0 amdgpu.ppfeaturemask=0xf7fff'`
- Run `sudo update-grub` and reboot.
- Now download [CoreCtrl](https://gitlab.com/corectrl/corectrl) and the file **FIX.ccpro** listed in this repository.
- Follow [this guide](https://gitlab.com/corectrl/corectrl/-/wikis/Setup) to setup CoreCtrl.
- Import **FIX.ccpro** in CoreCtrl's profile list.
- Modify the fan curve to your liking and apply.

**STEPS TO FOLLOW (LACT):**
- Replace the GRUB_CMDLINE_LINUX_DEFAULT line in /etc/default/grub with: `GRUB_CMDLINE_LINUX_DEFAULT='quiet splash amdgpu.noretry=0 amdgpu.lockup_timeout=0 iommu=pt amdgpu.gpu_recovery=1 amdgpu.runpm=0 amdgpu.mcbp=0 amdgpu.ppfeaturemask=0xf7fff'`
- Run `sudo update-grub` and reboot.
- Now download [LACT](https://github.com/ilya-zlobintsev/LACT) and the file **config.yaml** listed in this repository.
- Replace both instances of `[GPU ID]` in the config.yaml file with the ID that appears in the lact gui. The ID appears in the lact gui when you click the box that allows you to select your gpu, under your listed gpu will be the ID
- Replace the current **config.yaml** file to the one downloaded from this repository in /etc/lact/
- Start LACT daemon with `sudo systemctl enable --now lactd` and add it to boot with `sudo systemctl enable lactd` (Find the equivalent command for your INIT system)
- Start LACT with GUI and change your profile to "Safe OC" or "High OC" if you would like an overclock, or leave it on default. If you reset the default profile, "Altered Fork" is the same as what default is set to in the config file.
- Modify the fan curve to your liking and apply.


**For more information check [Resources.md](/Resources.md/).**
Your Gpu may need a different voltage to clock ratio and or a lower clockspeed so look at the resources to help you fine tune your settings to your own card if necessary.


