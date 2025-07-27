<picture>
  <source media="(prefers-color-scheme: dark)" srcset="/assets/images/logo_dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="/assets/images/logo_bright.svg">
  <img alt="TOTEM logo font" src="/assets/images/logo_bright.svg">
</picture>

# ZMK Config for Totem (Slipt Keyboard)

This is a WIP layout based on Colemak DHm for using on macOS (with **en-US International** ANSI layout on host) that includes Spanish accents, and complemented with easy access to development symbols.

![US International](/assets/layout/US-International.png)

---

## Menu

- [Usage](#usage)
  - [Power](#power)
  - [Charge](#charge)
  - [Reset](#reset)
  - [Configure](#configure)
- [Conventions](#conventions)
- [Layers](#layers)
  - [BAS](#bas)
  - [DEV](#dev)
  - [AXN](#axn)
  - [STG](#stg)
- [About](#about)

---

## Usage

### Power

The keyboard can be powered either by **USB-C cable** or **built-in battery**.

To turn on **battery power**, slide the power switch to the **left** (when seem from behind)."

The two halves pair automatically when both are powered.

- To use in wired mode:
Connect the left half to your device via USB-C.

- To use in wireless (Bluetooth) mode:
Power on the left half (battery switch ON). No cable is needed.

> The power switch controls battery power only. When connected by cable, the keyboard is powered and works even if the switch is off.

### Charge

To charge your boards you must put the half you want to charge in the ON position and connect it to a power source (it can be your computer) through the USB port.

### Reset

Pressing it once resets the keyboard (power cycle so essentially equivalent to turning it off and then back on).

Pressing it twice quickly puts into programming mode, if you plug it into your computer it shows up as a USB device instead of a keyboard; you can then drag and drop or copy and paste your firmware file to update your keymap.

### Configure

The wireless version of the Totem use ZMK as their firmware, you can find out more at [ZMK docs](https://zmk.dev/docs)

These pages will guide you to create your own keymap (follow them after your user-setup) [customization](https://zmk.dev/docs/customization) and [keymaps](https://zmk.dev/docs/features/keymaps)

Once you make changes to your keymap, you can download the firmware from the github actions tab of your repo. Since the keyboards come pre-flashed, you only need to flash the left half to change your keymaps. You can do it by following these steps:

1. Turn off both halves

2. Plug in the left half into your computer (without turning it on)

3. "Double tap" the reset button

4. After the previous step you should see a new storage device in your computer **XIAO-SENSE**. Drag and drop (or copy and paste) the firmware file `totem_left-seeduino_xiao_ble-zmk.uf2` which you should have generated and downloaded by following the guides linked above.

5. Wait until the storage device automatically disappears from your computer, this should not take longer than a few seconds.

6. Unplug the board from your computer

7. Follow the procedure in [Power ON](#power)

> Flashing the left half is usually enough. Flash both halves if some changes don’t take effect.

---

## Conventions

### Icons

Icons used to describe some modifiers and actions

| Label        | Description                                                  |
| :----------: | ------------------------------------------------------------ |
| <kbd>⌘</kbd> | Command                                                      |
| <kbd>⌃</kbd> | Control                                                      |
| <kbd>⌥</kbd> | Alt                                                          |
| <kbd>⇧</kbd> | Shift                                                        |
| <kbd>🄰</kbd> | Caps Lock                                                    |
| <kbd>⎋</kbd> | Esc                                                          |
| <kbd>↹</kbd> | Tab                                                          |
| <kbd>⏎</kbd> | Return                                                       |
| <kbd>␣</kbd> | Space                                                        |
| <kbd>⇪</kbd> | [Hold Tap](https://zmk.dev/docs/behaviors/hold-tap#hold-tap) |

⇧ [Back to menu](#menu)

---

## Layers

### BAS

Letters, accents for Spanish language and quick shortcuts for most used symbols to "avoid" changing layers.

![BAS Layer](/assets/layers/BAS.png)

#### Spanish

| Label        | Shortcut                                |
| :----------: | --------------------------------------: |
| <kbd>á</kbd> | <kbd>⌥</kbd>+<kbd>a</kbd>               |
| <kbd>Á</kbd> | <kbd>⇧</kbd>+<kbd>⌥</kbd>+<kbd>a</kbd>  |
| <kbd>é</kbd> | <kbd>⌥</kbd>+<kbd>e</kbd>               |
| <kbd>É</kbd> | <kbd>⇧</kbd>+<kbd>⌥</kbd>+<kbd>e</kbd>  |
| <kbd>í</kbd> | <kbd>⌥</kbd>+<kbd>i</kbd>               |
| <kbd>Í</kbd> | <kbd>⇧</kbd>+<kbd>⌥</kbd>+<kbd>i</kbd>  |
| <kbd>ó</kbd> | <kbd>⌥</kbd>+<kbd>o</kbd>               |
| <kbd>Ó</kbd> | <kbd>⇧</kbd>+<kbd>⌥</kbd>+<kbd>o</kbd>  |
| <kbd>ú</kbd> | <kbd>⌥</kbd>+<kbd>u</kbd>               |
| <kbd>Ú</kbd> | <kbd>⇧</kbd>+<kbd>⌥</kbd>+<kbd>u</kbd>  |
| <kbd>ü</kbd> | <kbd>^</kbd>+<kbd>u</kbd>               |
| <kbd>Ü</kbd> | <kbd>⇧</kbd>+<kbd>^</kbd>+<kbd>u</kbd>  |
| <kbd>ñ</kbd> | <kbd>⌥</kbd>+<kbd>n</kbd>               |
| <kbd>Ñ</kbd> | <kbd>⇧</kbd>+<kbd>⌥</kbd>+<kbd>n</kbd>  |

### Text

| Label          | Shortcut                    | Actions                                               |
| -------------: | --------------------------: | ----------------------------------------------------- |
| <kbd>⌫</kbd>   |                             | Backspace                                             |
| <kbd>⌫</kbd>   | <kbd>⌥</kbd>+<kbd>⌫</kbd>   | Delete word backward                                  |
| <kbd>⌫</kbd>   | <kbd>⌘</kbd>+<kbd>⌫</kbd>   | Delete until beginning                                |
| <kbd>⌦</kbd>   |                             | Delete                                                |
| <kbd>⌦</kbd>   | <kbd>⌥</kbd>+<kbd>⌦</kbd>   | Delete word forward                                   |
| <kbd>⌦</kbd>   | <kbd>⌘</kbd>+<kbd>⌦</kbd>   | Delete until end                                      |
| <kbd>▷</kbd>   |                             | Left (terminal autocompletion)                        |
| <kbd>🄰</kbd>   | <kbd>⇧</kbd>+<kbd>⎋</kbd>   | Caps lock                                             |
| <kbd>⇧⇧</kbd>  | <kbd>L⇧</kbd>+<kbd>R⇧</kbd> | [Caps word](https://zmk.dev/docs/behaviors/caps-word) |
| <kbd>⌘⌘</kbd>  | <kbd>L^</kbd>+<kbd>R^</kbd> | Cancel caps                                           |

### Files

| Label        | Shortcut                                | Actions                 |
| -----------: | --------------------------------------: | ----------------------- |
| <kbd>⌫</kbd> | <kbd>⌘</kbd>+<kbd>⌫</kbd>               | Move to trash           |
| <kbd>⌫</kbd> | <kbd>⌘</kbd>+<kbd>⌥</kbd>+<kbd>⌫</kbd>  | Delete file permanently |

⇧ [Back to menu](#menu)

### DEV

Symbols and dev shortcuts for JS/TS.

![DEV Layer](/assets/layers/DEV.png)

#### Symbols

| Label        | Shortcut                   |
| :----------: | -------------------------: |
| <kbd>°</kbd> | <kbd>⌥</kbd>+<kbd>#</kbd>  |
| <kbd>€</kbd> | <kbd>⌥</kbd>+<kbd>$</kbd>  |
| <kbd>«</kbd> | <kbd>⌥</kbd>+<kbd>[</kbd>  |
| <kbd>»</kbd> | <kbd>⌥</kbd>+<kbd>]</kbd>  |
| <kbd>¡</kbd> | <kbd>⌥</kbd>+<kbd>!</kbd>  |
| <kbd>¿</kbd> | <kbd>⌥</kbd>+<kbd>?</kbd>  |

#### Browser DevTools

| Label        | Shortcut                     | Action                     |
| -----------: | ---------------------------: | -------------------------- |
| <kbd>↻</kbd> |                              | Refresh                    |
| <kbd>⟳</kbd> | <kbd>⇧</kbd>+<kbd>↻</kbd>    | Hard refresh (clean cache) |
| <kbd>⩸</kbd> |                              | Open DevTools              |

#### IDE

| Label               | Action                      |
| ------------------: | --------------------------- |
| <kbd>💬</kbd>       | Cursor: Add to Chat         |
| <kbd>⚡</kbd>        | Cursor: Quick Edit          |
| <kbd>//</kbd>       | Toggle line comment         |
| <kbd>/\* \*/</kbd>  | Toggle block comment        |

⇧ [Back to menu](#menu)

### AXN

Quick navigation actions and numbers. Function keys works independently as a sub-layer to avoid shortcuts collisions.

![AXN Layer](/assets/layers/AXN.png)

#### Navigation

| Label         | Shortcut                   | Action                |
| ------------: | -------------------------- | --------------------- |
| <kbd>△</kbd>  |                            | Up                    |
| <kbd>▽</kbd>  |                            | Down                  |
| <kbd>◁</kbd>  |                            | Left                  |
| <kbd>▷</kbd>  |                            | Right                 |
| <kbd>⇤</kbd>  |                            | Home                  |
| <kbd>⇥</kbd>  |                            | End                   |
| <kbd>⇞</kbd>  |                            | Page up               |
| <kbd>⇟</kbd>  |                            | Page down             |
| <kbd>⇺</kbd>  |                            | Prev Tab              |
| <kbd>⇻</kbd>  |                            | Next Tab              |

#### Actions

| Label          | Shortcut                   | Action               |
| -------------: | -------------------------- | -------------------- |
| <kbd><\|</kbd> |                            | Expand selection     |
| <kbd>\|></kbd> |                            | Shrink selection     |
| <kbd>↶</kbd>   |                            | Undo                 |
| <kbd>↷</kbd>   |                            | Redo                 |
| <kbd>⬚</kbd>   |                            | Cut                  |
| <kbd>⿻</kbd>  |                            | Copy                 |
| <kbd>⏍</kbd>   |                            | Paste                |
| <kbd>⛶</kbd>  | <kbd>⇧</kbd>+<kbd>⏍</kbd>  | Paste without format |
| <kbd>☉</kbd>  |                            | Find                 |
| <kbd>☊</kbd>  |                            | Replace              |

⇧ [Back to menu](#menu)

### STG

Dedicated to Bluetooth and media controls.

![STG Layer](/assets/layers/STG.png)

#### Actions

| Label           | Shortcut                   | Action                        |
| --------------: | -------------------------- |  ---------------------------- |
| <kbd>B#️⃣</kbd>   |                           | Jump to #️⃣ device             |
| <kbd>❌</kbd>   |                            | ZMK Studio                    |
| <kbd>BC</kbd>   | <kbd>⇧</kbd>+<kbd>❌</kbd> | Clear Current Bluetooth       |
| <kbd>BA</kbd>   | <kbd>⌥</kbd>+<kbd>❌</kbd> | Clear All Bluetooth           |
| <kbd>Z+</kbd>   |                            | Zoom in                       |
| <kbd>ZR</kbd>   |                            | Zoom reset                    |
| <kbd>ZR</kbd>   | <kbd>⇧</kbd>+<kbd>ZR</kbd> | Zoom reset VSCode             |
| <kbd>Z-</kbd>   |                            | Zoom out                      |
| <kbd>🔅</kbd>   |                            | Bright down                   |
| <kbd>🔆</kbd>   |                            | Bright up                     |
| <kbd>⎚</kbd>    |                            | Application Window            |
| <kbd>▤</kbd>    |                            | Mission Control               |

#### Tools

| Label          | Shortcut                   | Action                        |
| -------------: | -------------------------- |  ---------------------------- |
| <kbd>⛢</kbd>  |                            | Show Color Picker             |
| <kbd>🜜</kbd>   | <kbd>⌥</kbd>+<kbd>⛢</kbd> | Pick a color                  |
| <kbd>□</kbd>   |                            | Capture screenshot options    |
| <kbd>▣</kbd>   | <kbd>⇧</kbd>+<kbd>□</kbd>  | Capture portion of the screen |
| <kbd>▣</kbd>   | <kbd>▣</kbd>+<kbd>␣</kbd>  | Capture a window or menu      |
| <kbd>⛶</kbd>  | <kbd>⌥</kbd>+<kbd>□</kbd>  | Capture area of the screen    |
| <kbd>⎅</kbd>   |                            | Finder (File Explorer)        |
| <kbd>⌑</kbd>   | <kbd>⌥</kbd>+<kbd>⎅</kbd>  | Show/hide system files        |

> [!NOTE]
> Combine `^` with `⇧` or `⌥` for sending the screenshoot to the clipboard instead of saving it to a file.

#### Media

| Label         | Shortcut                  | Action       |
| ------------: | ------------------------- | ------------ |
| <kbd>🔊</kbd> |                            | Volume up    |
| <kbd>🔇</kbd> |                            | Volume Mute  |
| <kbd>🎙️</kbd> | <kbd>⇧</kbd>+<kbd>🔇</kbd> | Mic Mute     |
| <kbd>🔉</kbd> |                            | Volume down  |

> Requires (MuteKey)[https://apps.apple.com/us/app/mutekey/id1509590766?mt=12] app

#### IDE

| Label        | Action |
| -----------: | ------ |
| <kbd>☗</kbd> | Home   |
| <kbd>♆</kbd> | Git    |
| <kbd>♺</kbd> | Debug  |
| <kbd>⊛</kbd> | ToDo   |

#### MacOS

| Label        | Action             |
| -----------: | ------------------ |
| <kbd>▤</kbd> | Mission Control    |
| <kbd>⎚</kbd> | Application Window |

⇧ [Back to menu](#menu)

---

## About

### Fork

- [zmk-config-totem](https://github.com/GEIGEIGEIST/zmk-config-totem) - ZMK GEIGEIGEIST layout

### Built With

- [VS Code](https://code.visualstudio.com/) - Code editing redefined.
- [ZMK Docs](https://zmk.dev/docs) - Modern, open source keyboard firmware
- [Keymap Editor](https://nickcoutsos.github.io/keymap-editor) - GUI ZMK Keymap Editor
- [Figma](https://www.figma.com/) - The collaborative interface design tool

### Typing

- [Colemak Club](https://gnusenpai.net/colemakclub/) - Learn Colemak Layout
- [Monkeytype](https://monkeytype.com/) - A minimalistic typing test, featuring many test modes, an account system to save your typing speed history and user configurable features like themes, a smooth caret and more.
- [Typ.ing](https://typ.ing/) - a typing trainer by [zsa.io](https://www.zsa.io/)

### Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [totem-zmk-config](https://github.com/deintech/totem-zmk-config/tags) on GitHub.

### Authors

- **Camilo Martinez** [[Equiman](http://github.com/equiman)]

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.

⇧ [Back to menu](#menu)
