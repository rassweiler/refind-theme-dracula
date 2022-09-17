# rEFInd theme Dracula
[![Script Static Analysis](https://github.com/rassweiler/refind-theme-dracula/actions/workflows/test.yml/badge.svg)](https://github.com/rassweiler/refind-theme-dracula/actions/workflows/test.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-informational.svg)](https://github.com/rassweiler/refind-theme-dracula/blob/master/LICENSE) [![AUR version](https://img.shields.io/aur/version/refind-theme-dracula?label=AUR)](https://aur.archlinux.org/packages/refind-theme-dracula/)

Simple [rEFInd](http://www.rodsbooks.com/refind/) theme inspired by the [Dracula](https://draculatheme.com) palette.

![refind theme dracula](samples/refind-theme-dracula.png)

This theme is derived from icons from other source; see [COPYING](https://github.com/rassweiler/refind-theme-dracula/blob/master/COPYING) for details.

## Installation

### UNIX General

On UNIX-like platforms simply open a terminal and enter:

```bash
curl -sL https://raw.githubusercontent.com/rassweiler/refind-theme-dracula/master/install.sh | bash
```

### UNIX Manual:

1. Download lastest release
	```bash
	curl -sL https://github.com/rassweiler/refind-theme-dracula/releases/download/1.0.0/refind-theme-dracula-1.0.0.tar.gz | tar xvz
	```
	```bash
	cd refind-theme-dracula-1.0.0
	```
2. Identify your `EFI` partition and inside it your `refind` directory. For example: `/efi/EFI/refind`
	```bash
	tree -L 3 /efi	
	```
	It results in:
	```bash
	/efi
	└── EFI
		└── refind
			├── fonts
			├── icons
			├── refind.conf
			├── refind_x64.efi
			└── vars
	```
  
3. Create the directory `/efi/EFI/refind/themes/dracula` and copy files to it. You need root permissions
	```bash
	sudo mkdir -p /efi/EFI/refind/themes/dracula
	```

	```bash
	sudo cp -r {icons,theme.conf,*.png} $_
	```

4. Includes Dracula theme in `/efi/EFI/refind/refind.conf`
	```bash
	sudo sed "s/^include/#include/g" -i /efi/EFI/refind/refind.conf
	```

	```bash
	echo "include themes/dracula/theme.conf" | sudo tee -a /efi/EFI/refind/refind.conf
	```

### Arch Linux AUR

From AUR repository:
```bash
git clone https://aur.archlinux.org/refind-theme-dracula.git
cd refind-theme-dracula
makepkg -si
```

Using AUR helper as PARU:
```bash
paru -S refind-theme-dracula
```

### Arch Linux Manual

1. Download lastest release
	```bash
	curl -sL https://github.com/rassweiler/refind-theme-dracula/releases/download/1.0.0/refind-theme-dracula-1.0.0.tar.gz | tar xvz
	```
	```bash
	cd refind-theme-dracula-1.0.0
	```
2. Identify your `EFI` partition and inside it your `refind` directory. For example: `/boot/EFI/refind`
	```bash
	tree -L 3 /boot	
	```
	It results in:
	```bash
	/boot
	└── EFI
		└── refind
			├── fonts
			├── icons
			├── refind.conf
			├── refind_x64.efi
			└── vars
	```
  
3. Create the directory `/boot/EFI/refind/themes/dracula` and copy files to it. You need root permissions
	```bash
	sudo mkdir -p /boot/EFI/refind/themes/dracula
	```

	```bash
	sudo cp -r {icons,theme.conf,*.png} $_
	```

4. Includes Dracula theme in `/boot/EFI/refind/refind.conf`
	```bash
	sudo sed "s/^include/#include/g" -i /boot/EFI/refind/refind.conf
	```

	```bash
	echo "include themes/dracula/theme.conf" | sudo tee -a /boot/EFI/refind/refind.conf
	```

### TODO

- [X] Add [Dracula](https://draculatheme.com/contribute) palette
- [ ] Setup dracula colours on certain os icons
