
The following are Requirements and User Stories for a Hyprland configuration and Widgets, meaning a complete System built on Hyprland. 
The important thing is: Not everything has to be built from the ground up. Existing tools may be implemented, for example for the Spotlight search. 
Highly customized features like the dynamic island however should be built individually. Even for those features existing projects should be used for inspiration or may even be forked. 

## Functions 
*User Story Style*
"I" means the user of the OS.

- **US#01** *Wallpaper picker in Dynamic Dock*: 
  I Want to be able to change my Wallpaper by cycling through the options like a carousel via the arrow keys. The menu should be in the dynamic island. 
  KS: SUPER+Shift+W
- **US#02** *Wallpaper-based Dynamic Colors*: 
  I Want the colours of my distro, including primary and secondary accent colors to be set automatically according to my Wallpaper. A change in wallpapers should change them too, however they should be set for a wallpaper (meaning that the same wallpaper should have the same colors switching off or on to it).
- **US#03** *Custom Color Mode*: 
  I want to toggle a "custom color mode". Meaning via KS the colors change to a custom set primary and secondary color. If that mode is toggled, the colors should not change with the wallpaper but stay the custom. The colors should be set in the settings app via a visual color picker. 
  KS (to switch between wallpaper colors and custom colors): SUPER+Shift+B
- **US#04** *Spotlight-like search*: 
  I want to quick search (primarily Apps) and open them via Return/Enter. The search shall always feature my newest installed apps. The ability to search files may later be added (like spotlight). The speed and accuracy of finding apps shall be the highest priority. The icons of the App shall be shown correctly amongside the name. 
  KS: SUPER+SPACE (may be changed to Ctrl+SUPER+SPACE)
- **US#05** *Keyboard Shortcut menu*: 
  I want to be able to open a Keyboard shortcut menu, that shows all the keyboard shortcuts. It should be searchable. Keyboard shortcuts should also be able to be changed here and shall be updated. The keys should not only be in plain text, but rather feature a key-style (like a square with rounded edges, or a rounded rectangle for larger keys like SUPER or Ctrl)
  KS: CTRL+SUPER+K
- **US#06** *Mac-like App Dock*: 
  I want a lower dock to feature all open Apps alongside pinned Apps. Open Apps should feature a Dot beneath. Like Mac, the Dock should also feature a shortcut to the Downloads folder. Right-Clicking an App should open a small menu with options like "Close App", "Pin/Unpin App", and similar. Clicking an App should jump to it's window. The dock should be able to be toggled (On/Off) and be animated with a quick morph in/out animation and the setting (shown or hidden) shall be remembered. The color of the dock shall also be dynamic. The size should be rezisable (like Mac's Dock) by dragging.
  KS (to show/hide): CTRL+SUPER+D 
- **US#07** *Terminal Emulator Kitty*: 
  I want Kitty to be my Terminal Emulator and it should be configured exactly like ML4W (My Linux 4 Work) - except it should show the Arch ASCII Art instead of the ml4w Logo. It shall also open automatically via Hypr's standard KS: SUPER+Return
- **US#08** *Power And Efficiency Modes*:
  I Want to switch between Power Modes that both change Power Consumtion and Fan Noise. They should affect Auto Sleep/Hibernate as well as CPU+GPU Performance and the Fan curve. However they should not change brightness. A quick menu should pop up scrollable with Arrow-Up and Arrow-Down which features names and emojis to the left. 
  KS (to show menu): Shift+SUPER+P
- **US#09** *Brightness Control*
  I Want to control the Brightness using the corresponding Function Keys (F-Keys) or in the Control-Centre. When using F-Keys the Dynamic Island should pop and show the current brightness as a slider and a percentage next to it. In the Control Centre I should be able to drag without a grid. 
- **US#10** *Volume Control*
  I Want to control the Volume using the corresponding Function Keys (F-Keys) or in the Control-Centre. When using F-Keys the Dynamic Island should pop and show the current brightness as a slider and a percentage next to it. When using F-Keys it should snap to a 5%-step size grid. When holding shift while clicking the F-Keys the step size should be 2%. When dragging in the control centre there should be no grid. 
- **US#11** *Cursor Acceleration*
  Using the Trackpad should have a cursor acceleration that is a copy of the natural feeling of the Macbook. The mouse acceleration should not affect an external mouse, but only the built in trackpad. In case the standard configuration does not resemble a good feeling, the smoothness should be editable in the settings app. Pointer speed should also be configurable in the settings app, seperate for external mouse and internal trackpad. 
- **US#12** *Now Playing Media*
  

## Dynamic Island like Dock
*A pill-like Element centered on the upper dock inspired by the Dynamic Island and "Alclove" (the Dynamic Island for Mac). It expands and pops up for multiple functionalities with the corresponding menu when pressing the kb-shortcut of the corresponding function.*

Requirements:
- The Dynamic Dock should expand smoothly to the appropriate size of the content, depending on the function
- The Dynamic Dock should ease out smoothly when clicked outside of it or the action is marked "done", or after 10 sec of inactivity (meaning not interacting with it). Interaction with it, meaning clicking or dragging bars via cursor or arrow keys, should reset the 10 seconds

The Dynamic Island hosts the following User Stories:
#01, #09, #10

## Quick Menus 
*Centered Quick menus with arrow-key navigation that serve multiple functionalities and pop up when pressing the corresponding keyboard-shortcut of the function.*


## Settings App
*A widget that behaves like the settings app, which is meant to host settings for every of the custom widgets and functionality as well as some basic device settings.*

## Standard Upper Dock
*The Standard upper Dock is always shown and features a basic overview and features. It shows standard Information (like WiFi, Bluetooth, Time and Date) and it's elements are clickable (like a click on WiFi opens the WiFi menu. It also features a Mac-Inspired Control-Centre which hosts multiple settings.*


