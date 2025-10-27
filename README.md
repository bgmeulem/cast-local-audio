Cast video to a Chromecast using [catt (Cast All The Things)](https://github.com/skorokithakis/catt). Extended to allow for splitting audio and video stream. This is useful if you want to cast to a device, but keep audio playing locally. Local audio can then e.g. be sent separately to a Bluetooth device, or AUX.

It automatically searches for `.srt` subtitle files with the same name, but also supports manually passing them.

## Requirements
[`uv`](https://docs.astral.sh/uv/getting-started/installation/)

## Usage

```bash
$ uv run python main.py -h
usage: main.py [-h] [--reset] [-s SUBTITLES] [-la] [filename]

Cast video to Chromecast using catt (Cast All The Things).
Extended to allow splitting video and audio stream, keeping
audio playing locally. Useful when stream to e.g. a beamer or
tv, but you want the audio to play on headphones or Bluetooth
speakers, connected to the hosting device.

positional arguments:
  filename              Path of a video file.

options:
  -h, --help            show this help message and exit
  --reset               Scan for chromecast devices and reset
                        them.
  -s, --subtitles SUBTITLES
                        Path of a subtitle file (optional).
                        Can be .srt or .vtt. If none passed, I
                        look for a subtitle file with the same
                        name as the video file.
  -la, --local-audio    Play audio on the local device instead
                        of the casting device. Playing audio
                        locally can be useful if you want to
                        send the audio stream to a different
                        device, e.g. via Bluetooth or AUX.
                        Audio is kept in sync with the video.
```
A wrapper shell script is provided so you can alias it to e.g. simply `cast` in your shell config, and invoke it as:

```bash
cast [-h] [--reset] [-s SUBTITLES] [-la] [filename]
```
