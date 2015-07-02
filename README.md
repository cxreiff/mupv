#mupv

###an mpv wrapper for playing audio from an iTunes Library

A bash script that creates a playlist from your iTunes Library and feeds it into mpv (mpv.io).

If given arguments, the first argument filters the playlist by artist, the second filters by album, and the third filters by song. The arguments are wildcarded, so 'mupv A B C' will play audio files by artists beginning with 'A', albums beginning with 'B' (out of those artists), and the songs themselves must begin with 'C'. This assumes your music is organized by iTunes into the normal format of Artist/Album/Song.

####options

There are a few options to pass into mupv (before the arguments):

	( -s ) This tells mpv to shuffle through the playlist.

	( -g ) This option turns on graphics, it will attempt to display any cover art embedded in the audio file.

	( -o ) This option, if used with "-g", turns on the on-screen controller.

	( -f ) This option, if used with "-g", will make the window float on top of other windows.

	( -t ) This option, if used with "-g", will prevent dragging the window around ("HUD" style).

	( -k ) This option will turn off the ability to use the macbook media keys to control mpv.

	( -d ) This option must be followed with an argument, which will be passed into mpv as the --geometry option. See mpv's man pages for details.

	( -m ) This option must be followed with an argument, the string passed in will be used as additional arguments to pass into mpv.

####bugs

Some audio files (including those downloaded from the iTunes Store) claim to have PNG images embedded in them when in truth the images are JPEG. Mpv's current release will print an error to the console every frame in this case, spamming the console, but this bug is fixed in mpv's master branch and will be fixed with the next release. I've filtered the message, but console input is broken when these kinds of files are played.