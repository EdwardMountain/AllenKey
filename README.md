# AllenKey

**MIDI hex strings for Allen & Heath Soft Keys**

AllenKey writes the hexadecimal MIDI strings that Allen & Heath consoles expect in their Soft Key MIDI fields, and reads them back. Choose the message, the channel and the values to build a string, or edit and paste the hex to see what it does.

It runs in your browser: no installation, no account, nothing uploaded.

Version: V1.02, by DoDo7

## What it does

- **Note**: Note On for Press. For Release, choose Note Off or Note On with velocity 0.
- **CC**: Control Change with separate Press and Release values. The standard function of the controller number is shown, when it has one.
- **Program**: Program Change. It is a two-byte message and has no Release string.
- **Channels 1 to 16**, one click each.
- **Separator**: bytes separated by commas (`90, 00, 7F`, the default, as the Allen & Heath editor software wants them) or by spaces (`90 00 7F`). Your choice is remembered.
- **Two-way editing**: change the controls and the hex updates; change the hex and the controls update.
- **Drag to edit**: drag a hex character up to increase it, down to decrease it. Works with mouse and touch; arrow keys work too.
- **Type or decode**: click or tap a byte to type it. Type or paste a whole string, such as `B3 14 7F`, to decode it. On a computer you can also paste anywhere on the page.
- **Copy**: the Copy button copies the Press or Release string.
- **Help**: a short guide to reading the bytes, plus the license.
- **Dark and Daylight** colour modes, remembered between sessions.
- **Defaults**: every session starts from Note On, channel 1, note C-1 (0), velocity 127.

## How to use it

1. Open `AllenKey_V1.02.html` in any modern browser (Chrome, Edge, Firefox, Safari), on computer, tablet or phone.
2. Choose Note, CC or Program, then the MIDI channel.
3. Set the note or controller and the values.
4. Type the bytes into the Soft Key on the console, or press Copy and paste the string into the Press or Release field of the editor software.

To read an existing string, paste it into AllenKey: the controls show the message type, channel, note or controller and value.

## Editing the hex

- On a data byte, the first character moves in steps of 16, the second in steps of 1.
- On the first byte, the first character sets the message type and the second sets the channel.
- Dimmed characters are fixed by the message, for example the release velocity of a note is always `00`.
- Wrong strings are rejected with a clear message, for example a data byte above `7F` or a Program Change with three bytes.

## Changes

- **V1.02**: comma separator by default, separator remembered between sessions, default note C-1 (0).
- **V1.01**: two-way editing between controls and hex, drag to edit, typing and decoding of whole strings.
- **V1.00**: first release.

## Reading the bytes

Most messages are three bytes, `xx yy zz`:

| Byte | Contains |
|---|---|
| `xx` | message type and channel |
| `yy` | note or controller number |
| `zz` | velocity or value |

| First byte | Message |
|---|---|
| `8n` | Note Off |
| `9n` | Note On |
| `Bn` | Control Change |
| `Cn` | Program Change (2 bytes) |

`n` is the channel minus one, in hex: channel 1 is `0`, channel 16 is `F`.

Note names use Middle C = C4 = 60 = `3C`.

## License

AllenKey is freeware. It is free to use for personal and professional work, and you may keep a copy on your own devices for offline use. Donations are welcome but never required: [paypal.me/edoardomontagnoli](https://paypal.me/edoardomontagnoli).

Selling it, or republishing it or a modified version as your own, is not allowed without written permission. See `LICENSE.txt` for the full text.

AllenKey is not affiliated with, endorsed by, or sponsored by Allen & Heath. Allen & Heath is a trademark of its respective owner.

Copyright (c) 2026 Edoardo Montagnoli (DoDo7).
