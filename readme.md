# Audio codecs comparsion

- FLAC (flac v1.5.0): Downloaded from it's [website](xiph.org/flac/download.html)
- MP3 (lame 3.100.1): Downloaded from it's [RareWares](www.rarewares.org/mp3-lame-bundle.php)
- APE (mac 11.08): Downloaded from it's [website](www.monkeysaudio.com/download.html)
- Wavpack (wavpack 5.8.0): Downloaded from it's [website](http://www.wavpack.com/downloads.html)
- TAK (takc 2.3.0): Downloaded from it's [website](thbeck.de/Tak/Tak.html)
- TTA (tta 2.3): Downloaded from it's [SourceForge](sourceforge.net/projects/tta/files/tta/ttaenc-win/)
- WMA (WmaEncoder 0.2.9c): Downloaded from [Hydrogenaudio Forum](hydrogenaud.io/index.php/topic,90519.0.html)
- lossyWAV (lossyWAV 1.4.2): Downloaded from [Hydrogenaudio Forum](hydrogenaud.io/index.php/topic,112649)
  - lossyFLAC = lossyWAV + FLAC;
  - lossyTAK = lossyWAV + TAK;
  - lossyWV = lossyWAV + Wavpack
- ALAC (refalac v2.84): Downloaded from it's [GitHub](github.com/nu774/qaac/releases)
- OptimFrog (ofc & ofs v5.100): Downloaded from it's [website](losslessaudio.org/Downloads.php)
- Opus (opusenc & opusdec 1.3): Downloaded from it's [website](opus-codec.org/downloads/)
- Ogg Vorbis (oggenc 2.88): Downloaded from [RareWares](www.rarewares.org/ogg-oggenc.php)
- AAC (NeroAac v1.5.1): Downloaded from [WebArchive](web.archive.org/web/20160923100008/http://ftp6.nero.com/tools/NeroAACCodec-1.5.1.zip)
- Musepack (mpcenc 1.30.0 & mpcdec 1.0.0): Downloaded from it's [website](musepack.net/index.php?pg=win)

For missing encoder or decoder, `ffmpeg` (nonfree static [build](github.com/AnimMouse/ffmpeg-autobuild/releases) of `bf327ac` from `2025-04-13 12:35`) is used. Not stored in archive since it has nonfree parts compiled in so it isn't legally redistributable.

# Run your own benchmark
The script can run regardless of your OS, but the preset codecs parameters and included binaries are for Windows. You will need Python 3 and following libraries installed to run the benchmark.
- `numpy`
- `scipy`
- `librosa`
- `matplotlib`

In order to run the benchmark, you have to
1. Copy binaries to `./codecs`. Use archived versions or download other needed.
2. Change the audio sources in the `test.py`
3. Change codec list and settigns in the `test.py`
4. Then execute `python test.py`

There are several things you can customize in test.py
- Change codecs parameters by change `lossless_codecs` and `lossy_codecs` dictionaries.
- Add your test audio files in `files` list.

# Results

## Criteria
- *Compression Ratio (CR)*: compressed file size / original uncompressed file size (lower the better)
- *Average Bitrate*: compression ratio times original bitrate
- *Spectrogram Error*: direct difference between power spectrograms (lower the better)
- *Weighted Spectrogram Error*: direct difference between A-weighted power spectrograms (lower the better)
- *Signal-to-Noise Ratio (SNR)*: noise is calculated from signal power difference (higher the better)
- *Weighted SNR*: noise is calculated from A-weighted signal power difference (higher the better)

When calculating the compressed file size for hybrid lossless audio codec (like `wavpack -c -b192`), the size of both compressed audio and correction file are counted in lossless charts, while only the size of compressed audio is counted in lossy charts.

> Note that not all results are shown in the plots since they will make the figure looks messy. Only best results in a series of codecs are plotted. For example in *encoding time - average bitrate* figure, only left-bottom data points are shown for an audio codec. For codec parameters in the figure, there's a *Full Charts* section below figures for each audio file. For complete results with numbers, please refer to [result.json](./result.json) or [result.md](./result.md)

## NOTICE

Currently not tested with newer codec versions on own hardware. Images are now from origin.

## PLight - Bass_tek 2 (*Genre: Hardcore*)

- **Audio Spectrogram**

![Spectrogram](figs/PLight_-_Bass_tek_2.wav.jpg)

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/PLight_-_Bass_tek_2.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/PLight_-_Bass_tek_2.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/PLight_-_Bass_tek_2.wav.lossy_err.jpg)

<details>
<summary> Full Charts </summary>

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/PLight_-_Bass_tek_2.full.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/PLight_-_Bass_tek_2.full.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/PLight_-_Bass_tek_2.full.wav.lossy_err.jpg)

</details>


## 久石让 - あの夏へ (*Genre: Acoustic*)

- **Audio Spectrogram**

![Spectrogram](figs/久石让_-_あの夏へ.wav.jpg)

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/久石让_-_あの夏へ.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/久石让_-_あの夏へ.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/久石让_-_あの夏へ.wav.lossy_err.jpg)

<details>
<summary> Full Charts </summary>

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/久石让_-_あの夏へ.full.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/久石让_-_あの夏へ.full.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/久石让_-_あの夏へ.full.wav.lossy_err.jpg)

</details>


## Aimer - Ref:rain (*Genre: Pop*)

- **Audio Spectrogram**

![Spectrogram](figs/Aimer_-_Ref_rain.wav.jpg)

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/Aimer_-_Ref_rain.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/Aimer_-_Ref_rain.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/Aimer_-_Ref_rain.wav.lossy_err.jpg)

<details>
<summary> Full Charts </summary>

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/Aimer_-_Ref_rain.full.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/Aimer_-_Ref_rain.full.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/Aimer_-_Ref_rain.full.wav.lossy_err.jpg)

</details>


## John Powell & Hans Zimmer - Hero (*Genre: Soundtrack*)

- **Audio Spectrogram**

![Spectrogram](figs/John_Powell_&_Hans_Zimmer_-_Hero.wav.jpg)

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/John_Powell_&_Hans_Zimmer_-_Hero.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/John_Powell_&_Hans_Zimmer_-_Hero.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/John_Powell_&_Hans_Zimmer_-_Hero.wav.lossy_err.jpg)

<details>
<summary> Full Charts </summary>

- **Lossless Codecs Performance Comparison**

![Lossless codecs comparison](figs/John_Powell_&_Hans_Zimmer_-_Hero.full.wav.lossless.jpg)

- **Lossy Codecs Performance Comparison**

![Lossy codecs comparison](figs/John_Powell_&_Hans_Zimmer_-_Hero.full.wav.lossy.jpg)

- **Lossy Codecs Quality Comparison**

![Lossy codecs comparison](figs/John_Powell_&_Hans_Zimmer_-_Hero.full.wav.lossy_err.jpg)

</details>

# References

- https://stsaz.github.io/fmedia/audio-formats/
- http://wiki.hydrogenaud.io/index.php?title=Lossy
- http://wiki.hydrogenaud.io/index.php?title=Lossless
- https://en.wikipedia.org/wiki/Comparison_of_audio_coding_formats
