# What Tinycast Won't Do

Some requests get a "no" on purpose. This page lists those choices, so you know what to expect
before you ask.

Every item here comes from a real request on GitHub. The number after each item links to the full
discussion.

## Why we say no

**Tinycast is not a copy of Raycast.** We don't add a feature only because Raycast has it. If
Raycast already does what you need, it may be the better app for you, and that's fine.

**Simple, light and fast comes first.** Each new option makes the app heavier and harder to keep
working. So we keep fewer settings and fewer special cases.

**A little extra effort is on purpose.** Some things take one or two more key presses than in other
launchers. We accept that to keep the app simple.

**Your data stays on your Mac.** We avoid network requests that aren't needed.

---

## Mac, languages and updates

- **Windows or Linux.** Tinycast is Mac only. It uses Apple tools that don't run on other systems.
- **More app languages.** Tinycast comes in English plus eight languages. That list is final for now. We may add one more
  language later, but not soon.
- **A beta switch in the regular app.** Stable and beta stay separate until at least version 1.0.
- **Import from Alfred, or from old Raycast exports.** Import works with Raycast v2 exports only.

## Typing in other languages

- **Input methods (IME) such as Chinese, Japanese or Wubi.** Basic typing works. But each
  input-method fix broke something for other people, so **we no longer fix input-method bugs.**
  That covers arrow keys or Escape while you compose, text that goes to a bar at the bottom of the
  screen, lag right after opening, the Notes placeholder over your text, and snippets leaving part
  of the keyword behind. New input-method reports are closed as not planned.
  **Instead:** the community fork [tinycast-cn](https://github.com/conversun/tinycast-cn).
- **More cases for Chinese app names.** Tinycast finds an app by its Chinese name, and matches
  pinyin too. It works when your Mac uses Simplified or Traditional Chinese with any region, for
  example Simplified Chinese with the US or Hong Kong region. If an app has no name in your
  language, Tinycast uses its English name. **That is every case we support, and we won't add
  more.** New reports about Chinese app names are closed as not planned.
  **⚠️ If these cases keep breaking, we may remove translated app names and show English names
  only.** **Instead:** add the Chinese name as an alias in Settings → Applications.
- **Keyboard layouts other than US QWERTY.** Paste, snippets and emoji press keys by their position
  on a US keyboard. On Colemak, Dvorak and similar layouts this can trigger the wrong shortcut.
  Shortcuts also don't match by layout.
- **App names in another language.** App names follow your Mac's language. **Instead:** set your
  Mac to English if you want English names.
- **Define Word in languages other than English.** The layout looks right only in English.

## Launcher and search

- **Search history.** There is no list of past searches, and ↑ won't bring one back. The launcher
  already learns what you open and moves it higher.
- **⌘1–⌘9 to open any result.** Number shortcuts work only on Favorites in the launcher and on
  pinned items in Clipboard History.
- **Space to act like Tab or Enter.** Space always types a space. After an alias, press **Tab** to
  fill in its inputs. Space in an empty search box won't open File Search either.
- **Vim keys (j/k).** **Instead:** use Ctrl-N and Ctrl-P.
- **⌘↑ and ⌘↓ to jump between sections.**
- **Click once to select, double-click to open.**
- **Dictionary results right in the launcher.** A lookup takes a few extra key presses.
- **Paste something to act on it**, like JSON to open a viewer or a file path to open Finder.
  **Instead:** use Search Files.
- **"!" to run shell commands.** **Instead:** make a custom command.
- **Drop-down choices for custom command inputs.**
- **Keep the palette open after a command shows a message.**
- **Jump from the launcher to an app's shortcut setting.** Go through Settings.
- **Act on selected text or files from anywhere (LaunchBar's Instant Send).**
- **Apps inside Parallels Desktop.**
- **Small palette quirks we keep:** dragging an app out makes a Desktop alias, a dragged palette can
  move off centre when the screen resolution changes, and very fast drags can stutter a little.

## Clipboard History

- **Encryption.** History is not encrypted. It never leaves your Mac, and encryption would slow it
  down. **Instead:** add sensitive apps to the block list.
- **⚠️ Copies from menu-bar helpers, like the Passwords menu.** The block list covers normal app
  windows only. Catching menu-bar helpers needs private Apple tools, so **those copies still land in
  your history.** Delete them by hand if you need to.
- **A large ⌘Y Quick Look preview.** The preview pane already shows the selected item.
- **Open images in Preview.** **Instead:** use Show in Finder.
- **Link previews or website icons.**
- **Keep a pasted item where it was.** A pasted item always moves to the top.
- **Copy without closing Tinycast.**
- **A global shortcut for paste as plain text.** It lives inside Clipboard History (⌃⌘↵).
- **Fuzzy search.**
- **Type "img" to filter.** **Instead:** press ⌘P to filter by type.
- **Merge duplicate entries.**
- **Turn an entry into a snippet with ⌘S.**
- **Block chosen extensions.**
- **A separate screenshot browser.** **Instead:** filter history by images and search the text in
  them. It may come later as a plugin.

## Snippets

- **Put a snippet on the clipboard instead of typing it.**
- **Pin snippets.**
- **Sort snippets by last used.**

## Calculator

- **A normal space as a thousands separator** (like `1 000 000`). A space already has a job: `1hr 30`
  and `5 feet 3 inches` must keep working. Commas and dots follow your region under Settings →
  General → Calculator → Number format.
- **`_` as a number separator** (like `1_000`).
- **Calculate the text you selected.** Each feature stays separate.

## Window management

Tinycast is an all-in-one launcher, not a full window manager. Its window tools are finished.

- **Custom snap cycles (like Loop), edge-anchored sizes, or step-by-step undo.**
- **Move a window without resizing it.** It caused odd side effects.
- **Drag a window to a screen edge to snap it.**
- **macOS Fill & Arrange layouts.**
- **Layouts per workspace (like FlashSpace).**
- **Switch Windows changes.** The order stays stable for muscle memory. No switch-on-release, and no
  alias search.
- **Follow Stage Manager.** **Instead:** try Window Rooms.
- **Safari's width after Mission Control.** Safari may reset its width afterwards.

## Notes

- **More than one Notes window.** One window, many notes.
- **Turn off "always on top".** Most people want Notes to float.
- **Collect everything you copy into a note (AutoPaste).**

## AI and dictation

- **Send your selected text or file to AI on its own.** macOS often won't share the selection.
- **Send prompts with ⌘↵.**
- **Different default models for Quick AI and AI Chat.** They are one feature with two sizes.
- **Open and close Quick AI with the main shortcut.** **Instead:** give Quick AI its own shortcut.
- **More command-line AI tools (like Pi Coding Agent).** Providers can block these tools at any
  time, so they may stop working.
- **Voice control, screen reading, or AI command suggestions.** Tinycast won't become a Siri-style
  assistant.
- **AI-powered "smart" search.** Search stays fast and on-device.
- **Old Raycast AI chats on import.** Raycast doesn't share that data.
- **Quick Action results inside the palette, or a preview that stays open.** **Instead:** copy the
  result with its copy button.
- **A proxy setting.**
- **Your own dictation models or a personal word list.** Tinycast is not a dictation app.

## Raycast extensions

- **Full Raycast compatibility.** Tinycast runs about 80% of what Raycast extensions use, and **that
  work has stopped.** Some extensions won't work, or will look a bit different. Tinycast's own
  shortcuts (like Tab) win over an extension's. Our future is native Tinycast extensions.
- **Let extensions use Tinycast's AI.**
- **⚠️ Locking extensions down.** An extension can do anything you can do on your Mac. **Install only
  extensions you trust.**

## Settings and looks

- **A theme editor or a custom font.**
- **Show ⌃⌥⇧⌘ as one ◆ symbol.**
- **Interface Size for the Settings window.** It sizes the palette only.
- **A switch to hide every item.** You can already turn almost every feature off.
- **Filter apps by shortcut, a "?" jump to settings, or no sidebar headings.**
- **Hide the calendar colour dot, or more meeting filters.**

## Hotkeys

- **Turn a shortcut off in chosen apps.**
- **One hotkey that cycles through several apps.**
- **Shortcut sequences (press one key, then another).**

## Other features we won't add

- **Quit apps on their own, or "quit all except".** Everything stays manual. **Instead:** a custom
  command with AppleScript can quit apps.
- **A timer, focus sessions, a flight tracker or confetti.**
- **Brightness and volume for external monitors.**
- **Fix accidental capitals as you type.**
- **The camera inside the palette.** It stays in its own window.
- **Spelling suggestions in Define Word.**
- **File Search extras:** Finder tags, folder search inside Finder or Open dialogs, Tab into a
  folder, play controls for audio and video, and two Quick Look shortcuts. File Search finds files,
  and that's all.
- **Fetch website icons for Quicklinks.** **Instead:** pick an icon yourself.

## Things macOS or other apps won't let us do

- **Move windows between Spaces.** macOS 27 removed the tool for this. Space switching uses a
  workaround that **may have to go** in a future release.
- **Use the Spotlight shortcut.** macOS won't give a shortcut Spotlight owns to another app.
  **Instead:** turn off Spotlight's shortcut in System Settings first.
- **Read selected text in every app.** Many apps and websites don't share it.
- **Another app's Quick Look plugin takes your keys** (like Obsidian's).
- **Duplicate images with Clop running.**
- **One-time-password extensions that paste for you.**

## Not now, but maybe later

These are on hold, not ruled out.

- **Contacts search**, as a separate plugin.
- **Open files in a Finder replacement.**
- **Emoji names in the picker.** Long names don't fit yet.
- **Keep any window on top.**

---

## Before you open a request

1. Check this page first.
2. Ask yourself: does it keep Tinycast simple, light and fast?
3. If Raycast already does it well, Raycast may suit you better.
4. Want it anyway? Fork Tinycast and make it yours.

Thank you for your ideas and your understanding.
