# Cloning your Voice 



```
conda create --name clone python=3.7
```

```
conda activate clone
```

## Installing pytorch

depending where operative system you are , you choose the correct command

https://pytorch.org/get-started/locally/

If you want to know wich version of CUDA you have

```
C:\Users\rusla>nvcc --version
```

in my case I will use CUDA 11

```
conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c conda-forge
```



```
pip install webrtcvad
```



##  Download Pretrained Models

Pretrained models come as an archive that contains **all three models** (speaker encoder, synthesizer, vocoder). The archive comes with the same directory structure as the repo, and you're expected to merge its contents with the root of the repository.

### [[Download pretrained.zip\]](https://github.com/blue-fish/Real-Time-Voice-Cloning/releases/download/v1.0/pretrained.zip)

Please ensure the files are extracted to these locations within your local copy of the repository:



## Install ffmpeg.

Install [ffmpeg](https://ffmpeg.org/download.html#get-packages).

In windows you download the file

[https://www.gyan.dev/ffmpeg/builds/ffmpeg-git-full.7z](https://translate.google.com/website?sl=it&tl=en&ajax=1&elem=1&se=1&u=https://www.gyan.dev/ffmpeg/builds/ffmpeg-git-full.7z) ". This will allow you to download the installation files of the latest version of FFmpeg for Windows to your computer. The files are stored in a compressed archive.



**Extract the content from the file you just downloaded.** 

- Select the **Extract here** option , then wait for the data decompression process to finish. A new folder will be created which will have the same name as the 7Z format file.

![](../assets/images/posts/README/1a.jpg)

copy the folder and  paste on your "Local Disk (C :)", 

[![Immagine titolata Install FFmpeg on Windows Step 11](https://www.wikihow.com/images/thumb/2/27/Install-FFmpeg-on-Windows-Step-11-Version-2.jpg/v4-728px-Install-FFmpeg-on-Windows-Step-11-Version-2.jpg.webp)](https://www-wikihow-it.translate.goog/Installare-FFmpeg-in-Windows?_x_tr_sl=it&_x_tr_tl=en&_x_tr_hl=en-GB&_x_tr_pto=ajax,elem#/Immagine:Install-FFmpeg-on-Windows-Step-11-Version-2.jpg)

**Click on an empty spot in the right pane of the window with the right mouse button, then choose the \**Paste\** option from the context menu that will appear.** This way the folder you copied will be transferred from the directory where it is currently located to the root of your computer's hard drive.

[![Immagine titolata Install FFmpeg on Windows Step 12](https://www.wikihow.com/images/thumb/0/0e/Install-FFmpeg-on-Windows-Step-12-Version-4.jpg/v4-728px-Install-FFmpeg-on-Windows-Step-12-Version-4.jpg.webp)](https://www-wikihow-it.translate.goog/Installare-FFmpeg-in-Windows?_x_tr_sl=it&_x_tr_tl=en&_x_tr_hl=en-GB&_x_tr_pto=ajax,elem#/Immagine:Install-FFmpeg-on-Windows-Step-12-Version-4.jpg)

**Access the window from which you can manage Windows environment variables.** Follow these instructions:

- Press the **Windows** + **S** key combination to access the Windows search bar;
- Click on the **Edit system-related environment variables** icon that appears in the list of results;
- Click on the **Environment Variables** button displayed in the lower right corner of the window;

[![Immagine titolata Install FFmpeg on Windows Step 13](https://www.wikihow.com/images/thumb/4/4f/Install-FFmpeg-on-Windows-Step-13-Version-4.jpg/v4-728px-Install-FFmpeg-on-Windows-Step-13-Version-4.jpg.webp)](https://www-wikihow-it.translate.goog/Installare-FFmpeg-in-Windows?_x_tr_sl=it&_x_tr_tl=en&_x_tr_hl=en-GB&_x_tr_pto=ajax,elem#/Immagine:Install-FFmpeg-on-Windows-Step-13-Version-4.jpg)

**Select the variable Path listed in the "User Variables for [username]" section, then click the \**Edit\** button .** The list of paths currently assigned to the variable will be displayed.



[![Immagine titolata Install FFmpeg on Windows Step 14](https://www.wikihow.com/images/thumb/e/ea/Install-FFmpeg-on-Windows-Step-14-Version-3.jpg/v4-728px-Install-FFmpeg-on-Windows-Step-14-Version-3.jpg.webp)](https://www-wikihow-it.translate.goog/Installare-FFmpeg-in-Windows?_x_tr_sl=it&_x_tr_tl=en&_x_tr_hl=en-GB&_x_tr_pto=ajax,elem#/Immagine:Install-FFmpeg-on-Windows-Step-14-Version-3.jpg)



**Add the path of the "FFmpeg" directory to the "Path" variable.** 

- Click on the **New** button to insert a new line of text after the last one in the list;
- Enter the path C:\ffmpeg\bin. If you have pasted the "FFmpeg" folder into a different memory drive or folder, you will need to replace the path indicated with the specific one in your case (remember to add the string "\ bin" at the end);
- Click on the **OK** button . At this point, the complete path of the "FFmpeg" folder will be present as the last value of the "Path" variable.

[![Immagine titolata Install FFmpeg on Windows Step 15](https://www.wikihow.com/images/thumb/f/f5/Install-FFmpeg-on-Windows-Step-15-Version-3.jpg/v4-728px-Install-FFmpeg-on-Windows-Step-15-Version-3.jpg.webp)](https://www-wikihow-it.translate.goog/Installare-FFmpeg-in-Windows?_x_tr_sl=it&_x_tr_tl=en&_x_tr_hl=en-GB&_x_tr_pto=ajax,elem#/Immagine:Install-FFmpeg-on-Windows-Step-15-Version-3.jpg)

**Click on the \**OK\** button to save the changes.**

 At this point the installation of FFmpeg and the configuration of the system variables is complete.

 To ensure that FFmpeg is working properly, open a window of the "Command Prompt" and run the command to display on screen the program version number: 

```
ffmpeg -version
```

```
libavutil      57.  4.101 / 57.  4.101
libavcodec     59.  5.100 / 59.  5.100
libavformat    59.  4.101 / 59.  4.101
libavdevice    59.  0.101 / 59.  0.101
libavfilter     8.  2.100 /  8.  2.100
libswscale      6.  0.100 /  6.  0.100
libswresample   4.  0.100 /  4.  0.100
libpostproc    56.  0.100 / 56.  0.100
```

### Test Configuration

Before you download any dataset, you can begin by testing your configuration with:

```
python demo_cli.py
```

If all tests pass, you're good to go.

### (Optional) Download Datasets

For playing with the toolbox alone, I only recommend downloading [`LibriSpeech/train-clean-100`](https://www.openslr.org/resources/12/train-clean-100.tar.gz). Extract the contents as `<datasets_root>/LibriSpeech/train-clean-100` where `<datasets_root>` is a directory of your choosing. Other datasets are supported in the toolbox, see [here](https://github.com/CorentinJ/Real-Time-Voice-Cloning/wiki/Training#datasets). You're free not to download any dataset, but then you will need your own data as audio files or you will have to record it with the toolbox.

###  Launch the Toolbox

You can then try the toolbox:

```
python demo_toolbox.py -d <datasets_root>`
or
`python demo_toolbox.py
```

depending on whether you downloaded any datasets. 

