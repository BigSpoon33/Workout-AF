# Installation Guide

## Prerequisites

1. **Obsidian** v1.0 or higher
2. **Datacore Plugin** - This library requires the Datacore community plugin

## Installing Datacore

1. Open Obsidian Settings
2. Go to Community Plugins
3. Click "Browse" and search for "Datacore"
4. Install and enable the plugin

## Option 1: Use as a Standalone Vault

1. Open this folder as a vault in Obsidian
2. Enable the Datacore plugin
3. Open `System/Dashboards/Component-Showcase.md` to see the components

## Option 2: Copy to Your Existing Vault

Copy the `System` folder to your vault:

```
Your Vault/
├── System/
│   ├── Scripts/
│   │   ├── Core/
│   │   ├── Components/
│   │   └── Widgets/
│   ├── Themes/
│   ├── Dashboards/
│   └── Settings.md
└── ... your other files
```

## Configuration

### Settings File

The `System/Settings.md` file stores your active theme and preferences:

```yaml
---
widget-theme: default          # Active theme ID
widget-color-override: ""      # Optional color scheme override
flashy-mode: true              # Enable/disable animations
---
```

### Creating Custom Themes

#### The Easy Way
1. Use the Theme Studio

#### The Hard Way
1. Copy `System/Themes/_themeTemplate.md`
2. Rename it (e.g., `my-theme.md`)
3. Fill in the frontmatter values:
   - `theme-id`: Unique identifier (lowercase, no spaces)
   - `theme-name`: Display name
   - Colors, gradients, and styling options
4. Use the Theme Studio to switch to your new theme

### Adding Sprites

For animated sprites on buttons, bars, and toggles:

1. Find or create a GIF image
2. Load the image directly in the Theme Studio or
3. Convert to base64 (many online tools available)
4. Paste the full data URL in your theme:

```yaml
bar-sprite: "data:image/gif;base64,R0lGODlh..."
```

## Using Components

In any note, create a `datacorejsx` code block:

````markdown
```datacorejsx
const { GloButton } = await dc.require(
    dc.fileLink("System/Scripts/Components/dc-gloButton.jsx")
);

return (
    <GloButton
        label="Hello"
        onClick={() => new Notice('Hello!')}
    />
);
```
````

```datacorejsx
const { GloButton } = await dc.require(
    dc.fileLink("System/Scripts/Components/dc-gloButton.jsx")
);

return (
    <GloButton
        label="Hello"
        onClick={() => new Notice('Hello!')}
    />
);
```

## Troubleshooting

### Components not rendering

1. Ensure Datacore plugin is enabled
2. Check that file paths are correct (`System/Scripts/...`)
3. Refresh the note or restart Obsidian

### Theme not applying

1. Verify `System/Settings.md` has the correct `widget-theme` value
2. Ensure the theme file exists in `System/Themes/`
3. Check the theme file has a valid `theme-id` in frontmatter

### Import errors

The components use relative paths like:
```javascript
dc.fileLink("System/Scripts/Components/dc-gloButton.jsx")
```

If you placed the `System` folder in a subdirectory, update the paths accordingly.

## Support

For issues or feature requests, visit the Rice AF repository.
