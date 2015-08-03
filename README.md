TBOPLAYER 0.2
============

A GUI interface using jbaiter's pyomxplayer wrapper to control omxplayer

If you want the simple version of tboplayer please visit https://github.com/KenT2/tboplayer

INSTALLATION
============

Instructions for installation on the official Raspbian image

Install/Update omxplayer
---------------

Ensure you have the latest version of omxplayer by download and install the lastest build here http://omxplayer.sconde.net/
		 
Download and Install pexpect
-----------------------------

This is specified here http://www.noah.org/wiki/pexpect#Download_and_Installation and copied below:

From a terminal window open in your home directory type:

         wget http://pexpect.sourceforge.net/pexpect-2.3.tar.gz
         tar xzf pexpect-2.3.tar.gz
         cd pexpect-2.3
         sudo python ./setup.py install

Download and Install youtube-dl
-----------------------------

This is specified here https://rg3.github.io/youtube-dl/download.html and copied below:

From a terminal window open in your home directory type:

         sudo wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
         sudo chmod a+rx /usr/local/bin/youtube-dl

Download and Install livestreamer
-----------------------------

This is specified here http://docs.livestreamer.io/install.html and copied below:

From a terminal window open in your home directory type:

         sudo apt-get install livestreamer

Download and Install TBOPlayer
------------------------------

From a terminal window open in your home directory type:

         wget https://github.com/popiazaza/tboplayer/tarball/extreme -O - | tar xz

There should now be a directory 'popiazaza-tboplayer-xxxx' in your home directory. Rename the directory to tboplayer

Open the tboplayer directory and from a terminal opened in THIS directory:

		sudo python tboplayer.py

If you want larger player, you can type one of these instead:

		sudo python tboplayer1024x768.py
		sudo python tboplayer1366x768.py
		sudo python tboplayer1920x1080.py

You can request me for more screen resolution, or you can make one for yourself by edit few python code.
Sudo is not require to use tboplayer but omxplayer might use it.
 
 
OPERATION
=========

Buttons
-------

* ADD - duplicates the Track>Add menu item

* ADD URL - duplicates the Track>Add URL menu item

* EDIT - duplicates the Track>Edit menu item

* OPEN/SAVE/CLEAR LIST - duplicates the Playlist>Open,Save,Clear menu item

* PLAY/PAUSE - Play the selected track or pause if playing

* STOP - Stop playing, operational only during playing

* PREVIOUS - Play previous track, operational only after played some track

* NEXT - Play next track, up to mode that you set

* VOL +- - Volume control, operational only during playing

Menus
-----
* Track - add edit or remove a track from the current playlist
 
   * Add Youtube URL - ex. http://www.youtube.com/watch?v=ABC12345, please mind that the regex goes to youtube-dl directly
 
   * Add Livestreamer URL - ex. twitch.tv/esl_csgo, please mind that the regex goes to livestreamer directly

* Playlist - save the current playlist or open a saved one
 
* OMX - display the track information for the last played track (needs to be enabled in options)
 
* Options -

    * Audio Output - play sound to hdmi or local output, auto does not send an audio option to omxplayer.
	
    * Mode - play the Single selected track, Repeat the single track, rotate around the Playlist starting from the selected track, randomly play a track from the Playlist.
	
    * Initial directory for tracks - where Add Track starts looking.
	
    * Initial directory for playlists - where Open Playlist starts looking
	
	* Enable subtitles
	
    * OMX player options - add your own options, read more here https://github.com/popcornmix/omxplayer/blob/master/README.md (no validation so be careful)
	
    * Debug - prints some debug text to the command line
	
    * Generate Track Information - parses the output of omxplayer, disabled by default as it may cause problems with some tracks.

    * Livestreamer Quality - select the quality of livestreamer's stream. Please mind that not all stream have every quality, Add Livestreamer URL will use best quality if you set unaviable quality.

A track is selected using a single click of the mouse or up-down arrow key, playing is started by pressing the Play/Pause button, the . key or the Return key.

Remove the selected track can be done by pressing the Delete key.

During playing of a track a slightly modified set of omxplayer commands can be used from the keyboard but there must be FOCUS on TBOPlayer. A list  of commands is provided in the help menu. Note: some of the commands are not implemented by omxplayer.

If you have problems playing a track try it from the command line with omxplayer -ohdmi file or omxplayer -olocal file
