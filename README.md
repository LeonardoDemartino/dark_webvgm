# dark_webvgm
A mod of webVGM by Juergen Wothke


Hello, Delek here! :)

I did some changes in the code of webVGM by Juergen Wothke for personal use.
But maybe you will like this changes too so I decided to share this “fork”, the news are:

1) It works completely offline.
2) The drag & drop is more intuitive (you can drag and drop anywhere in the window)
3) The spectrum is on the middle and without the strange “isometric” view.
4) Dark look.
5) The legends of the song being played is:
	GAMENAME (SYSTEM) 
	Author - Song Title
6) Vgm files loops infinite times instead of 2.
7) Uses more CPU for the spectrum and the bars are different so it looks nice and fast.
8) I added my favorite songs from Arcade machines in music folder. You’re welcome <3
9) I don’t remember.

How to use:
1) Open player.html on a web browser
2) Drag and drop vgm/vgz files to the window.

Todo:
1) Equalizer?
2) Mute per channel?
3) Make it an App? (Chrome app?)

Regards, Delek.

Leonardo Demartino
delek.net

WARNING: New Google Chrome builds have disabled the auto play feature of audio, so you have to re-enable it for this to work properly with chrome://flags/#autoplay-policy


Original readme file:

/*
* webVGM
* =======
*
* 	Copyright (C) 2015 Juergen Wothke
*
* Based on original C code of vgmPlay (see http://vgmrips.net/forum/viewtopic.php?t=112).
*
* LICENSE
*
* This library is free software; you can redistribute it and/or modify it
* under the terms of the GNU Lesser General Public License as published by
* the Free Software Foundation; either version 2.1 of the License, or (at
* your option) any later version. This library is distributed in the hope
* that it will be useful, but WITHOUT ANY WARRANTY; without even the implied
* warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
* GNU Lesser General Public License for more details.
*
* You should have received a copy of the GNU Lesser General Public
* License along with this library; if not, write to the Free Software
* Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301 USA
*/

This is a JavaScript/WebAudio plugin of vgmPlay. This plugin is designed to work with version 1.0 of my 
generic WebAudio ScriptProcessor music player (see separate project). 

It allows to play various Arcade and Console game music files (see VGMPlay.txt for more details)  - formats like: Video Game Music Files (*.vgm, *.vgz), Creative Music Files (*.cmf), DosBox RAW OPL Log Files (*.dro) - directly in some WebAudio enabled web browser. The plugin does not support archives but only individual music files. (Respective music files can be found on pages like these: http://vgmrips.net/packs/, http://www.smspower.org/Music/VGMs, etc)

A live demo of this program can be found here: http://www.wothke.ch/webvgm/

The project is based on version vgmPlay0.40.5. It includes most of the original code including the 3rd party dependencies. All the "Web" specific additions (i.e. the whole point of this project) are contained in the "emscripten" subfolder. The main interface between the JavaScript/WebAudio world and the original C code is the adapter.c file. Some patches were necessary within the original codebase (these can be located by looking for EMSCRIPTEN if-defs).



Howto build:

You'll need Emscripten (I used the win installer on WinXP: emsdk-1.13.0-full-32bit.exe which could be found here: 
http://kripken.github.io/emscripten-site/docs/getting_started/downloads.html) I did not need to perform 
ANY additions or manual changes on the installation. The below instructions assume that the web project 
folder has been moved into the main emscripten folder (maybe not necessary) and that a command prompt has been 
opened within the vgmPlay0.40.5/emscripten sub-folder, and that the Emscripten environment vars have been set (run emsdk_env.bat).

Running the makeEmscripten.bat will generate a JavaScript 'vgmPlay0.40.5' library (vgmPlay.js) including the above mentioned 
interface APIs. This lib is directly written into the web-page example in the "htdocs" sub-folder. (This generated lib is 
used from some manually written JavaScript/WebAudio code, see htdocs/sample_player.js). Study the example in "htdocs" 
for how the player is used (Notice: In order to play "YMF278B (OPL4)" files you'll need a sample ROM, called yrw801.rom - which 
you should place in the "htdocs" folder.). This project comes without any music files, so you'll have to get your own and place them
in the htdocs/music folder (you'll also have to configure them in the 'songs' list in index.html).

