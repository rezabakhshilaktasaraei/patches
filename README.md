# patches — Accessibility Tracker

This repository is a fork of [desktop-app/patches](https://github.com/desktop-app/patches) that tracks **accessibility-related Qt patches** used by Telegram Desktop. These patches backport or adjust Qt behavior so that Windows screen readers (via UI Automation) report the correct roles, names, states, and relationships. All changes listed here are merged into the official upstream repository.

> This is part of the broader [Telegram Desktop Accessibility](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible) effort.

## Merged Pull Requests

| PR | Title | Author | First Telegram Desktop Release |
|---|---|---|---|
| [#233](https://github.com/desktop-app/patches/pull/233) | Use RTTI to get class name for accessibility | [@ilya-fedin](https://github.com/ilya-fedin) | [v6.2.5](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.2.5) |
| [#245](https://github.com/desktop-app/patches/pull/245) | Add patch: fix toggle state notification for all checkable widgets | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | [v6.6.0](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible/releases/tag/v6.6.0) |
| [#253](https://github.com/desktop-app/patches/pull/253) | Don't require an action interface for UIA SelectionContainer | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | Unreleased |
| [#254](https://github.com/desktop-app/patches/pull/254) | Backport UIA selection + orientation interfaces for custom tab controls | [@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei) | Unreleased |
| [#257](https://github.com/desktop-app/patches/pull/257) | Use RTTI in automation ID on Qt 5, too (accessibility commit within "Fixes") | [@ilya-fedin](https://github.com/ilya-fedin) | Unreleased |

## What Was Added

- **RTTI-based class name for accessibility** — Qt derives the accessibility class name via RTTI so screen readers see the real widget class instead of a generic one; a follow-up extends the same approach to the UI Automation automation id on Qt 5 ([#233](https://github.com/desktop-app/patches/pull/233), [#257](https://github.com/desktop-app/patches/pull/257))
- **Toggle state notification fix** — Corrects state-change notifications so all checkable widgets (checkboxes, toggles) announce checked/unchecked updates to screen readers ([#245](https://github.com/desktop-app/patches/pull/245))
- **UIA SelectionContainer without an action interface** — Allows a control to act as a UI Automation selection container even when it exposes no action interface, needed for custom-painted tab strips ([#253](https://github.com/desktop-app/patches/pull/253))
- **Backported selection & orientation interfaces** — Backports `QAccessibleSelectionInterface` (UIA tab/selection state) and `QAccessibleAttributesInterface` (UIA orientation) from Qt 6 to Qt 5.15 so custom tab controls report selection and orientation correctly ([#254](https://github.com/desktop-app/patches/pull/254))

## Related Repositories

- [tdesktop-accessible](https://github.com/rezabakhshilaktasaraei/tdesktop-accessible) — Main tracker with releases
- [lib_ui](https://github.com/rezabakhshilaktasaraei/lib_ui) — Accessible widget framework
- [lib_base](https://github.com/rezabakhshilaktasaraei/lib_base) — Screen reader detection

## Contributors

- **[@rezabakhshilaktasaraei](https://github.com/rezabakhshilaktasaraei)** (Reza Bakhshi Laktasaraei) — toggle state notification fix and the UIA selection/orientation backports ([#245](https://github.com/desktop-app/patches/pull/245), [#253](https://github.com/desktop-app/patches/pull/253), [#254](https://github.com/desktop-app/patches/pull/254)).
- **[@ilya-fedin](https://github.com/ilya-fedin)** (Ilya Fedin) — RTTI-based class name and automation id for accessibility ([#233](https://github.com/desktop-app/patches/pull/233), [#257](https://github.com/desktop-app/patches/pull/257)).

## License

Same license as the official [desktop-app/patches](https://github.com/desktop-app/patches).
