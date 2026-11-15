---
layout: default
title: Changelog
---
# Changelog

## 2027.0.0 - 2026-11-15
- Upgraded FFmpeg to 9.0 (Windows x64 and ARM64, Linux, macOS)
- Interlaced video: The field order (top or bottom field first) is now written to the encoded file. Frames are marked progressive when a deinterlace filter is used
- Fixed lost frames at the end of an export (encoders are now flushed correctly)
- Fixed post-processing commands with spaces or special characters in paths
- Fixed chapter parsing and 24-bit audio
- Errors during an export are now reported instead of being ignored
- Scene files are saved safely, so a crash while saving no longer leaves a broken scenes.json
- License check: Added timeouts, and the subscription check no longer fails when the license server can't be reached
- Premiere Pro: Reworked the plugin. Exports now carry the timecode, scenes are remembered more reliably (existing projects keep their selection), audio-only exports and frame rates are fixed, cancel and error messages are clearer and Unicode paths work
- After Effects: Added 32 bpc (float) output, tagged with the correct color space (After Effects 25.2+)
- After Effects: Fixed audio-only exports, several exports running at the same time, exact NTSC frame rates, pixel aspect ratio, straight/premultiplied alpha, the file extension and Unicode paths
- After Effects: Fixed scene identity and chapters, plus a problem with After Effects' idle callback
- After Effects: More detailed logging in the After Effects log
- DaVinci Resolve: Fixed scene identity and chapters
- VEGAS Pro: Fixed the audio length, the scene selection and memory leaks. Voukoder Pro now loads only when it's first used
- Designer: Asks to save unsaved changes before closing, fixed "Save As" and added support for Unicode paths
- Designer: Scene names are no longer passed through a shell when starting the Designer (security fix)
- Transkoder: Audio and video stay in sync, including variable frame rate sources and joined TS files. Fixed output planning and format conversion
- macOS: FFmpeg is no longer bundled. Voukoder Pro uses Homebrew FFmpeg and the installer warns if it's missing. macOS 15 or newer is required

## 2026.2.8 - 2026-11-13
- After Effects: Added support for 16 bpc color depth ("Trillions of Colors" and "Trillions of Colors+")
- Transkoder: Queue items can be reordered via drag and drop
- Transkoder: Queue items can be disabled to skip them without removing them from the queue
- Transkoder: Added a context menu to the queue with "Disable/Enable", "Go to Source", "Go to Output", "Duplicate" and "Remove"
- Transkoder: Showing the elapsed time while encoding and the total encoding time when an item is done
- Transkoder: The progress bar turns green while encoding and when done, and red if encoding failed
- Designer: The dropdowns in the preferences show the encoder IDs (e.g. h264_nvenc) so hardware encoders can be told apart
- Designer: Fixed the post-processing selection in the preferences

## 2026.2.7 - 2026-11-07
- Reworked the encoder parameters: the global options are now read directly from FFmpeg
- GOP size and B-frames default to the encoder's own defaults, like the FFmpeg command line does
- Fixed quality settings that had no effect with some encoders (e.g. MJPEG, MPEG-4, Snow, SpeedHQ, SVQ1, rav1e, kvazaar and WebP)
- libsvtav1: The CRF, VBR and CBR rate control modes are working now
- QSV: Fixed the rate control modes (CQP, ICQ, look-ahead)
- Existing scenes are converted to the new encoder parameters automatically

## 2026.2.6 - 2026-10-28
- Added an installation target for BorisFX Vegas Pro 2027

## 2026.2.5 - 2026-10-22
- Windows on ARM: The Core is now a hybrid ARM64X library and the DaVinci Resolve and VEGAS Pro plugins are ARM64EC builds
- Windows on ARM: Fixed a crash of the Designer
- ProRes 4444 with alpha: The MOV file now stores the correct bit depth so players (e.g. Resolume) detect the alpha channel
- Reverted the ProRes codec tag change from 2026.2.4
- Fixed the chroma subsampling shown for the NV16, P210 and P216 pixel formats (4:2:2 instead of 4:2:0)
- Installer: Updated the bundled Visual C++ runtime

