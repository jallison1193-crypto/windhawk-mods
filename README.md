# Windhawk mods

My mods for [Windhawk](https://windhawk.net/), the customization platform for
Windows.

## Taskbar Smart Auto-Hide

[`mods/taskbar-smart-auto-hide.wh.cpp`](mods/taskbar-smart-auto-hide.wh.cpp)

One mod for taskbar auto-hide on Windows 11. It combines three existing mods
and adds a fix for apps like ChatGPT.

**When to hide**

- Only when a window is maximized
- When a window is maximized or touches the taskbar
- Always, like the Windows setting
- Never

**Keep it shown**

- While the desktop is focused (Win+D or clicking the desktop)
- On a monitor with no open windows

**Reveal speed**

- Slide at a custom speed, or use instant, fade, elastic, bounce, slide + fade
  or overshoot animations
- Separate show and hide delays

**Notifications**

- A flashing taskbar button no longer keeps the taskbar open forever. It
  re-hides after a delay you choose.

**Maximized apps that look fullscreen**

Some apps, ChatGPT among them, size their maximized window to exactly fill the
screen. Windows mistakes them for fullscreen apps, takes the taskbar out of the
always-on-top layer, and reveals it behind the app. Moving the cursor down then
only shows a resize cursor. This mod keeps the taskbar on top while the active
window is maximized, so it appears as expected. True fullscreen apps such as
videos and games aren't affected.

As a backup, an edge watcher reveals the taskbar directly when the cursor
touches its edge while another window covers it.

### Install

1. In Windhawk, click **Create a New Mod**, then **Begin coding**.
2. Replace the template with the contents of
   [`taskbar-smart-auto-hide.wh.cpp`](mods/taskbar-smart-auto-hide.wh.cpp).
3. Click **Compile Mod**, then **Exit Editing Mode**.

Disable "Taskbar auto-hide when maximized", "Taskbar Auto-Hide Instant Show"
and "Better Taskbar Autohide" first, since they hook the same taskbar
functions.

Tested on Windows 11 25H2 (build 26220).

### Credits

This mod is built on:

- [Taskbar auto-hide when maximized](https://github.com/m417z/my-windhawk-mods)
  by m417z (GPL-3.0). This mod is a fork of it.
- [Taskbar Auto-Hide Instant Show](https://github.com/Bo0ii/windhawk-mods) by
  Bo0ii (Apache-2.0). Animation and timer code.
- Better Taskbar Autohide by [Cirn09](https://github.com/Cirn09) (MIT).
  Notification flash handling.

## License

[GPL-3.0](LICENSE). The file header lists the licenses of the adapted code.
