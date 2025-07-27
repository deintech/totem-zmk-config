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
  - [Charging](#charging)
  - [Reset](#reset)
  - [Firmware](#firmware)
- [Conventions](#conventions)
- [Layers](#layers)
  - [BAS](#bas)
  - [DEV](#dev)
  - [AXN](#axn)
  - [STG](#stg)
- [About](#about)

---

## Usage Guide

### Power

Your keyboard can be powered by **USB-C cable** or its **built-in battery**.

* **Battery Power:** To turn on battery power, slide the power switch to the **right** on both halves. The two halves will pair automatically.

  > The power switch controls battery power only. When connected via USB-C, the keyboard is powered and functions even if the switch is off.

* **Wired Mode:** Connect the left half to your device using a USB-C cable.

* **Wireless (Bluetooth) Mode:** Power on both halves using the battery switch. No cable is needed.

### Charging

To charge a half, ensure its power switch is in the **ON** position, then connect it to a power source (e.g., your computer) via its USB-C port.

### Reset

The reset button offers two functions:

* **Single Press:** Resets the keyboard (power cycles).
* **Double Press (quick):** Puts the keyboard into programming mode. When connected to your computer, it will appear as a USB device, allowing you to drag and drop or copy/paste firmware files for keymap updates.

### Firmware

Your Totem wireless keyboard uses **ZMK firmware**. For in-depth information, customization guides, and keymap creation, refer to the [ZMK documentation](https://zmk.dev/docs), specifically the [customization](https://zmk.dev/docs/customization) and [keymaps](https://zmk.dev/docs/features/keymaps) sections after your initial user setup.

**Updating Firmware:**
To update your keymap, you generally only need to flash the left half. However, for certain changes or troubleshooting, you may need to flash both.

**To flash a single half:**

1.  Turn off the half you intend to flash.
2.  Plug the half into your computer (ensure it's off).
3.  Double-press the reset button quickly.
4.  A new storage device, **XIAO-SENSE**, will appear on your computer. Drag and drop (or copy/paste) the appropriate firmware file (e.g., `totem_left-seeduino_xiao_ble-zmk.uf2` for the left half, or `totem_right-seeduino_xiao_ble-zmk.uf2` for the right) onto it.
5.  Wait for the storage device to automatically disappear (a few seconds).
6.  Unplug the board.
7.  Follow the [Power](#power) instructions to turn it ON.

**When to flash both halves:**
* If new keymap changes don't take effect after flashing only the left half.
* If you are updating to a new major version of ZMK firmware.
* **If you are experiencing persistent Bluetooth connection issues between the two halves or with your host device.** This is often resolved by ensuring both halves have compatible and up-to-date firmware.

### Bluetooth Connection Troubleshooting (Reset Firmware Shield)

If you are experiencing persistent issues with Bluetooth connections (e.g., halves not pairing, intermittent disconnections, or difficulty connecting to your computer), performing a "settings reset" on both halves can often resolve the problem. This clears all saved Bluetooth profiles and settings.

**To perform a settings reset on both halves:**

1.  **Generate the "settings reset" firmware:** You will need to modify your ZMK configuration to build a special "settings reset" `.uf2` file. Refer to the ZMK documentation on "Connection Issues" or "Reset Behaviors" for detailed instructions on how to include the `settings_reset` shield in your `build.yaml` (if using GitHub Actions) or how to build it locally. This will produce a specific `.uf2` file for settings reset.
2.  **Flash the "settings reset" firmware to the left half:** Follow the "To flash a single half" procedure above, but use the "settings reset" `.uf2` file generated in step 1.
3.  **Flash the "settings reset" firmware to the right half:** Repeat the "To flash a single half" procedure for the right half, using the "settings reset" `.uf2` file.
4.  **Re-flash your regular left firmware:** After resetting both halves, they will not automatically pair. Flash your standard `totem_left-seeduino_xiao_ble-zmk.uf2` file to the left half using the "To flash a single half" procedure.
5.  **Re-flash your regular right firmware:** Flash your standard `totem_right-seeduino_xiao_ble-zmk.uf2` file to the right half using the "To flash a single half" procedure.
6.  **Re-pair the halves:** After both halves are flashed with their regular firmware, ensure both are powered on. You may need to press the reset button on both halves simultaneously or briefly turn them off and on again to encourage them to re-pair.
7.  **Forget and Reconnect on Host Device:** On your computer or host device, "forget" or "remove" the keyboard from your Bluetooth devices list, then initiate a new pairing process.

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
