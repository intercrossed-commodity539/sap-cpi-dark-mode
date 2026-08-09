# SAP CPI Dark Mode

A dark theme for SAP Integration Suite and SAP Cloud Integration. It gives the
tool a comfortable charcoal look that is easier on the eyes during long working
sessions. You can adjust brightness, contrast, and warmth, and the theme only
runs on SAP CPI pages.

I built this because I spend most of my day in SAP CPI and the default light
theme gets tiring. It is a Chrome extension (Manifest V3) and works in Chrome
and Edge.

## Features

- Comfortable charcoal look that avoids a harsh pure black.
- Three one click presets: Soft, Comfort, and Deep.
- Fine tune sliders for Brightness, Contrast, Warmth, and Saturation.
- Warmth control lowers blue light for late sessions.
- Keyboard shortcut to turn it on or off.
- Runs only on SAP CPI pages. Other sites are not touched.
- No tracking and no network calls. Settings stay in your browser.

## Install from a release

1. Download the zip from the latest release on the Releases page.
2. Unzip it to a folder you will keep.
3. Open your browser and go to the extensions page.
   - Chrome: chrome://extensions
   - Edge: edge://extensions
4. Turn on Developer mode.
5. Click Load unpacked and select the unzipped folder.
6. Open SAP CPI. Use the toolbar icon to toggle or adjust the theme.

## Install from source

1. Clone or download this repository.
2. Follow steps 3 to 6 above and select the repository folder.

## Keyboard shortcut

The default toggle shortcut is Alt+Shift+D. To change it, open
chrome://extensions/shortcuts, find SAP CPI Dark Mode, and set your own
combination. The popup shows the shortcut that is currently active.

## How it works

The page is themed with one CSS filter on the root element:

```
html { filter: invert(100%) hue-rotate(180deg) brightness(B%) contrast(C%) sepia(W%) grayscale(G%) }
```

SAP CPI uses a light interface, so the invert and hue rotate stages turn it
dark. Contrast below 100 lifts the result to a soft charcoal and eases harsh
white text. Warmth reduces blue light. Images, logos, and video are inverted a
second time so they still look natural.

This is a filter based theme, so it covers the whole app quickly and stays
consistent, including the integration flow editor. It is not a per control color
map, so a few colors are approximate, but the defaults keep the SAP status
colors readable.

## Presets

| Preset  | Brightness | Contrast | Warmth | Good for                        |
| ------- | ---------- | -------- | ------ | ------------------------------- |
| Soft    | 108        | 74       | 12     | tired eyes or dim rooms         |
| Comfort | 105        | 80       | 8      | everyday use                    |
| Deep    | 100        | 92       | 5      | bright rooms or higher contrast |

## Permissions

- storage: saves your settings and syncs them with your browser profile.
- tabs: lets the popup confirm the current tab is a SAP CPI page so it can show
  the right status. It does not read page content.
- Host access to SAP business technology platform hosts: needed to apply the
  theme on SAP CPI pages.

## Privacy

This extension does not collect, send, or sell any data. All settings stay in
your browser. See PRIVACY.md for the full statement.

## Notes and limits

- The theme approximates some colors rather than mapping each control. The
  defaults keep the SAP status colors readable.
- Native browser tooltips cannot be styled by any extension.
- SF Pro Display is used for the toolbar popup only, with a system fallback on
  non Apple platforms. No font files are bundled.

## License

MIT. See LICENSE.
