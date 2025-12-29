# Bitwig-5.3.13-libcurl-Guide-HY-Plugins-on-Linux-debian-based

	## The Main Command you ececute in the Plugin.so Folder:
	## $ patchelf --replace-needed libcurl-gnutls.so.4 libcurl.so.4 Plugin.so

This is a Solution for HY- Plugin for Bitwig 5.3.13 in Linux (Debian-based)

If you have any Issues with your HY-Plugins try this Solution what is also mentioned
in the Read Me Files inside the Plugin Package.

But there is no detailed Guid, now here it is. (i send this to the Developer as well)

This is tested in MX Linux 23.6 (a debian-based Distribution)

	>System:
	>Kernel  : 6.17.13-1-liquorix-amd64 [6.17-15~mx23ahs] arch: x86_64 bits: 64 compiler: gcc v: 12.2.0
	>Desktop : KDE Plasma v: 5.27.5 tk: Qt v: 5.15.8 wm: kwin_x11 vt: 7 dm: SDDM
	>Distro  : MX-23.6_ahs_x64 Libretto Jan 12 2025 base: Debian GNU/Linux 12 (bookworm)


	>KDE-Plasma-Version     : 5.27.5
	>KDE-Frameworks-Version : 5.103.0
	>Qt-Version             : 5.15.8
	>Grafik-Plattform       : X11
	>Prozessoren            : i5-14600K
	>Speicher               : 62,6 GiB Arbeitsspeicher
	>Grafikprozessor        : NVIDIA GeForce RTX 4070 Ti SUPER/PCIe/SSE2

## The Long Guide:

	__1.__ Download, unpack the HY-Plugin Packages
	__2.__ Drop the Plugin Folder into your HOME Folder  ~/.vst3
	__3.__ Drop the Presets Folder into your HOME Folder ~/.config
	__4.__ Open Bitwig an search for HY if it is listed you are probably fine, if not
	__5.__ Open Setting -> Plugins click on [Show Plugin Errors] (or similar)

<img width="832" height="803" alt="Screenshot_20251228_213420" src="https://github.com/user-attachments/assets/a9d89179-f5c3-4982-b77f-8418088b396f" />

	Here you see the Error.

<img width="825" height="804" alt="Screenshot_20251228_215021" src="https://github.com/user-attachments/assets/ff9b8af9-7366-43af-a2e1-ae12deda78a4" />

	__6.__ Close Bitwig and open Synaptic, 
	check if you have __libcurl4 + libcurl4-gnutls + libcurl4:i386 + patchelf__ installed, 
	if not mark the pakets and install it:

<img width="1715" height="926" alt="Screenshot_20251228_220242" src="https://github.com/user-attachments/assets/d63652b4-cc68-4587-9253-79ee2bba4fc8" />

	__7.__ You are half-done. Now open the Terminal, go to the Path with your ## Plugin.so ## file in .vst3. 
	You can do this via Dolphin "Open Terminal Here" or set the Path manually.
	Attention HY-Plugin-Developer uses Space in Names, you need the "\" after Word and before Space.
	ls= List what is in a Path
	cd= call the Path

### Example

```bash
x@mx:/
$ cd ~/.vst3/HY-POLY\ free\ Linux/HY-POLY\ free.vst3/Contents/x86_64-linux
mx@mx:~/.vst3/HY-POLY free Linux/HY-POLY free.vst3/Contents/x86_64-linux
$ ls
'HY-POLY free.so'
mx@mx:~/.vst3/HY-POLY free Linux/HY-POLY free.vst3/Contents/x86_64-linux
$ patchelf --replace-needed libcurl-gnutls.so.4 libcurl.so.4 HY-POLY\ free.so
```

	__8.__ Restart Bitwig