## 2026.2.4 - 2026-08-21
- ProRes: Setting the codec tag (FourCC) that matches the selected ProRes profile in MOV and MP4 files

## 2026.2.3 - 2026-08-20
- Showing audio track codec tags as hex values instead of question marks
- Showing global options for libfdk_aac if the user uses a custom compilation for it

## 2026.2.2 - 2026-08-08
- Fixed the bug with random characters in the VEGAS Pro UI

## 2026.2.1 - 2026-08-08
- Tried to fix the bug Voukoder Pro doesn't start up in VEGAS Pro

## 2026.2.0 - 2026-08-06
- Added support for file attachments in the Matroska/MKV format
- Ignore all input nodes that are not connected  to any output node
- Removed the 2nd MATROSKA muxer entry
- Transkoder: Avoid displaying  horizontally compacted columns if no scenes.json file is there
- Transkoder: Prevents running the transcoding if no scenes are available.
- Transkoder: Using a QFileSystemWatcher that triggers reload of the scene selections and removed the manual actions (That solves also the blocking Transkoder  when the Designer is also open)
- Transkoder: Fixed a planar/packed audio decoding issue

## 2026.1.12 - 2026-08-02
- Applied a bt2020 fix

## 2026.1.11 - 2026-08-01
- Added support for exporting HDR (PQ and HLG) files with Premiere Pro

## 2026.1.10 - 2026-07-24
- Included a BETA but fully functional version of the "Transkoder" app

## 2026.1.9 - 2026-06-23
- Fixed a small issue with the new "Codec Tag" parameter

## 2026.1.8 - 2026-06-22
- Got After Effects on MacOS back working again!

