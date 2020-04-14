# macOS Setup Checklist

## Installation

- [ ] Sign out of Adobe Creative Cloud
- [ ] Sign out of iCloud
- [ ] Shutdown
- [ ] [Reset SMC](https://support.apple.com/en-us/HT201295)
- [ ] Start internet recovery
	- `Command` + `Option` + `R` = the latest version
	- `Shift` + `Command` + `Option` + `R` = the version that came with your Mac or the closest thing still available
- [ ] Format the hard drive in Disk Utility
	- `View` › `Show All Devices`
	- Select the parent drive
	- Press the `Erase` button, select `APFS`, and press `Erase`
- [ ] In Terminal, run:
	```sh
	diskutil secureErase 0 /dev/diskX
	```
- [ ] Reboot
- [ ] Start internet recovery (again)
- [ ] Format the hard drive in Disk Utility (again)
- [ ] Install macOS
	- [ ] Skip iCloud sign in
- [ ] Install updates



## System Preferences

#### System Preferences
- Apple ID
	- [ ] Sign in to iCloud
	- iCloud
		- [ ] Photos, Mail, Safari, Keychain: unchecked
		- [ ] iCloud Drive, Contacts, Calendars, Reminders, Notes, Find My Mac, News, Stocks, Home, Siri: checked
- Desktop & Screen Saver
	- Desktop
		- Custom Color...
			- [ ] #0C0A1F
	- Screen Saver
		- [ ] Screen Saver Options...
		- [ ] Start after: 5 Minutes
		- [ ] Show with clock: checked
		- Hot Corners...
			- [ ] Top-left: Put Display to Sleep
			- [ ] Bottom-left: Start Screen Saver
			- [ ] Top-right: Mission Control
			- [ ] Bottom-right: Desktop
- Dock & Menu Bar
	- Sound
		- [ ] Show in Menu Bar: checked
		- [ ] Drop-down menu: always
	- Battery
		- [ ] Show Percentage: checked
	- Clock
		- [ ] Display the time with seconds: checked
- Siri
	- [ ] Enable Ask Siri: checked
	- [ ] Show Siri in menu bar: checked
- Notifications
	- Do Not Disturb
		- [ ] From: 10:00 PM to 7:00 AM: checked
		- [ ] When the display is sleeping: checked
		- [ ] When the screen is locked: checked
		- [ ] Allow repeated calls: checked
- Security & Privacy
	- General
		- [ ] Require password 5 seconds after sleep or screen saver begins: checked
	- Firewall
		- [ ] Turn on the firewall
- Bluetooth
	- [ ] Show Bluetooth in menu bar: checked
- Sound
	- Output
		- [ ] Output: Internal Speakers
- Printers & Scanners
	- [ ] Add printer(s)
- Keyboard
	- Keyboard
		- [ ] Customize Control Strip...: Launchpad, Mission Control, Volume Slider, Siri
	- Text
		- [ ] Add [text snippets](https://github.com/addisonzimmerlin/email/blob/master/text-snippets.md)
		- [ ] Correct spelling automatically: unchecked
		- [ ] Capitalize words automatically: unchecked
		- [ ] Add period with double-space: unchecked
		- [ ] Use smart quotes and dashes: unchecked
	- Input Sources
		- [ ] Show Input menu in menu bar: checked
- Displays
	- Night Shift
		- [ ] Schedule: Sunrise to Sunset
- Battery
	- Power Adapter
		- [ ] Turn display off after: 25 min
		- [ ] Prevent computer from sleeping automatically when the display is off: checked
		- [ ] Put hard disks to sleep when possible: unchecked
		- [ ] Wake for network access: checked
		- [ ] Enable Power Nap while plugged into a power adapter: checked
- Sharing
	- [ ] Verify computer name
	- [ ] Screen Sharing: checked
	- [ ] File Sharing: checked


#### Bash Profile
- [ ] Run:
	```sh
	curl https://raw.githubusercontent.com/addisonzimmerlin/dotfiles/master/macos/.zshrc > ~/.zshrc
	```


#### nanorc
- [ ] Run:
	```sh
	curl https://raw.githubusercontent.com/addisonzimmerlin/dotfiles/master/macos/.nanorc > ~/.nanorc
	```


#### git
- [ ] Install [git](https://git-scm.com/download/mac)
- [ ] Run:
	```sh
	mkdir ~/git/
	git config --global user.name "Addison Zimmerlin"
	git config --global user.email "add*************@gmail.com"
	sudo chmod -R 777 ~/.config/
	```


#### SSH
- [ ] `mkdir ~/.ssh/`
- [ ] Copy SSH keys
- [ ] Create SSH key for GitHub
	```sh
	ssh-keygen -t ed25519 -N "" -C "add*************@gmail.com" -f ~/.ssh/github
	cat ~/.ssh/github.pub
	```
- [ ] [Add SSH key to your GitHub account](https://github.com/settings/keys)
- [ ] Copy [SSH config](https://github.com/prodctrl/.dotfiles/blob/master/cfg/ssh/config)
	```sh
	nano ~/.ssh/config
	```
- [ ] `sudo chmod -R 700 ~/.ssh/`


#### /etc/hosts
- [ ] Run:
	```sh
	curl https://raw.githubusercontent.com/addisonzimmerlin/dotfiles/master/hosts > ~/hosts.tmp
	cat ~/hosts.tmp | sudo tee -a /etc/hosts
	rm ~/hosts.tmp
	```



## macOS Application Preferences

#### Finder
- `Finder` › `Preferences...`
	- General
		- [ ] Show these items on the desktop:
			- [ ] Hard disks: checked
			- [ ] External disks: checked
			- [ ] CDs, DVDs, and iPods: checked
			- [ ] Connected servers: checked
		- [ ] New Finder windows show: addison
	- Sidebar
	- Advanced
		- [ ] Show all filename extensions: checked
		- [ ] When performing a search: Search the Current Folder
- [ ] `View` › `Show Status Bar`


#### Mail
- [ ] Add accounts (using profiles)
- [ ] `Mail` › `Preferences...`
	- General
		- [ ] Dock unread count: (smart mailbox)
		- [ ] New message notifications: (smart mailbox)
	- Fonts & Colors
		- [ ] Message font: Helvetica 14
	- Viewing
		- [ ] Show most recent message at the top: checked
	- Composing
		- [ ] Send new messages from s*****t@rundowncreator.com
	- Signatures
		- [ ] Add [signatures](https://github.com/addisonzimmerlin/email/blob/master/signatures.md)


#### Messages
- [ ] `Messages` › `Preferences...`
	- Account
		- Settings
			- [ ] Enable this account: unchecked


#### Calendar
- `Calendar` › `Preferences...`
	- General
		- [ ] Default Calendar: Appointments


#### Contacts
- `Contacts` › `Preferences...`
	- [ ] Sort By: First Name


#### Image Capture
- [ ] Create directory for scanned files
	```sh
	mkdir ~/scans/
	```
- Settings
	- [ ] Scan Mode: Flatbed
	- [ ] Kind: Color
	- [ ] Resolution: 300 dpi
	- [ ] Size: US Letter
	- [ ] Scan To: ~/scans
	- [ ] Format: PDF
	- [ ] Combine into single document: checked


#### TextEdit
- `TextEdit` › `Preferences...`
	- New Document
		- [ ] Plain text: selected
		- [ ] Correct spelling automatically: unchecked
		- [ ] Smart copy/paste: unchecked
		- [ ] Smart quotes: unchecked
		- [ ] Smart dashes: unchecked



## Third-Party Applications

#### 1Password
- [ ] Install [1Password](https://1password.com/)


#### Firefox
- [ ] Install [Firefox](https://www.mozilla.org/en-US/firefox/new/)
- [ ] `Firefox` › `Preferences...`
	- General
		- Network Settings
			- [ ] Enable DNS over HTTPS: unchecked
	- Home
		- [ ] Homepage and new windows: Custom URLs...
			- [ ] file:///Users/addison/Rundown%20Creator,%20Inc%20Dropbox/Addison%20Zimmerlin/homepage.html
		- [ ] New tabs: Blank Page
	- Privacy & Security
		- Logins and Passwords
			- [ ] Ask to save logins and passwords for websites: unchecked
- [ ] Install the [1Password add-on](https://support.1password.com/getting-started-browser/)
	- `Tools` › `Add-ons` › `1Password`
		- [ ] Run in Private Windows: Allow
- [ ] Install the [Firefox Multi-Account Containers add-on](https://addons.mozilla.org/en-US/firefox/addon/multi-account-containers/)
- [ ] Import [Firefox bookmarks](https://github.com/addisonzimmerlin/firefox-bookmarks)


#### Chrome
- [ ] Install [Chrome](https://www.google.com/chrome/)


#### Opera
- [ ] Install [Opera](https://www.opera.com/)


#### Spotify
- [ ] Install [Spotify](https://www.spotify.com/us/)
- [ ] `Spotify` › `Preferences`
	- Music Quality
		- [ ] Streaming quality: Very High
	- Display Options
		- [ ] Show unavailable songs in playlists: checked
	- Advanced
		- Startup and Window Behaviour
			- [ ] Open Spotify automatically after you log into the computer: No


#### Things 3
- [ ] Install [Things 3](https://apps.apple.com/us/app/things-3/id904280696?mt=12)


#### LibreOffice
- [ ] Install [LibreOffice](https://www.libreoffice.org/)


#### DYMO Label
- [ ] Install [DYMO Label](https://www.dymo.com/en_US/online-support)


#### Adobe Creative Cloud
- [ ] Install [Adobe Creative Cloud](https://www.adobe.com/creativecloud.html)
	- [ ] Install Photoshop
	- [ ] Install Illustrator
	- [ ] Install Premiere Pro
	- [ ] Install After Effects
	- [ ] Install Media Encoder
	- [ ] Install Audition
	- [ ] Install Acrobat
	- [ ] Install Bridge


#### OBS
- [ ] Install [OBS](https://obsproject.com/)


#### Real VNC Viewer
- [ ] Install [Real VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)


#### NewTek NDI Tools
- [ ] Install [NewTek NDI Tools](https://ndi.tv/tools/)


#### Sublime Text
- [ ] Install [Sublime Text](https://www.sublimetext.com/)
- [ ] Run:
	```sh
	curl https://raw.githubusercontent.com/addisonzimmerlin/dotfiles/master/sublime-text-user-settings.json > ~/Library/"Application Support"/"Sublime Text 3"/Packages/User/Preferences.sublime-settings
	curl https://raw.githubusercontent.com/addisonzimmerlin/dotfiles/master/macos/default-project.sublime-project > ~/default-project.sublime-project
	```
- [ ] Create a new `.scss` file, go to `View` › `Syntax` › `Open all with current extension as...` › `CSS`
- [ ] Copy and paste license


#### iTerm2
- [ ] Install [iTerm2](https://www.iterm2.com/)
- [ ] `iTerm2` › `Preferences...`
	- General
		- Magic
			- [ ] Instant Replay uses 256 MB per session
		- Selection
			- [ ] Copy to pasteboard on selection: unchecked
	- Appearance
		- Tabs
			- [ ] Show tab bar even when there is only one tab: checked
	- Profiles
		- Colors
			- [ ] Background: #00002a
		- Window
			- [ ] Transparency: above the "E" in "Opaque"


#### Transmit
- [ ] Install [Transmit](https://panic.com/transmit/)
- [ ] `View` › `Show One File Browser`
- [ ] `View` › `Remote Browser`
- [ ] `Transmit` › `Preferences...`
	- Files
		- [ ] Double Click Action: Edit in External Editor
	- Transfers
		- [ ] Play: Morse
- [ ] Copy and paste license


#### Sequel Ace
- [ ] Install [Sequel Ace](https://apps.apple.com/us/app/sequel-ace/id1518036000?mt=12)


#### Sequel Pro
- [ ] Install [Sequel Pro](https://www.sequelpro.com/)
- [ ] `Sequel Pro` › `Preferences...`
	- Tables
		- [ ] Reload Table After: Adding a row / Editing a row / Removing a row
	- Auto Update
		- [ ] Automatically check for updates: checked


#### Node.js
- [ ] Install [Node.js](https://nodejs.org/en/)
- [ ] Run:
	```sh
	sudo npm install -g http-server
	mkdir ~/Desktop/www/
	```


#### VirtualBox
- [ ] Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (requires two passes)


#### RESTed
- [ ] Install RESTed from the App Store


#### Visual JSON
- [ ] Install Visual JSON from the App Store


#### DiffMerge
- [ ] Install [DiffMerge](https://sourcegear.com/diffmerge/) using the DMG option
- [ ] `DiffMerge` › `Preferences...`
	- File Windows
		- [ ] Window Font: Courier, 14 Point
- [ ] Run:
	```sh
	mkdir -p ~/diff/before/
	mkdir -p ~/diff/after/
	```


#### Alinof TimerPro
- [ ] Install Alinof TimerPro from the App Store
- [ ] `File` › `Choice of the color theme` › `Black`
- [ ] `File` › `Alarm sounds` › `None`


#### Dropbox
- [ ] Install [Dropbox](https://www.dropbox.com/)
	- `Dropbox` › `Preferences...`
		- Network
			- [ ] Bandwidth › Change Settings... › Upload rate: Don't limit
			- [ ] Enable LAN sync: unchecked
		- Notifications
			- [ ] New files synced: unchecked
		- Sync
			- [ ] Save hard drive space automatically: Off
			- Selective Sync
				- [ ] Choose folders

> If Smart Sync is enabled, you can choose between "Online Only" and "Local" on a folder-by-folder basis in Finder by right-clicking on a folder



## Dock

- [ ] Finder
- [ ] Firefox
- [ ] Safari
- [ ] Chrome
- [ ] Opera
- [ ] Mail
- [ ] Messages
- [ ] FaceTime
- [ ] Calendar
- [ ] Notes
- [ ] Things
- [ ] Reminders
- [ ] iTerm
- [ ] Sublime Text
- [ ] DiffMerge
- [ ] Transmit
- [ ] Sequel Pro
- [ ] Rested
- [ ] VisualJSON
- [ ] VirtualBox
- [ ] Spotify
- [ ] Alinof TimerPro
- [ ] Adobe Photoshop
- [ ] Adobe Illustrator
- [ ] 1Password
- [ ] System Preferences
- [ ] Applications \(as a folder\)
- [ ] Utilities \(as a folder\)
- [ ] Downloads \(as a folder\)



## Sidebar

- [ ] Desktop
- [ ] Applications
- [ ] Utilities
- [ ] addison
- [ ] git
- [ ] .ssh
- [ ] diff
- [ ] before
- [ ] after
- [ ] Downloads
- [ ] AirDrop
- [ ] Dropbox
- [ ] iCloud Drive
- [ ] Exocortext
- [ ] REDACTED
- [ ] Rundown Creator, Inc.
- [ ] Employees
- [ ] Receipts by ID
- [ ] Receipts by Date
- [ ] Receipts Inbox
- [ ] Checks
- [ ] Addison's Inbox
- [ ] Bradley's Inbox
- [ ] Modified v2
- [ ] Templates
- [ ] Tmp