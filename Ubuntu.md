# Ubuntu Tips

### Removing SU password

If you're running Ubuntu in a VM behind a DMZ it may be Ok to just remove the password for su.

I do that. But if you really want to do that, you should have to google it and type it all out yourself.

Personally, I've never been raped with Linux in >20 years. So I don't need a password in a private, sandboxed, DMZ'd VM.

I just type what I want and it's faster.

## The Multiverse

These allow Ubuntu to access all the specialised hardware on your device.

This once required using a GUI or an editor. Now, just use a Terminal:

	$ sudo apt-add-repository multiverse && sudo apt-get update
	
## Chrome

Once you install it, type

	$ google-chrome
	
From a terminal, then find it in the launcher, right-click on it and select "Lock to Launcher".


	


