# PS5 FPKG Builder


Windows application for reading, preparing, and building PS5 PKG/FPKG files from prepared source folders or supported image/container formats.

Credits: Drakmor and SvenGDK for the original project and for the foundations used while studying the package-building workflow.

## Features

- Build PKG files from prepared source folders.
- Import `.exfat`, `.ffpkg`, `.ffpfs`, and `.ffpfsc` files.
- Automatic extraction during the `Build PKG` process.
- Automatic cleanup of temporary extracted folders after a successful build.
- PKG inspection in the `Reader` tab.
- Cover, background, Title ID, region, version, type, SDK, and minimum system version preview.
- Languages: English, Portuguese, Spanish, and Russian.
- Automatic update check through GitHub Releases.
- Single-file executable for easier distribution.

## How To Use

### 1. Build Tab

Use the `Build` tab to create a PKG.

1. Click `Import folder` to select an already prepared source folder.
2. Or click `Import file` to select a `.exfat`, `.ffpkg`, `.ffpfs`, or `.ffpfsc` file.
3. Check the preview: cover, background, Title ID, region, version, and type.
4. Choose the `Output folder`.
5. Adjust the settings if needed:
   - `Content ID`
   - `Title`
   - `Version`
   - `Passcode`
   - `Package`
   - `Image`
   - `Kraken`
   - `PlayGo`
6. Click `Build PKG`.
7. Wait for the log to finish successfully.
8. Click `Open output` to open the folder where the PKG was generated.

When an image/container file is imported, it is not immediately extracted into a permanent source folder. Extraction happens inside the `Build PKG` process, using a temporary folder, and that folder is removed automatically after a successful build.

### 2. Clear Import

Use the `Clear` button in the import area of the `Build` tab to remove the imported file or folder from the preview.

This clears:

- imported path;
- cover;
- background;
- displayed metadata;
- preview status.

The general build settings remain available for the next import.

### 3. Reader Tab

Use the `Reader` tab to inspect a PKG.

1. Click `Import PKG`.
2. Select a `.pkg` file.
3. The application will display:
   - file path;
   - Content ID;
   - Title ID;
   - region;
   - version;
   - format;
   - minimum system version;
   - SDK;
   - size;
   - entries;
   - cover and background when available.

System and SDK versions are shown in human-readable format, for example `9.00` or `9.40`.

### 4. Supported Formats

#### Folders

A prepared source folder usually contains `sce_sys/param.json` and the application/game content files.

#### `.exfat`

An exFAT image containing the game/application structure.

#### `.ffpkg`

Image/container format that can be read and extracted into a source structure before build.

#### `.ffpfs`

PFS image. When it contains an internal exFAT image, the application performs a deep read and extracts the correct layer for the build.

#### `.ffpfsc`

Compressed image. The application decompresses it and processes the internal image during the build.

### 5. Output And Temporary Files

- The default output folder uses the `-pkg` suffix.
- The default temporary folder uses `%TEMP%`.
- If the build succeeds, the temporary extracted folder is removed.
- If the build fails, the temporary folder may be preserved for diagnostics.

<img width="1918" height="1031" alt="image" src="https://github.com/user-attachments/assets/e70eef7b-96b2-4e3f-a729-aaf9aae4f92d" />

This project focuses on application engineering, metadata reading, source preparation, and package creation. It does not document or share sensitive information, private keys, or protected material.
