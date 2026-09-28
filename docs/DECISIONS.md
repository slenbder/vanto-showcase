# Decisions

Short records of the choices that shape Vanto, and why.

### A queue, not a clipboard history

Clipboard managers keep everything you have ever copied and let you search it.
Vanto does the opposite: collection is explicit, only what you copy while
collecting enters the queue, and pasting consumes it in arrival order. The
point is getting several things somewhere else in the right order, not finding
something you copied last week. For the same reason the queue is not saved to
disk; it resets on quit.

### Ordinary ⌘C and ⌘V stay ordinary

Vanto never intercepts the system shortcuts. Collection has its own toggle
(⌃⌘C) and pasting has its own key (⌃⌘V), so nothing changes until you ask
for it.

### Direct distribution, no sandbox

Global key monitors and synthetic key events are unavailable to sandboxed
apps, and those two capabilities are the product. Vanto is therefore
distributed from its website as a signed, notarized app rather than through
the Mac App Store.

### Match shortcuts by character, store overrides by key

A default shortcut should mean "the C key" on every keyboard, including Dvorak,
AZERTY, and while typing in Russian or Japanese. Defaults are translated
through the ASCII-capable layout in both directions: key code to character for
matching, and character to key code for showing the binding in Settings. Both
directions use the same unmodified table so Settings never displays a
different key from the one that fires. User-recorded shortcuts are stored as
raw key codes, which is also what allows function keys.

### Files before images before text

A copied Finder file also answers as an image (its icon). Checking file URLs
first is the only reliable way to queue the file instead of its icon.

### AppKit status item, SwiftUI content

An AppKit `NSStatusItem` instead of `MenuBarExtra` lets the template icon
follow the menu bar's effective appearance and keeps the queue count as a
separate label laid out against the button's real bounds. The popover is
managed explicitly as well, which is what makes focus restoration before a
paste possible. SwiftUI still draws everything inside it.

### Drain only after the keystroke is posted

The queue loses an item only after the synthetic ⌘V was posted. That result
does not prove the target app accepted it, but failing earlier (focus could
not be restored, the pasteboard could not be written) never loses an item.

### Silent, automatic updates

A small utility should not ask about updates. Sparkle checks, downloads, and
installs on its own, with no toggle in Settings. The feed lives on the
product's own domain so it does not depend on where the source code is hosted.

### Offline-friendly licensing

The trial clock and the license live in Keychain on the Mac. Validation
retries later on network or server errors and keeps access meanwhile; only a
definitive "invalid" answer from the license server removes an activation. A
paying user should never be locked out by a flaky connection. An expired
trial blocks pasting but never touches the queue.

### Seven languages from day one, with an in-app override

The app, the website, and the demo on the website ship in English, Russian,
Spanish, German, Japanese, Simplified Chinese, and Brazilian Portuguese.
Settings can pick a language independently of the system one. German copy
uses the informal "du", matching Apple's own German.

### Honest accessibility

VoiceOver support is a baseline, not parity: reordering by drag has no
VoiceOver equivalent yet, and deleting an item moves focus to the list
container rather than the next row. These are documented gaps on the roadmap,
not hidden ones.
