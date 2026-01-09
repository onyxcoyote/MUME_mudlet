# MUME_mudlet
Mudlet packages and information for MUME

## Packages

### ShmeepMUMEsounds - https://github.com/onyxcoyote/MUME_mudlet/releases/tag/ShmeepMUMEsounds%2Fv0.4
	Description
		- Room-based ambience and sound effects for MUME, approx 450MB. All sound files are public domain CC0.
		- Ambience - fairly comprehensive coverage for all rooms
		- Sound Effects - some SFX, but there is still a need for many more/improved sound effects.
		- A sound should play when you log in to MUME. Volume can be adjusted.
		- 'sms help' to see commands.

	How to Install
		1. Open mudlet
		2. Open MUME profile (either connect or offline)
		3. Drag the mpackage file into mudlet
			OR use [Toolbox > Package Manager]
		4. Wait 5 seconds, then done.

	Updating Versions
		1. Old version would need to be uninstalled first through [Toolbox > Package Manager], then
		2. Same as install instructions.

	Compatibility
		Windows
		--------
		* YES - Should work with no additional dependencies.

		Linux
		--------
		* EASY - Works on mudlet snap (beta),
		* HARD - install from source should work, though I didn't test it, it would need gstreamer libraries
			e.g. gstreamer install for debian
				sudo apt install \
				gstreamer1.0-tools \
				gstreamer1.0-plugins-base gstreamer1.0-plugins-good \
				gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly \
				gstreamer1.0-libava gstreamer1.0-alsa
		* DOES NOT work on the mudlet AppImage.
			Mudlet needs gstreamer to use sounds on linux, but Mudlet.AppImage does not have gstreamer and can't use the OS gstreamer (even if it is installed)

	Troubleshooting
		If no sound is heard:
		* check that volume isn't too low (e.g. you could try: 'sms volume 80'). The loudness of different speakers varies significantly, e.g. laptop speakers are generally much quieter than OTE headphones.
		* check that mudlet can play any sound file (i.e. linux - could be gstreamer issue), e.g.
			lua playSoundFile({name=getMudletHomeDir() .. "/ShmeepMUMEsounds/soundResources/sfx/pleasing-bell.wav"})
		* check that file path is correct/file exists
			lua display(getMudletHomeDir() .. "/ShmeepMUMEsounds/soundResources/sfx/pleasing-bell.wav")
		* run mudlet through console and check command line output for errors
