# Changelog

Released versions are listed here and on the [Releases](../../releases) page.

## 1.0.0 — 9 October 2026

- First public release for Apple silicon Macs running macOS 13 or later.
- Signed and notarized DMG available from the website and GitHub Releases.
- FIFO queue for text, images, and files; reorder, drag out, or combine text
  before pasting.
- 14-day unrestricted trial; one-time license for up to three Macs, with
  automatic future updates included.
- Seven app and website languages. Sparkle update feed published.

## Development history before 1.0.0

### September 2026

**27 Sep**
- Launch waitlist on the website.
- Search and link-preview metadata for the website.

**26 Sep**
- Website translated into all seven app languages.
- German interface switched to the informal "du".
- 14-day refund window.

**25 Sep**
- Product renamed to Vanto; marketing website launched at
  [vanto.slenbder.com](https://vanto.slenbder.com).

**23–24 Sep**
- 14-day trial with reminders 7, 3, and 1 day before the end.
- License activation, weekly validation that tolerates being offline, and
  deactivation to move a license to another Mac.
- Automatic updates with Sparkle.
- Continuous integration for tests and the Release build.

**22 Sep**
- Combine and Paste: merge text items into one paste with a chosen separator.
- Release build targets Apple silicon.

**19–20 Sep**
- Settings screen: rebind both shortcuts, choose one of seven languages,
  Launch at Login.

**16 Sep**
- Popover stays put while you paste through the queue.
- A copy made just before pasting is captured instead of lost.
- Caps Lock no longer blocks the shortcuts; key repeat is ignored.
- Synthetic paste follows the current keyboard layout.
- Items stay in the queue if preparing a paste fails.

**13–14 Sep**
- Shortcuts follow the key's character on Dvorak, AZERTY, and non-Latin
  input sources.
- Copying several images keeps all of them, not just the first.
- Queued files keep their original names.
- Baseline VoiceOver support.

**10–12 Sep**
- Separate recording and queue indicators in the menu bar.
- New app and menu-bar icons.

**5 Sep**
- First version: a FIFO clipboard queue in the menu bar.
