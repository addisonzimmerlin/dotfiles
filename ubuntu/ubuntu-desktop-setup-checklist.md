# Ubuntu Desktop Setup Checklist

## Installation

- [ ] Boot from the Ubuntu Desktop installation DVD
- [ ] Select "Try Ubuntu"
- [ ] Open Terminal
- [ ] Find the path of the computer's hard drive
	```sh
	sudo fdisk -l
	```
- [ ] Erase the hard drive
	```sh
	sudo dd if=/dev/zero of=/dev/nvme0n1 bs=1M
	```
- [ ] Reboot
- [ ] Boot from the Ubuntu Desktop installation DVD (again)
- [ ] Select "Install Ubuntu"



## Setup

1. Open two Terminal windows. In the first Terminal window, run:
	```sh
	mkdir ~/.setup/
	touch ~/.setup/error.log
	tail -F ~/.setup/error.log
	```

1. In the second Terminal window, run:
	```sh
	wget https://raw.githubusercontent.com/prodctrl/echo_/master/echo_.sh -O ~/.setup/echo_.sh
	wget https://raw.githubusercontent.com/addisonzimmerlin/dotfiles/master/ubuntu/ubuntu-desktop-setup.sh -O ~/.setup/ubuntu-desktop-setup.sh
	sh ~/.setup/ubuntu-desktop-setup.sh "add*************@gmail.com" 2> ~/.setup/error.log
	```

1. Reboot

1. `Firefox` › `☰` › `Settings`
	- General
		- Network Settings
			- [ ] Enable DNS over HTTPS: unchecked
	- Home
		- [ ] Homepage and new windows: Custom URLs...
			- [ ] file:///home/addison/Rundown%20Creator,%20Inc%20Dropbox/Addison%20Zimmerlin/homepage.html
		- [ ] New tabs: Blank Page
	- Privacy & Security
		- Logins and Passwords
			- [ ] Ask to save logins and passwords for websites: unchecked

1. Install the [1Password Firefox add-on](https://support.1password.com/getting-started-browser/)
	- `Firefox` › `☰` › `Add-ons` › `1Password`
		- [ ] Run in Private Windows: Allow

1. Install the [Firefox Multi-Account Containers add-on](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/)

1. Import [Firefox bookmarks](https://github.com/addisonzimmerlin/firefox-bookmarks)

1. `Dropbox` › `Preferences...`
	- Bandwidth
		- Upload rate
			- [ ] Don't limit: selected
		- LAN sync
			- [ ] Enable LAN sync: unchecked
	- Sync
		- Selective Sync...
			- [ ] Choose folders

1. Set Favorites
	- Files
	- Firefox Web Browser
	- Sublime Text
	- Terminal
	- Meld
	- VirtualBox
	- 1Password
	- Ubuntu Software
	- Screenshot

1. Set Files Bookmarks
	- git
	- diff
	- before
	- after
	- Dropbox
	- Exocortext
	- Coding
	- Tmp