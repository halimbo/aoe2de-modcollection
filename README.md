# Audio Modding for Age of Empires II: Definitive Edition

### Finding the correct Identifier for the  `.wem` (for Use in a Mod)

- The sound effect you are looking for might be in StepS's Spreadsheet
- https://docs.google.com/spreadsheets/d/1bczdFQksnbLnjI5zAkw-mSpb9MnnxxEkHDiz1PftIHw/edit

- If you can't find it there you might be able to find it with the AdvancedGenieEditor
- Open the game folder

 ![steam]("Balanced Audio"/scr18.png)

- Open Tools-Builds/AdvancedGenieEditor.exe
- Select "Age of Empires II: Definitive Edition" and hit "Open"

 ![open]("Balanced Audio"/scr19.png)

- Find the ingame unit and then scroll down until you reach the section on sound effects.
- Note: Please ignore the fact that the soundfiles in the Editor show the `.wav` extension, for all our purposes aoe2 sound mods use `.wem` files.
![open]("Balanced Audio"/scr20.png)
 ![open]("Balanced Audio"/scr21.png)
  
### Replacing and/or Muting Sound Effects
- If you want to mute something, all you need is the correct Identifier of the corresponding sound effect and a "stub" audio file (for Use in a Mod).
- The "Original Sounds" Mod from StepS included a "stub" audio file that is only 1kb and empty. (also included in the Mods "Pasture Mute", "Quiet Sound Mod", ...)
- We can use this to overwrite any sound effect by putting it in our mod folder at "resources/_common/drs/sounds" and renaming it as the "identifier.wem" we want


## 🎧 How to EQ In-Game Sound Effects (AOE2:DE)

---

### 🔍 Extracting `.wem` Files from the Game

If you can't get `.wem` files by subscribing to an existing mod, here's how:

- Locate the in-game sound files (In your steam game-folder inside **/wwise**)
  
  ![Game files screenshot](quietsoundmod/scr13.png)

- Download **Ravioli Extractor**  
  [https://www.scampers.org/steve/sms/other.htm#ravioli_download](https://www.scampers.org/steve/sms/other.htm#ravioli_download)

- Use **foobar2000** + **vgmstream plugin** to preview and find the audio you want:  
  [https://vgmstream.org/](https://vgmstream.org/)

  ![vgmstream screenshot](quietsoundmod/scr17.png)  
  ![foobar screenshot](quietsoundmod/scr7.png)
  
### Renaming the extracted files 
⚠️ IMPORTANT NOTICE: The audio files extracted using Ravioli are mislabeled with a .wav extension. However, they are actually .wem files in disguise. For compatibility with the Foobar plugin, these files must be renamed with the correct .wem extension. Below are commands to batch rename all .wav files in the current directory to .wem:
⚠️ WARNING: These commands will irreversibly rename all .wav files in the current directory.
Only proceed if you're certain that the only `.wav` files in your current directory are the ones that were extracted from Ravioli (`.wem` in disguise). Create a backup if needed.
### PowerShell

```Get-ChildItem *.wav | Rename-Item -NewName { $_.Name -replace '\.wav$', '.wem' }```

### Windows CMD

```for %f in (*.wav) do ren "%f" *.wem```

### 🔄 Convert `.wem` to `.wav` (for EQ in Audacity)

- Install **vgmstream command-line tool**

  ![vgmstream folder](quietsoundmod/scr16.png)

- Open the folder in a terminal:

  ![terminal open](quietsoundmod/scr12.png)  
  ![terminal view](quietsoundmod/scr9.png)

- Copy the path of your `.wem` file

  ![copy path](quietsoundmod/scr10.png)

- Use the `-o sound.wav` option to name your output file

  ![output screenshot](quietsoundmod/scr11.png)

---

### 🔁 Convert `.wav` Back to `.wem` (for Use in a Mod)

- Install **Wwise Launcher**
- Create a free account (non-commercial use only)
- Skip all unnecessary plugins during install
- Create a new Wwise project
- Set **Source Encoding** to `"Vorbis High Quality"`

  ![wwise encoding](quietsoundmod/scr1.png)  
  ![wwise settings](quietsoundmod/scr2.png)  
  ![wwise UI](quietsoundmod/scr3.png)

- Import your `.wav` files

  ![upload files](quietsoundmod/scr4.png)  
  ![file list](quietsoundmod/scr5.png)

- Export the files as `.wem`

  ![export screenshot](quietsoundmod/scr6.png)

- By default, Wwise exports these into your `Documents` Windows-Folder in the `.cache` directory of the Project.

- Just as a notice, your aoe2 mods are not stored where the base game is (opening game files through steam), but next to the folder where your Replays are saved (opening the directory of a Mod through the ingame Mod-Settings).
- Now you can test your modded audio file by putting it in your mods folder into **/mods/local/mysoundmod/resources/_common/drs/sounds**

  ***All Credit goes to StepS and the aoe2 mod community***
