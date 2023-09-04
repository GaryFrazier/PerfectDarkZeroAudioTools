
# Perfect Dark Zero Audio Tools

A collection of tools to extract, and replace Perfect Dark Zero's audio assets from the Xbox 360 files, all in one place.

## Prerequisites

Download the tools from the Releases page on the right

Have your Perfect Dark Zero Disc image extracted (via this tool https://digiex.net/threads/xbox-360-xiso-extract-best-an-easiest-xdg3-extraction-tool-with-gui-ftp.9711/)

Backup any files you plan to replace or you risk losing them!

Unzip the tools.rar archive.

## Extraction

Audio files are located in the ASSETS/AUDIO folder, they are packed into the .xwb files.

There are two possible extraction methods that could occur. We can use the ToWav tool to extract any non - xma audio files from the .xwb files, however, sometimes this extracts only some, or none of the files. if you only see some of the expected sound files, you will need to also use the second method to get the skipped files. The second method uses the ABX tool in the abx folder to extract .xma audio files. This should grab everything.
More details below.

### ToWav

In the towav folder, paste your .xwb file in the folder, and double click "ConvAll.bat". This will extract the .wav files. If you don't see all of the files expected (as indicated if there is a skip in the file number name), then use the abx tool to get the rest.

### ABX

In the ABX foler, paste your .xwb file in the same directory. Open the EkszBox-ABX.exe program, and load the .xwb. Click the save icon, and it will extract the audio files as .xma's. To convert these into listenable formats, we will open them in Audacity (https://www.audacityteam.org/).

In Audacity, select File->Import->Raw Data, and import a .xma. You may need to play around with the import settings to get it sounding correct. Then, export as .wav, and you have a playable wav file.


## Replacing Audio files

If you wish to replace an audio file, you must replace the entire .xwb. To do this, you must first extract your .xwb, and take note of all of the files in the .xwb, and the order that they are in.

You must get all files in .wav format, so if you needed to get some files as .xma, then you must use Audacity to convert them.

Replace the .wav files of your choosing in the list.

Now that we have all of the wav's we wish to pack, we must repack them using Xact2

### Xact2

Perfect Dark Zero packed audio files using Direct X (Oct 2005)'s version of Xact, so I bundled that in the tools. HOWEVER, it was a pre release and such had an expiration date on the program. We can get around that though.

Change your system's date to any date in the year 2003, then open Xact2.exe (maybe as administrator) in the DirectXOct2005 folder. Once it is open, you can revert your computers date back.

Here is where things can get tricky, my method may not work for all files, open an issue or play around with the settings if the following settings don't work.

Do these steps for each xwb

File -> New Project, name it whatever you want

View -> Xbox 360 properties, this sets output to xbox

Right click compression presets, create new

Right click wave banks, create new.

Under the properties of the wav bank set these values:
SyncWaveData: True
Name: The name of your xwb minus the .xwb (ex. music_lv01)
Streaming: True (probably true for all, but could be a setting you tinker with if doesnt work)
FriendlyNames: False
Compression Preset: The preset you just created
XboxBuildName: The name of the xwb WITH the .xwb extension (ex. music_lv01.xwb)
XboxBuildPath: Wherever you want the new xwb to be saved, preferably in some temporary folder

Now we add the wav files by right clicking your wav bank, insert wav files.

MAKE SURE YOU INSERT ALL FILES THAT WERE IN THE ORIGINAL XWB AND IN THE SAME ORDER.

Of course you put your replacement wav file in place of the original you were trying to replace.

File -> build

Place the new xwb and overwrite the original xwb in the ASSETS/AUDIO folder

Boot up your game however you deem fit, hopefully it doesn't crash. Like I said, the files can come in many formats and may require tinkering. These tools are here to help ease some of the pain, it is not guaranteed to work.
