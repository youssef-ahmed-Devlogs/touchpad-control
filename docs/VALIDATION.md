# Validation notes

Release: **3.1.0**

## Verified on the development Windows laptop

| Check | Result |
| --- | --- |
| Fresh app defaults | English; System theme; tray icon off; Ctrl + Alt + F9. |
| Tray preference | Enabling creates a visible notification icon; disabling disposes it. Both values survive reopening. The interface switch was also exercised. |
| Startup preference | On writes the background startup entry; Off removes it. |
| Language | Arabic and English selections persist. |
| Appearance | System light/dark transitions and manual overrides passed automated tests. |
| Layout | 24 combinations checked: 2 languages × 2 themes × 3 pages × minimum/default sizes; no horizontal overflow. |
| Touchpad control | Main switch disabled the touchpad; global shortcut enabled it again. |
| Shortcut editing | Saved a replacement shortcut, used it to toggle off/on, then restored the original shortcut. |
| Window close | Closing hides the window and leaves one process running. |
| Reopen | Opening again restores the existing window without a duplicate process. |
| Uninstall from touchpad OFF | Enabled the touchpad; removed the app, preferences, and startup entry. |
| Fresh reinstall after uninstall | Setup completed successfully and selected automatic startup by default. |
| Background startup from touchpad OFF | Enabled the touchpad successfully. |

User preferences were restored after testing and the touchpad was left enabled.

## Scope and limits

These results are from the development laptop, not a fleet of different laptop models or a freshly reinstalled operating system. The clean-install test removed this app and its preferences, then reinstalled it on the existing Windows installation. The background-startup test launched the same background mode used at sign-in; it did not reboot the computer.

The notification icon lifecycle was checked; a complete manual walkthrough of every tray-menu action is not recorded here. The tray menu uses the same open, toggle, and exit handlers as the app.

Layout-boundary checks do not establish compatibility with every display scale, accessibility setting, Windows version, or third-party touchpad driver. This release is unsigned.
