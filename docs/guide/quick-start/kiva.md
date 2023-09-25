<h1>Quick Start - Minimal (Kiva)</h1>

If you want to have less hassle, you can try playing Black MIDI songs with [Kiva](https://github.com/arduano/Kiva), a modern MIDI player à la Piano From Above that is quite fast, configurable, and easy to start, making it a good choice if just want to try some Black MIDI songs. It has roots of Black MIDI, but you sure can play general MIDI songs with it.

![](https://camo.githubusercontent.com/185b2dfc4998218b661b214832ba14adb59e38aa270d5a7cbd547f2890300e7d/68747470733a2f2f692e696d6775722e636f6d2f594430774845312e706e67)

## Get Kiva

Kiva is hosted on GitHub. Go to [its Releases page](https://github.com/arduano/Kiva/releases/latest) and download either the installer or the portable version.

## Get OmniMIDI (optional)

Kiva has its own audio engine that you can use from the get-go for now, but if you still want to, you can try installing OmniMIDI.

OmniMIDI is an established MIDI driver/synthesizer that is built with Black MIDI in mind, but also appropriate for general use for normal MIDI playbacks and DAWs.

You can get the latest version on [the GitHub repository](https://github.com/KeppySoftware/OmniMIDI/releases/latest).

The default configuration should be fine enough. However, should you want to configure it, here's a recommendation. Your milage may vary, so try experimenting later.

1. Engine: Windows Audio Session API (WASAPI) is a nice one, but you can try Audio Stream Input/Output (ASIO) for higher quality sounds, especially if you have FL Studio.
2. Driver voice limit: 1024 is nice, but 128 to 512 is fine for low-ends.
3. Output buffer: You can set it to have a consistent delay and sound on Black MIDI songs. Try doing 100ms.

## Get a soundfont

Kiva (and OmniMIDI if you installed it) requires a soundfont to output a sound.

[The Publico folder of Carlos S. M.](https://drive.google.com/drive/u/0/folders/0B-jbdgbiY_-YMGU1M2dqbkFmUHc) has a collection of soundfonts that you can pick. As a quick recommendation, try [xp50houz](https://drive.google.com/file/d/0B-jbdgbiY_-YR0ZWRzN5bXNpa3M/view?usp=drive_link&resourcekey=0-w4WMweb8O6MG1SI-BTP45g).

After downloading it, open the settings window by clicking the gear icon on the top, click the "Audio" tab, and add the soundfont, either by clicking the plus icon on the right side and follow the instructions or drag the file and drop it on the settings window.

## Play a MIDI song

You can start playing Black MIDI songs now! The internet is wide enough for you to find one. Start on YouTube and search for one. Check the description to see if they provide a download link. After downloading it, press the folder icon on the top-left portion of Kiva and choose the MIDI file, or drag the file and drop it on Kiva.
