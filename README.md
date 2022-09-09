# HP BIOS Config and Password Reset

This is not a definitive "how-to" however I believe this is what you can use to reset the HP BIOS password.

**Most of this is largely untested!**

**PLEASE PROVIDE FEEDBACK AND UPDATE THIS README**

You will need to be able to boot into Windows to use this tool.

In theory, it is possible to boot into [WinPE](https://docs.microsoft.com/en-us/windows-hardware/manufacture/desktop/winpe-intro?view=windows-11) USB.

If the BIOS is password protected you won't be able to change the boot order. Usually, if the BIOS does not find a bootable hard drive it will look for bootable USB's. So, you can either remove, replace (with blank) or zero-out the current hard drive or storage device. This may cause the BIOS to then search for other bootable devices such as a USB.

If you can already boot into Windows then you are good to go!

## Install BIOS Configurator

Run the exe file which will install the configurator into `C:\Program Files (x86)\hp` directory however if you have a USB you might be able to install onto that.

## Reset BIOS Password

```powershell
BiosConfigUtility64.exe /npwdfile:""
```

## Update BIOS Settings

Get the current config:

```powershell
BiosConfigUtility64.exe /getconfig:config.txt

```

Edit config.txt file and reload config:

```powershell
BiosConfigUtility64.exe /setconfig:config.txt
```

## Compatibility

The pdf is copyright 2012 to 2021. I'm guessing this utility might work on BIOS chips during this time however this whole thing is untested by myself. I have actually zero clue how well any of this works. Feedback would be much appreciated!

## Disclaimer

I do not claim ownership for any of the files in this repository as my own except this README. I supply these files for historical purposes. What you choose to do with them is by your own accord. I make no claims as to the outcome or functionality of this program. I have not modified the program or documentation in any way. USE AT YOUR OWN RISK. NO GUARANTEES OR WARRANTIES.