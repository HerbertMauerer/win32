---
title: Stopping, Pausing, and Restarting Playback
description: Stopping, Pausing, and Restarting Playback
ms.assetid: 39751342-63bc-4e68-bf9e-38665db8a05c
keywords:
- waveform audio,stopping playback
- waveform-audio interface,stopping playback
- playing waveform-audio files,stopping playback
- waveform audio,pausing playback
- waveform-audio interface,pausing playback
- playing waveform-audio files,pausing playback
- waveform audio,restarting playback
- waveform-audio interface,restarting playback
- playing waveform-audio files,restarting playback
- waveOutPause function
- waveOutReset function
- waveOutRestart function
- stopping waveform-audio playback
- pausing waveform-audio playback
- restarting waveform-audio playback
ms.topic: article
ms.date: 05/31/2018
---

# Stopping, Pausing, and Restarting Playback

You can stop or pause playback while waveform audio is playing. After playback has been paused, you can restart it. Windows provides the following functions for controlling waveform-audio playback.



| Function                                 | Description                                                                                 |
|------------------------------------------|---------------------------------------------------------------------------------------------|
| [**waveOutPause**](https://msdn.microsoft.com/en-us/library/Dd743867(v=VS.85).aspx)     | Pauses playback on a waveform-audio output device.                                          |
| [**waveOutReset**](https://msdn.microsoft.com/en-us/library/Dd743870(v=VS.85).aspx)     | Stops playback on a waveform-audio output device and marks all pending data blocks as done. |
| [**waveOutRestart**](https://msdn.microsoft.com/en-us/library/Dd743871(v=VS.85).aspx) | Resumes playback on a paused waveform-audio output device.                                  |



 

Pausing a waveform-audio device by using [**waveOutPause**](https://msdn.microsoft.com/en-us/library/Dd743867(v=VS.85).aspx) might not be instantaneous; the driver may finish playing the current block before pausing playback.

Generally, as soon as the first waveform-audio data block is sent by using the [**waveOutWrite**](https://msdn.microsoft.com/en-us/library/Dd743876(v=VS.85).aspx) function, the waveform-audio device begins playing. If you do not want the sound to start playing immediately, call **waveOutPause** before calling **waveOutWrite**. Then, when you want to begin playing waveform-audio data, call [**waveOutRestart**](https://msdn.microsoft.com/en-us/library/Dd743871(v=VS.85).aspx).

You cannot use **waveOutRestart** to restart a device that has been stopped with [**waveOutReset**](https://msdn.microsoft.com/en-us/library/Dd743870(v=VS.85).aspx); you must use **waveOutWrite** to send the first data block to resume playback on the device.

 

 




