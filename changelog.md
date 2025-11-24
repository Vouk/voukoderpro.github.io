---
layout: default
title: Changelog
---

# Changelog

## 3.0 - Begin of Q1 2026
- Core
  - Disabling a track doesn't cause Voukoder Pro to create an empty track anymore
  - If FFmpeg could not be found inform the user in a user friendly message
  - It's possible overwritten filenames can contain apostrophes
  - Muxer options (i.e. +faststart) are working again
  - Using FFmpeg 8.0 now
  - Sorting video tracks first, audio tracks are second
  - Optimized the compiler flags that resulted in around 8% performance increase
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
      - (Tell me if you need more)
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
