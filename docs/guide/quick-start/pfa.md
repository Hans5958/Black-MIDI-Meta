<h1>Quick Start - Classic (PFA)</h1>

As a classic choice, Piano From Above (PFA) is a MIDI player à la Synthesia. It is lightweight, portable, and also free. It has been used by the community since the early days, and still being used as a baseline for legit runs till this day.

This would take some time to configure so it can be used effectively. If you don't have much time, [try using Kiva instead](quick-start-kiva.md).

[![](https://i.ytimg.com/vi/LFnqZiH7aIk/maxresdefault.jpg)](https://www.youtube.com/watch?v=LFnqZiH7aIk&list=PLyy0nazZT2T6x2OYjQyLhJOzC1VA2qzh1)

## Get Piano From Above

Few years ago, PFA has its own website. Nowadays you can just go to [the GitHub repository](https://github.com/brian-pantano/PianoFromAbove) and download it for there.

Go to [its Releases page](https://github.com/brian-pantano/PianoFromAbove/releases/latest) to download it. Depending on your PC architecture, you should get the correct one.

## Get OmniMIDI

OmniMIDI is an established MIDI driver/synthesizer that is built with Black MIDI in mind, but also appropriate for general use for normal MIDI playbacks and DAWs.

You can get the latest version on [the GitHub repository](https://github.com/KeppySoftware/OmniMIDI/releases/latest).

The default configuration should be fine enough. However, should you want to configure it, here's a recommendation. Your milage may vary, so try experimenting later.

1. Engine: Windows Audio Session API (WASAPI) is a nice one, but you can try Audio Stream Input/Output (ASIO) for higher quality sounds, especially if you have FL Studio.
2. Driver voice limit: 1024 is nice, but 128 to 512 is fine for low-ends.
3. Output buffer: You can set it to have a consistent delay and sound on Black MIDI songs. Try doing 100ms.

## Get a soundfont

OmniMIDI requires a soundfont to output a sound. 

[The Publico folder of Carlos S. M.](https://drive.google.com/drive/u/0/folders/0B-jbdgbiY_-YMGU1M2dqbkFmUHc) has a collection of soundfonts that you can pick. As a quick recommendation, try [xp50houz](https://drive.google.com/file/d/0B-jbdgbiY_-YR0ZWRzN5bXNpa3M/view?usp=drive_link&resourcekey=0-w4WMweb8O6MG1SI-BTP45g).

After downloading it, open OmniMIDI, navigate to the "Lists editor" tab, and add the soundfont, either by clicking the plus icon on the right side and follow the instructions or drag the file and drop it on the list.

## Configure Piano From Above

You can now open Piano From Above and configure it. Choose the appropriate MIDI output device, the track colors, etc. For further configuration such as showing 128 keys or the FPS display, try using [Piano From Above: Configurator from KaleidonKep99](https://github.com/KaleidonKep99/PianoFromAboveConfigurator).

### Patch using WinMMWRP

Starting on Windows 8, the performance when playing with MIDI is decreased due to the OS functions. In OmniMIDI, there is a patch called "Windows Multimedia Wrapper" that solves this issue.

Open OmniMIDI, press "Extensions > Windows Multimedia Wrapper", and use the "Standard performance improvement patch (BM)" for Piano From Above. You can also patch other apps, preferably using the other patch for DAWs like FL Studio.

## Play a MIDI song

You can now start playing Black MIDI songs now! The internet is wide enough for you to find one. Start on YouTube and search for one. Check the description to see if they provide a download link. After downloading it, press "File > Pratice Song..." and choose the MIDI file.