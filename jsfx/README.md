# Reaper JSFX Installation and Enablement

This repository provides notes and examples for locating the JSFX installation directory in Reaper and how to enable/register JSFX effects. It also includes basic steps to clone this repository and start experimenting with custom JSFX in Reaper.

## Prerequisites

- Reaper installed on Windows, macOS, or Linux.
- Basic familiarity with Reaper's Preferences and the JSFX workflow.

***

## Repository setup

Clone this repository to your local machine:

```bash
git clone https://github.com/RichardAnthonySanchez/static-vs-lut.git
cd static-vs-lut
```

If you already have a local copy, pull the latest changes:

```bash
git pull origin main
```

***

## Where to find the JSFX installation directory

Reaper stores JSFX effects in a specific directory on your system. The exact path can vary by OS and Reaper version. Follow these steps to find the directory:

- Open REAPER
- At the top of the screen, click "Options"
- At the bottom of the drop down select, "Show REAPER resource path..."
- Explorer/Finder should open

Common locations are:

- Windows (64-bit Reaper):
  - User-specific JSFX:  
    `%APPDATA%\REAPER\Wave\JSFX\`  
    Example: `C:\Users\<YourUser>\AppData\Roaming\REAPER\Wave\JSFX\`
  - Global JSFX (installer-provided) might be under Reaper’s installation folder, e.g.:  
    `C:\Program Files\REAPER (x64)\Plugins\FX\JSFX\` (or similar)

- macOS:
  - User JSFX:  
    `~/Library/Application Support/REAPER/Wave/JSFX/`
  - Global JSFX often resides under the Reaper application bundle in a path like:  
    `/Applications/REAPER.app/Contents/Resources/JSFX/`

- Linux:
  - User JSFX:  
    `~/.config/REAPER/Wave/JSFX/`
  - Global JSFX:  
    `/usr/share/reaper/Plugins/JSFX/` or similar depending on distro/package

Notes:
- “JSFX” files are plain text with the extension `.jsfx-inc` or `.jsfx` and associated header blocks for Reaper to compile.
- There may also be a subfolder such as `FX` or `BlueCat\` depending on your Reaper version.

Tip:
- In Reaper, you can display the path by right-clicking a JSFX item in the FX browser and selecting “Open directory” or by inspecting the Reaper resource path in Preferences.

***

## Enabling and using JSFX in Reaper

1. Open Reaper.
2. Add an FX to a track:
   - Click the FX button on the track’s mixer/channel strip.
3. In the FX Browser, navigate to the JSFX category (often under “JS” or “JSFX”).
4. If your custom JSFX files are in the JSFX directory, they should appear in the list. If not:
   - Ensure Reaper is pointing to the correct JSFX directory (see above).
   - You can also enable “Show all effects” in the FX Browser to locate custom files.
5. Drag-and-drop or double-click a JSFX to load it on the track.
6. Adjust the parameters as provided by the JSFX UI.

Notes:
- If you’re developing your own JSFX, after saving your `.jsfx-inc`/`.jsfx` file into the correct directory, re-scan may occur automatically, or you may need to refresh the FX browser.
- Use the article and SDK reference for structure and common patterns when writing your own JSFX: the JSFX architecture includes the init, block, and end sections, plus optional user interface code.

***

## Quick development workflow

- Create or edit a JSFX file in your chosen editor.
- Save to the appropriate JSFX directory, preserving the proper file extensions.
- In Reaper, refresh/re-scan the FX list, then apply the new JSFX to a track.
- Open the JSFX’s UI (if any) and tweak parameters as needed.

***

## Troubleshooting

- If a newly added JSFX does not appear:
  - Confirm the file is in the correct JSFX directory per your OS.
  - Ensure the file has the proper extension and syntax according to the JSFX SDK.
  - Reboot Reaper or refresh the FX list.
- If a JSFX loads but behaves oddly:
  - Check the console/log for error messages (Reaper’s debug/log console can help).
  - Validate syntax against the SDK guidelines and the example code in the provided references.

***

## Further reading

- Write a Reaper MIDI JSFX from scratch (tutorial): https://www.admiralbumblebee.com/music/2018/02/08/Write-a-Reaper-MIDI-JSFX-from-scratch.html
- Reaper JSFX SDK overview and references: https://www.reaper.fm/sdk/js/js.php