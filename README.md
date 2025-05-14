# Version
Linux 6.12.25-1-MANJARO #1 SMP PREEMPT_DYNAMIC Sat, 26 Apr 2025 05:36:37 +0000 x86_64 GNU/Linux

# ManjaroInstall
Use Ventoy (or similar) software to create bootable USB for manjaro.
Install with non-propietary drivers. My NVIDIA 4080 super did not like the proprietary drivers off the bat.
Encrypt if you want to. Will use a USB key to make this seamless later.

# Install additional packages you might want.
```
pamac update
pamac install vim
```
# Customizations
```
extensions: enable launch new instance
settings
> multitasking: turn off hot corners, turn off active screen edge
> power:increase auto suspend to an hour
> mouse & touchpad: pointer speed max
> keyboard:
  > shortcuts:
    system:  super + R, run command prompt
    windows: super + up, maximize windows vertically
    custom:  super + T, launch new terminal, /usr/bin/kgx
    

keyboard shortcuts:
> 
```
# NVIDIA propietary drivers install

```
# Run this to add ibt=off to the end of the GRUB_CMDLINE_LINUX_DEFAULT
sed -i "s|\(GRUB_CMDLINE_LINUX_DEFAULT='.*\)'|\1 ibt=off'|" /etc/default/grub
update-grub

# Now install nvidia drivers, you might lose screen when updating. This ensure you power off properly and can power on when you are done.
mhwd -a pci nonfree 0300 && poweroff

# After rebooting enable 120hz from display settings
```
TODO:
Create auto decrypt USB key
