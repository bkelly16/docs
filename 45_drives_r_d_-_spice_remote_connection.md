### SPICE CONNECTION

Default spice connection password is 120 seconds. Seem you can set a expiration using 

	
	spice.set_ticket `<password>` [expiration=`<seconds>` [,connected=keep|disconnect|fail]
	
	 Set the spice connection ticket (one time password), with expiration and behavior when
	 already connected. An empty password prevents any connection. A zero value for expiration
	 means the password never expires.


Issue is where to set this using ovirt 

refs:

*  https://www.spice-space.org/docs/spice_user_manual.pdf

*  https://www.redhat.com/archives/libvirt-users/2015-February/msg00055.html

----

Console connection file created by ovirt UI set a password expiry by default of 120s.

By removing "passwdValidTo=" option in the "spice" entry of the VM XML file, it should disable password expiry. This is untested as of yet however.

Would first need to wrote a hook to remove the option to the XML file.

Confident this will work as the libvert XML format docs, implies that no expiry is the default. See [SPICE](https///libvirt.org/formatdomain.html#elementsGraphics)

	
	spice
	...
	 It is possible to set a limit on the validity of the password by giving an timestamp passwdValidTo='2010-04-09T15:51:00' assumed to be in UTC.
	...


Here is a python VDSM hook someone wrote for altering SPICE options : https://github.com/humblec/vdsm-hooks/tree/master/spiceoptions