## 2026.1.7 - 2026-06-21
- Added the "Codec Tag" selection to (hopefully) support encoding videos for telegram (and

## 2026.1.5 - 2026-06-18
- Made After Effects available again on Windows on ARM
- Remove the encoder/muxer compatiblity check for now to make ProRes in MXF work

## 2026.1.4 - 2026-06-17
- Introduce the MacOS version for Adobe Premiere Pro and Davinci Resolve Studio

## 2026.1.3 - 2026-05-10
- Fixed some settings in the installer for non-us customers

## 2026.1.2 - 2026-05-03
- Fixed one big bug in the plugin for VEGAS Pro 18, 19, 20 and 21

## 2026.1.1 - 2026-05-01
- Added "global"-options to many encoders
- Support multithreading with slice-based encoders (like FFv1)

## 2026.1.0 - 2026-04-26
- Added the new installer for the Boris FX VEGAS Pro 2026 plugin

## 2026.0.21 - 2026-04-12
- prores: Added qscale / global_quality specifier which lets the user to define the encoding quality

## 2026.0.20 - 2026-04-11
- Fixed allowing unlimited instances on the same computer

## 2026.0.19 - 2026-04-10
- Released the first BETA of the ARM64 build

## 2026.0.18 - 2026-01-22
- Core
  - Fixed applying side data (Stereo 3D, Spherical and HDR) in the encoder dialog

## 2026.0.17 - 2026-01-17
- Core
  - Removed the invalid BETA tag

## 2026.0.16 - 2026-01-10
- Core
  - Removed the watermark because it caused too many problems 

## 2026.0.15 - 2026-01-01
- Core
  - Disabling a track doesn't cause Voukoder Pro to create an empty track anymore
  - If FFmpeg could not be found inform the user in a user friendly message
  - It's possible overwritten filenames can contain apostrophes
  - Muxer options (i.e. +faststart) are working again
  - Using FFmpeg 8.0 now
  - Sorting video tracks first, audio tracks are second
  - Optimized the compiler flags that resulted in around 8% performance increase
  - Validating the license seat count more reliably
- Logging
  - Added the menu option to open the log dir.
  - Added a dropdown box in the settings to change to log level
  - Added a check box to the settings to enable or disable the logging
  - Added colors to the scene test log view
  - Added the option to select the number of days when to delete log files
  - Printing the system information at the beginning of each log file
  - Added a "Copy to clipboard" button
- NLE Plugin
  - [VEGAS Pro 23] Added a new plugin.
  - [VEGAS Pro] Probably fixed the issue Voukoder Pro is not displayed to some users
- Designer
  - Added back IAvoe's presets [FFV1, libsvtav1, libx264 and libx265 encoders (if present)]
  - The Designer supports re-opening the last open tabs
  - Supporting different 5.1 audio channel layouts now (Selectable over the input node)
  - It is now possible to add the ISO date and time when overwriting the file name in the file properties.
  - The "About" dialog has been reworked so you can see more information about your license.
  - Added a textual description to all video pixel formats and audio sample formats
  - Extended the "Open-Scene" dialog in the designer.
  - You can now select and open and delete multiple files.
  - There is also a new button where you can rename a single scene.
  - Scene Test
    - Made the simulated video- and audio tracks editable and deletable again
    - Fixed measuring the time (and corrected the fps) in the scene test
  - Languages
    - Added translations for multiple other languages:
      - Chinese
      - Japanese
      - Korean
      - Russian
      - Brazilian (Portuguese)
      - French
      - Spanish
      - German
      - (Tell me if you need more, please also report if translations are not correct)
- Installer
  - Expanded the VEGAS Pro Plugin section, so users are more aware they have to check their version here
- Licensing
  (Added an alternative, monthly subscription model license, still to come)

## 2.0.14 - 2025-06-29
  - Fixed the input field of the encoder settings > HDR > Min. Luminance that it can be 4 decimals.

## 2.0.13 - 2025-06-25
  - Added a watermark for users of the trial version. You'll still get access to the full functionality to test it.

## 2.0.12 - 2025-05-02
  - Fixed assigning the muxer options (i.e. WEBP "loop" or MP4 "faststart", etc)

## 2.0.11 - 2025-04-24
  - [Adobe Premiere Pro CC 2025] Fixed 5.1 audio support

## 2.0.10 - 2025-03-05
  - Fixed a small bug with the side data.

## 2.0.9
  - Fixed the side data values. Some of them have changed in FFmpeg 7.

## 2.0.8
  - Made the license verification more reliable

## 2.0.7
  - Fixed the Adobe After Effects plugin on Windows
  - The installer should ask for a reboot if necessary

## 2.0.6 - 2025-01-23
  - Voukoder Pro
    - Increased the number of muxer node inputs from 8 to 10

## 2.0.5 - 2025-01-10
- Voukoder Pro
  - (renamed color trc gamma22 & gamma28 to bt470m and bt470bg)
  - (Fixed the color range when using no filters)
  - Added support for Intel Macs
  - MacOS Big Sur should be lowest supported (untested)
  - Adobe Premiere Pro CC
    - Prevented the app to crash when an export has been started

## 2.0.0 - 2025-01-01
- Voukoder Pro
  - Added auto-detection of the FFmpeg filters and added those with a 1:1 media type
  - Added auto-detection of the FFmpeg output protocols and added some network outputs
  - Separated FFmpeg into it's own project and installer -> https://github.com/Vouk/ffmpeg/releases
  - Removed the external "asset" libs / dlls and cumpiled it into the Voukoder Pro project
  - Fixed encoder properties dialog
  - Switched log mode from DEBUG to INFO
  - Added version number to main window title
  - Supported opening the Designer App with a specific scene
  - Added the missing color spaces/matrices/transfers from FFmpeg 7.1
  - Added the "g" and "bf" global parameter to all h264, hevc and AV1 encoders
  - Added back the actual used encoder parameters preview box to the designer app
  - Added a file name input to the scene test
  - Improved (but not fixed) applying data from the filter chain to the codec context
  - Many smaller bug fixes
  - DaVinci Resolve Studio
    - Fixed DaVinci Resolve Studio alpha channel / transparency export
    - Made chapter export more reliable
