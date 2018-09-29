# Ubuntu Touch sounds

This repository contains the ringtones and notification tones included with Ubuntu Touch. It was previously hosted [on Launchpad](https://launchpad.net/ubuntu/+source/ubuntu-touch-sounds).

## Adding sounds

Add sounds by placing them in the appropriate directory, [share/sounds/ubports/notifications](share/sounds/ubports/notifications) for notification sounds or [share/sounds/ubports/ringtones](share/sounds/ubports/ringtones) for ringtones. Please listen to the different sounds in this repository and ensure that your sound meets roughly the same audio levels, to avoid giving users some very loud and some very quiet sounds.

Files must be in Vorbis encoding with the extension `.ogg`. Also add the license of the file to [debian/copyright](debian/copyright) (please keep the file in alphabetical order by file name/path). Files must be licensed under the Creative Commons-Attribution-ShareAlike 3.0 (CC-BY-SA 3.0) license. A newer version of the CC-BY-SA license may be used. A more permissive license than CC-BY-SA 3.0 may be used. A less permissive license may not be used.

If you need all the details, the files in this repository are all 44100 Hz sample rate Vorbis files. They have a variable but nominal 499.821000kb/s bitrate, except for `Alarm clock.ogg` and `Alarm synth.ogg`, which are variable but nominal 256kb/s.

## Removing sounds

There is currently no way to safely remove a sound from this package. Sounds which are used for notifications or ringtones have a hard path stored to them in the user's `gsettings` storage. Similarly, the alarms system and other custom alerts hard-code their paths in their own settings. For that reason, this package contains symlinks from `share/sounds/ubports/*` to `share/sounds/ubuntu/`. See [ubports/ubuntu-touch#892](https://github.com/ubports/ubuntu-touch/issues/892) for more information.

## Setting new default sounds

Default ringtones and notification tones are set in the gsettings schema `com.ubuntu.touch.sound`. These can be found in the [ubports/gsettings-ubuntu-touch-schemas](https://github.com/ubports/gsettings-ubuntu-touch-schemas) repository.

## License

See the [debian/copyright](debian/copyright) file for license information for each sound.
