# aoe2de-modcollection

## 🎧 How to EQ In-Game Sound Effects (AOE2:DE)

---

### 🔍 Extracting `.wem` Files from the Game

If you can't get `.wem` files by subscribing to an existing mod, here's how:

- Locate the in-game sound files manually.
  
  ![Game files screenshot](quietsoundmod/scr13.png)

- Download **Ravioli Extractor**  
  [https://www.scampers.org/steve/sms/other.htm#ravioli_download](https://www.scampers.org/steve/sms/other.htm#ravioli_download)

- Use **foobar2000** + **vgmstream plugin** to preview and extract the audio:  
  [https://vgmstream.org/](https://vgmstream.org/)

  ![vgmstream screenshot](quietsoundmod/scr17.png)  
  ![foobar screenshot](quietsoundmod/scr7.png)

---

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
