# Vira Inspired Theme

A Material-inspired VS Code theme with four carefully crafted dark variants. Inspired by the aesthetic of the Vira Theme (the official successor to Material Theme).

## Variants

- **Ocean** — Deep navy blues with teal accent. Easy on the eyes during long sessions.
<img width="1461" height="790" alt="image" src="https://github.com/user-attachments/assets/975b5fd7-17aa-47e0-b2af-ba78ca8bb95c" />

- **Palenight** — Rich purple darks with violet accent. Elegant and immersive.
<img width="2874" height="1578" alt="image" src="https://github.com/user-attachments/assets/9ad38e6a-53aa-4251-bad4-cba36d55b9cb" />

- **Carbon** — Near-black with desaturated syntax colors. Clean and distraction-free.
<img width="2860" height="1564" alt="image" src="https://github.com/user-attachments/assets/b99ee8bb-254c-495e-b89a-3ad3f04db0dc" />

- **High Contrast** — Maximum readability with vivid, fully saturated colors.
<img width="2858" height="1554" alt="image" src="https://github.com/user-attachments/assets/8ddc821f-a358-42d5-9f2d-829cda0b3ffe" />

## Icons

This theme pairs best with [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) (MIT licensed), which is listed as a recommended extension and will be suggested on install.

## Building from Source

The `.vsix` format is a ZIP archive with a specific internal structure. You don't need `vsce` to build it — you can package it manually with any zip tool.

### Required file structure

Your directory must look like this before zipping:

```
[Content_Types].xml
extension.vsixmanifest
extension/
  package.json
  README.md
  themes/
    ocean.json
    palenight.json
    carbon.json
    high-contrast.json
```

### `[Content_Types].xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">
  <Default Extension=".json" ContentType="application/json" />
  <Default Extension=".md" ContentType="text/markdown" />
  <Default Extension=".vsixmanifest" ContentType="text/xml" />
</Types>
```

### `extension.vsixmanifest`

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <Identity Language="en-US" Id="vira-inspired-theme" Version="1.0.0" Publisher="local" />
    <DisplayName>Vira Inspired Theme</DisplayName>
    <Description xml:space="preserve">A Material-inspired dark theme for VS Code.</Description>
    <Tags>theme,dark,material</Tags>
    <Categories>Themes</Categories>
    <GalleryFlags>Public</GalleryFlags>
    <Properties>
      <Property Id="Microsoft.VisualStudio.Code.Engine" Value="^1.75.0" />
    </Properties>
  </Metadata>
  <Installation>
    <InstallationTarget Id="Microsoft.VisualStudio.Code" />
  </Installation>
  <Dependencies />
  <Assets>
    <Asset Type="Microsoft.VisualStudio.Code.Manifest" Path="extension/package.json" Addressable="true" />
  </Assets>
</PackageManifest>
```

### Zipping on macOS / Linux

```bash
cd /path/to/your/build-folder
zip -r vira-inspired-theme-1.0.0.vsix .
```

> The zip must be created **from inside** the build folder so that `[Content_Types].xml` and `extension.vsixmanifest` are at the root of the archive — not nested inside a subdirectory.

### Zipping on Windows (PowerShell)

```powershell
cd C:\path\to\your\build-folder
Compress-Archive -Path * -DestinationPath vira-inspired-theme-1.0.0.vsix
```

### Using vsce (optional)

If you prefer the official tool, install it and run:

```bash
npm install -g @vscode/vsce
cd /path/to/extension   # folder containing package.json
vsce package
```

This automatically generates the manifest and content types for you.

## Installation

### From VSIX (manual install)
1. Open VS Code
2. Press `Ctrl+Shift+P` → `Extensions: Install from VSIX...`
3. Select the `.vsix` file
4. Reload VS Code
5. Press `Ctrl+K Ctrl+T` and choose a **Vira Inspired** variant

### Recommended settings

```json
{
  "workbench.iconTheme": "material-icon-theme",
  "editor.fontFamily": "'Fira Code', 'Cascadia Code', monospace",
  "editor.fontLigatures": true,
  "editor.fontSize": 14,
  "editor.lineHeight": 1.7
}
```

## Color Palette Reference

| Token        | Ocean     | Palenight | Carbon    | High Contrast |
|--------------|-----------|-----------|-----------|---------------|
| Accent       | `#80CBC4` | `#C792EA` | `#89DDFF` | `#00E5FF`     |
| Background   | `#0D1B2A` | `#1C1C30` | `#121212` | `#000000`     |
| Foreground   | `#EEFFFF` | `#EEFFFF` | `#D4D4D4` | `#FFFFFF`     |
| Keywords     | `#C792EA` | `#C792EA` | `#B87AA8` | `#E040FB`     |
| Strings      | `#C3E88D` | `#C3E88D` | `#89A87A` | `#00E676`     |
| Functions    | `#82AAFF` | `#82AAFF` | `#7A8FA6` | `#40C4FF`     |
| Numbers      | `#F78C6C` | `#F78C6C` | `#CF9E7A` | `#FF6D00`     |
| Classes      | `#FFCB6B` | `#FFCB6B` | `#C9B87A` | `#FFD600`     |

## License

MIT — free to use, modify, and distribute.
