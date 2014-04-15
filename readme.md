#Read Me

####about
This repo contains the Technic Solder files for HeliosRealms.

Files uploaded to this repo will automatically be reflected to http://files.heliosrealms.com/solder/

#conventions

Solder expects very exact naming conventions and will not work unless everything is as expected.

The basic idea behind adding things to Solder is that Solder will take the exact, versioned .zip file you specify and extract it into the
base modpack folder when Technic does the install.

This means that your versioned ZIP files need to be completely self-contained and need to extract with (and only with) thier parent folder (mods/, configs/ or bin/).

Here is the format of all repo'd items as viewed from the root of this repo

####solder file and folder format
```
	mods/
		[mod-slug]/
			[mod-slug]-v[mod-version].zip
				..[folder]/[actual-mod-name].[jar|zip]
```
To find the [mod-slug] go to the Solder repo site and look at the Mod list

####mods

Wrap all mod JAR files (or ZIPs depending on the mod) inside a 'mods' folder before zipping

####config

Wrap all the config files inside a 'configs' folder before zipping

####jar mods

Put jar mods in a modpack.jar file and put that in a 'bin' folder before zipping

####example
```
	mods/
		reactorcraft/
			reactorcraft-v19b.zip
				..contains mods/reactorcraft-blah.jar	
		tmc-icehenge-configs/
			tmc-icehenge-configs-v1.6.zip
				..contains configs/all the config files
		forgemodloader/
			forgemodloader-v9.11.1.965
				..contains /bin/modpack.jar
```

##adding a new mod to the Solder repo

* Go to Solder -> Mods -> Add Mod and fill out the Mod details
* Make a note of the assigned mod-slug (you will need this)
* In the git repo add a folder with the name of the mod-slug
	* E.g. if you're adding a mod called "My New Mod" the mod slug is likely "my-new-mod"
	* So create the folder REPO/mods/my-new-mod/
* then add the versioned mod zip (follow format above)
* push changes to git
* in Solder, edit the Mod and choose the Versions (tab)
* put the version number in the field and hit add
* if you named something wrong it will not create and MD5 and will error
* if all goes well you should see a new version of your mod in the list of available versions

Remember to add a mod You have to create a 'mods' folder, stuff the mod .jar (or .zip) into the that 'mods' folder
and then zip that 'mods' folder into an archive named after both the mod slug and version (see above)

This can be very tedious for large amounts of new mods. 

If you are on a Mac, download and use the Automator Workflow (see below for instructions)

##adding a new version of an existing mod to the Solder repo

Follow the standard conventions (above) just add the new versioned zip file into the mod-slugged folder

For example to add a new version of ReactorCraft...
* Create a folder named 'mods'
```
	mods/
```
* put the reactorcraft jar file in that 'mods' folder
```
	mods/
		reactorcraft_20.jar
```
* ZIP that mods folder and name it properly
```
	reactorcraft-v20.zip
```
* put that ZIP folder in the REPO/mods/reactorcraft folder
```
	mods/
		reactorcraft/
			reactorcraft-v19b.zip
			reactorcraft-v20.zip
```
* upload to this git repo
* add the version to the list in Solder (remember to put the 'v' as in 'v20' for version number)

# Automator Workflow
Download Automator Workflow in this repo. It can help make this process less painful.

It will automatically wrap whatever MOD you have slected in a 'mods' folder, zip it, and name it according to conventions
