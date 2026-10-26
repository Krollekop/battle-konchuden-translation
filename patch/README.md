# English Translation Patch

This page explains how to apply the English translation patch for *Battle Konchūden* (PlayStation, 1999).

The patch is distributed in PPF format. It modifies an existing game disc image; it does not include the original game.

## First release — Please read

This is the first public release of the English translation. Although the main story has been played through to the ending credits and automated regression tests have been performed, some parts of the game have not yet been fully tested.

You may encounter bugs, untranslated text, graphical issues, or unexpected behaviour. Some optional content remains incompletely tested, including later stages of Secret Mode, certain Story Mode item effects, and the optional PocketStation minigame.

Further updates may be released as testing continues. Feedback and reports of issues are very welcome!

## What's included

- The English translation patch in PPF format.
- Translation of the game's functional text, including dialogue, menus, insect names, encyclopedia entries, and interface elements.
- The original Japanese voice acting, game logo, studio logo, and decorative artwork are preserved.

## Requirements

Before applying the patch, you will need:

- A legally obtained copy of the original Japanese PlayStation game.
- The original disc image in BIN/CUE format.
- A PPF-compatible patching utility, such as PPF-O-Matic.
- `chdman`, included with [MAME](https://www.mamedev.org/).
- A PlayStation emulator that supports CHD images.

## Installation instructions

### 1. Prepare your original game image

Make sure you have the original game's `.bin` and `.cue` files.

**Make a backup of your original files before applying the patch.** Keep the untouched image somewhere safe in case you need to start over.

### 2. Apply the PPF patch

1. Extract the `.ppf` patch file from the downloaded archive, if necessary.
2. Open your PPF-compatible patching utility.
3. Select the appropriate original `.bin` file as the image to patch.
4. Select the English translation `.ppf` file.
5. Apply the patch and wait for the operation to finish.

The PPF patch must be applied to the appropriate BIN image, not to the CUE file.

**Important:** Keep the patched BIN file alongside the CUE file that describes the disc. If you keep the patched BIN under its original filename and in its original location, the CUE file will normally continue to reference it correctly. If you rename or move the BIN, update the filename referenced in the CUE file accordingly.

If the game image contains multiple BIN files, make sure you patch the specific file expected by the patch and preserve the rest of the disc image structure.

### 3. Convert the patched image to CHD

CHD is a convenient, compressed disc-image format supported by many PlayStation emulators.

Once the patch has been applied and the CUE file correctly references the patched BIN, use `chdman` to create the CHD image.

Open a terminal or Command Prompt in the folder containing the CUE and BIN files, then run:

```bash
chdman createcd -i "Battle Konchuden.cue" -o "Battle Konchuden English.chd"
```

Replace the input filename with the actual name of your CUE file if it differs.

The command reads the CUE file and the disc tracks it references, then creates `Battle Konchuden English.chd`. Keep the CUE and all referenced BIN files together until the conversion has completed successfully.

If `chdman` reports an error, check that the CUE file exists, that every BIN filename referenced inside it is correct, and that the files are in the expected locations.

### 4. Play the game

Open `Battle Konchuden English.chd` in a CHD-compatible PlayStation emulator and launch the game.

Enjoy *Battle Konchūden* in English!

## Troubleshooting

**The patching utility reports an error**

- Check that you are using the correct original game image.
- Make sure you selected the `.bin` file and the correct `.ppf` patch.
- Confirm that the image matches the version for which the patch was created.

**The CHD conversion fails**

- Check that the CUE file points to the correct BIN filename.
- Make sure all referenced disc-image files are present.
- Ensure that the patch was applied successfully before converting the image.

**The CHD does not load in my emulator**

- Make sure your emulator or PlayStation core supports CHD images.
- If the problem persists, try loading the patched BIN/CUE image directly, provided your emulator supports it. This can help determine whether the issue is related to the CHD conversion or to the patched image itself.

**I found a bug or a translation issue**

Please report it through the project's GitHub Issues page, including the game mode, the steps needed to reproduce the issue, and screenshots where possible.

## About this project

This is an unofficial fan translation project. It is not affiliated with, endorsed by, or associated with Jaleco or any other rights holder.

The patch contains translation modifications only and does not include the original game files.
---

[Back to the main project page](../README.md)
