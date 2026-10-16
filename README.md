# Pragmatic Audio PEQ

**A system-wide parametric EQ for your headphones.** Load a correction for your headphones (OPRA, AutoEq and the measurement
sites), edit it, make your own, and hear it on everything you play. Made by [Pragmatic Audio](https://www.pragmaticaudio.com/).

![Music from any app passes through Pragmatic Audio PEQ on its way to your headphones or speaker](images/peq-concept-illustration.jpg)

This repository holds the **downloads** (see [Releases](../../releases)). The source is not published here. The full write-up,
with every screen explained, is on the website:
**[Pragmatic Audio PEQ: the article](https://www.pragmaticaudio.com/articles/2026/10/pragmatic-audio-peq/)**.

## What's new in 1.0.2 (build 38)

Available now in the macOS and Android downloads below. iOS App Store and
TestFlight distribution follow Apple's release process; the Windows download
remains build 26 while a new local Windows build is prepared.

- **Adaptive navigation.** Compact portrait screens show Live, Profile, Find profile,
  A/B and Settings. Wide or landscape screens show every section in a left sidebar,
  including Create and Effects. Tabs is the default for new installations; existing
  layout preferences are retained, and One page remains available in Settings.
- **More room to edit.** Graphs and section content fill the space beside the sidebar.
  Find profile includes Create your own, and A/B has its own destination.
- **Profiles and controls.** Import separate left and right personalised filter files,
  choose a language (including Dutch), adjust Smart Headroom or the preamp manually,
  and preview bass/treble preferences with the loaded profile retained.
- **Getting started.** A Welcome guide and clearer Live instructions explain connecting
  music, finding profiles and creating your own. An audio connection alone is no
  longer treated as confirmation that music is arriving.
- **Updated icon.** Larger white PEQ lettering on a black badge.

## Downloads

Please try them and report what you find in [Issues](../../issues).

| Platform | Get it | Status |
|---|---|---|
| **macOS** (Apple silicon and Intel, macOS 14 or newer) | [1.0.2 (38) DMG](https://github.com/jeromeof/PragmaticAudioPEQ-releases/releases/download/macos-v1.0.2/Pragmatic-Audio-PEQ-1.0.2-build38.dmg) · [release notes](../../releases/tag/macos-v1.0.2) | Signed by KONECKTA LIMITED; app and DMG notarized and stapled. |
| **Windows 11** | [Build 26 installer](https://github.com/jeromeof/PragmaticAudioPEQ-releases/releases/download/windows-v1.0.0/PragmaticAudioPEQ-1.0.0-build26-Setup.exe) | Previous tester build; a new local Windows build is pending. Not code-signed. |
| **Android** (9 or newer) | [1.0.2 (38) APK](https://github.com/jeromeof/PragmaticAudioPEQ-releases/releases/download/android-v1.0.2/Pragmatic-Audio-PEQ-1.0.2-build38.apk) · [release notes](../../releases/tag/android-v1.0.2) | Release-signed with the existing Android key; installed over build 26 on FiiO M25. |
| **iPhone and iPad** (iOS 27 or later) | [App Store](https://apps.apple.com/app/id6818329288) · [TestFlight](https://testflight.apple.com/join/U4Kt84nB) | TestFlight availability depends on Apple's processing and beta review. A physical device is required for live audio routing. |

Each new Mac and Android release includes a SHA-256 checksum file. The APK is for
direct installation and is separate from the Google Play submission.

The Mac app checks this page once a day and tells you when a newer version is out.

### Installing on macOS

1. Open the `.dmg` and drag **Pragmatic Audio PEQ** to Applications.
2. The first time you open it, it offers to install its audio driver, a virtual output called **Pragmatic EQ**. macOS asks for an
   administrator password, and your sound pauses for a second while the audio service restarts. Nothing is recorded.
3. Choose **Pragmatic EQ** as your sound output (the app can do that for you), and what you play is equalised.

The app lives in the menu bar and can open at login. **Uninstall Audio Driver…** in its menu removes the driver; then drag the
app to the Trash.

### Installing on Windows 11

1. Download `PragmaticAudioPEQ-…-Setup.exe` and run it. It needs administrator rights: it installs the app and an audio
   processing object that Windows' audio engine loads.
2. **Windows will warn you** ("Windows protected your PC"), because the installer is not yet signed with a paid code-signing
   certificate. Choose **More info**, then **Run anyway**. You can compare the file with the one on this page if you want to be sure.
3. In the app, open **Settings > Windows audio** and turn it on for **your** playback device (it is off until you do). Windows
   asks for permission, and restarts Windows audio, which stops your players for a moment. The app presses play again for you; if
   your player stays paused or silent, press play or restart it. A tray icon keeps the app running with the window closed.

Limits for now: only stereo, 32-bit float, 48 kHz has been tested (44.1 kHz, multichannel, USB DACs and exclusive mode have not),
and a few audio drivers replace Windows' effects and may drop ours (the app tells you and offers to turn it back on). If
Smart App Control is on, Windows can block the unsigned installer outright. If the effect ever fails, the sound passes through
untouched and `C:\ProgramData\PragmaticAudioPEQ\apo.log` says why. The uninstaller removes everything it added.

### Installing on Android

Android apps outside Google Play are installed by hand, which means allowing **unknown sources** once:

1. Download the `.apk` on the phone (or copy it there).
2. Open it. Android asks to allow installs from that app (your browser or file manager): choose **Settings**, switch on
   **Allow from this source**, and go back.
3. Choose **Install**. Later updates are installed the same way, over the top, and keep your settings.

Android has no system-wide output to choose, so the EQ is attached to the audio of the players that announce themselves, which
is how Wavelet and Poweramp Equalizer work. That means:

- Most music players work. A few, and some phones' own sound effects (Samsung's, Dolby's), can get in the way.
- The live views need a one-time **microphone permission** (Android uses it for audio visualisers; nothing is recorded), and Android only
  gives them coarse, mono, 8-bit audio, so they are rougher than on a Mac or iPhone.
- If the sound stutters on an older phone, raise **Settings > Android audio > Smoothness**.
- It needs Android 9 or newer.

## What it does

- **System-wide parametric EQ**, under any music app.
- **Load a PEQ** from [OPRA](https://opra.roonlabs.net/) (thousands of headphones and IEMs, every creator credited), from the
  measurement sites through their Export button, or from a `Filters.txt` file.
- **One PEQ editor**: drag the dots, change the width, type exact values, and hear every change live.
- **Make your own**: simple bass and treble, a fixed-band graphic EQ, an advanced editor, and **Uplifting PEQ**, a listening
  process that tunes the treble above 4 kHz to your own ears.
- **A bass and treble preference** that sits on top of any PEQ and any headphone.
- **A personalised library** you can export and import, and **pin to your headphones**, so they load their own PEQ when they
  connect.
- **A/B testing**, with volume matching, and a **blind test** with an exact result.
- **Effects**: crossfeed, a tube amp and vinyl.
- **Live visualisation**: eight views, including Visual PEQ, which shows what the EQ does to your music as it plays.
- **Headroom management**: the preamp is set from the filters, **Smart headroom** gives back volume where it safely can, and a
  limiter guards the peaks.
- **In English, French, Spanish, German, Italian, Chinese and Japanese.**

## A look

| | |
|---|---|
| ![Live Audio with Visual PEQ](images/peq-home-live-audio-visual-peq.jpg) | ![Loading a profile from OPRA](images/peq-opra-browser-model-list.jpg) |
| **Live Audio**: what you are hearing, and what the EQ is doing to it. | **Load**: OPRA's headphones and presets, with the creator credited. |
| ![The PEQ editor](images/peq-current-peq-personalised-selected.jpg) | ![Create](images/peq-create-menu.jpg) |
| **The editor**: one editor for every profile. | **Create**: Simple, Advanced or Uplifted. |
| ![Simple bass and treble](images/peq-create-simple.jpg) | ![Uplifting PEQ](images/peq-uplift-overview.jpg) |
| **Simple**: bass and treble, heard as you move them. | **Uplifting PEQ**: tune the treble to your own ears. |
| ![Library and pinning](images/peq-library-menu-pin.jpg) | ![A/B testing](images/peq-ab-testing.jpg) |
| **Library**: keep profiles, and pin one to your headphones. | **A/B testing**: with and without, level-matched. |
| ![Blind test results](images/peq-blind-test-results.jpg) | ![Effects](images/peq-effects-overview.jpg) |
| **Blind test**: does the PEQ really sound different? | **Effects**: crossfeed, tube amp and vinyl. |
| ![VU meters](images/peq-vu-meters.jpg) | ![The iPad in two panes](images/peq-ipad-landscape.jpg) |
| **Views**: VU meters, spectrum, spiral and more. | **iPad and big windows** get two panes. |

The screenshots are from the iPhone and iPad. The Mac, Windows and Android apps are the same app and look the same, with
the parts that need the platform's own audio (the output, the driver, the effect) adapted.

## Good to know

- It does not record, store or send your audio. OPRA's preset list is downloaded (about 1 MB) when you open Load.
- Uplifting PEQ is a listening aid, not a measurement. Check it with the blind test.
- Smart headroom trusts the limiter for the occasional peak. If your music is unusually bright and loud, use Safe.
- Vinyl and Tube Amp are effects inspired by real things, not models of specific equipment.

## Support

If it is useful to you, you can [buy Pragmatic Audio a coffee](https://buymeacoffee.com/pragmaticaudio). Bug reports and
suggestions are welcome as [Issues](../../issues) in this repository.

## Credits

Headphone corrections come from [OPRA](https://opra.roonlabs.net/) and its contributors (including oratory1990 and AutoEq),
credited in the app next to every preset. Pragmatic Audio PEQ is not affiliated with any of them.
