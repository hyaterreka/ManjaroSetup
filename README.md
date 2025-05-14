# Version
Linux 6.12.25-1-MANJARO #1 SMP PREEMPT_DYNAMIC Sat, 26 Apr 2025 05:36:37 +0000 x86_64 GNU/Linux

# ManjaroSetup
Use Ventoy (or similar) software to create bootable USB for manjaro.
Install with non-propietary drivers. My NVIDIA 4080 super did not like the proprietary drivers off the bat.
Encrypt if you want to. Will use a USB key to make this seamless later.

# Install packages you might want.
pamac update
pamac install vim

# Customizations
extensions: enable launch new instance


# Run this to add ibt=off to the end of the GRUB_CMDLINE_LINUX_DEFAULT
sed -i "s|\(GRUB_CMDLINE_LINUX_DEFAULT='.*\)'|\1 ibt=off'|" /etc/default/grub
update-grub
reboot

# Now install nvidia drivers
mhwd -a pci nonfree 300
