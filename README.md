Espruino Web IDE
======================

A Web-Based VT100 Serial Terminal - designed for writing code on microcontrollers that use the Espruino JavaScript interpreter (http://www.espruino.com) - but useful for a bunch of other stuff too!

[![ScreenShot](https://raw.github.com/espruino/EspruinoWebIDE/master/extras/screenshot.png)](http://youtu.be/Fjju_QhzL-c)
[![ScreenShot](https://raw.github.com/espruino/EspruinoWebIDE/master/extras/screenshot2.png)](http://youtu.be/Fjju_QhzL-c)

This is a Chromium Web App that uses chome.serial to access your PC's serial port. You can download it from the Chrome Web Store: https://chrome.google.com/webstore/detail/espruino-serial-terminal/bleoifhkdalbjfbobjackfdifdneehpo

It implements basic VT100 terminal features (up/down/left/right/etc) - enough for you to write code using the Espruino. You can also use the right-hand pane to write JavaScript code on the PC, and can then click the 'transfer' icon to send that code directly down the Serial Port.

Currently, this isn't as good as it could be. So please, if you have some free time, help us improve this!

Installing From Chrome Web Store
----------------------------

* Install the [Chrome Web Browser](https://www.google.com/intl/en/chrome/browser/)
* [Go Here](https://chrome.google.com/webstore/detail/espruino-serial-terminal/bleoifhkdalbjfbobjackfdifdneehpo) to find the app in the Chrome Web Store
* Click 'Install'
* Click 'Launch App'

Installing from GitHub
-------------------

* Install the [Chrome Web Browser](https://www.google.com/intl/en/chrome/browser/)
* Download the files in EspruinoWebIDE to a directory on your PC (either as a [ZIP File](https://github.com/espruino/EspruinoWebIDE/archive/master.zip), or using git)
* Click the menu icon in the top right
* Click 'Settings'
* Click 'Extensions' on the left
* Click 'Load Unpackaged Extension'
* Navigate to the EspruinoWebIDE Directory and click Ok
* Job Done. It'll now appear as an app with the 'Unpacked' banner so you can tell it apart from the normal Web IDE. You can start it easily by clicking the 'Launch' link on the extensions page, or whenever you open a new tab.

Permissions
----------

This web app requires the following permissions:
* *Serial port access* : So that it can access the Espruino board via USB/Serial
* *Webcam access* : So that when you click the little person icon in the top-right of the terminal window, you can overlay the terminal on a live video feed

Using
-----

* Run the Web app
* If you've only just plugged your device in, press the refresh button
* In the Top Left, make sure the correct serial port is chosen (usually: Highest COM# number on Windows, tty.usbmodem/ttys000 on Mac, ttyUSB0/ttyACM0 on linux)
* Click the 'Play' (connect) button
* Click in the left-hand terminal window and start typing away!

Using (advanced)
--------------
* Click the button with left/right arrows to transfer the text (or graphics) in the right-hand pane to Espruino
* Click the button with a picture frame to switch between graphical and text views (the code will not auto-update)
* To copy on the left-hand side, click and drag over the text to copy (text is copies when you lift the mouse button)
* To paste, press **Ctrl + V**
* **Ctrl + Space** starts auto-complete

Features that would be good to implement
-----------------------------------
* Better auto-detection of the correct serial device
* Detection of serial disconnect (and auto reconnect)
* Make everything prettier/easier to use
* Implement more of Espruino as Blockly Blocks
* Actually toggle WebCam on and off (currently it can only turn on)
* Blockly Blocks to turn red if they can't do certain things (for instance a pin that won't do analog)
* Codeacademy-style online tutor that talks you through the first few steps of coding on Espruino
* Keep code on right in sync with graphical editor
* Being able to choose a filename for Save, so you don't have to change the name each time
* Storing blockly blocks locally so they are remembered on startup
* Auto-complete that knows more about Espruino's API

Nice but not required at all
-------------------------
* More complete VT100 terminal emulation
* Option to use a Baud rate other than the default 9600
* Use the Mozilla sound API to fake a serial port over the Audio Link for non-Chrome web browsers

Contributing
------------

Contributions are welcome - especially if they make the Web IDE easier to use and more reliable!

### Code Style

 * Please stick to a [K&R style](http://en.wikipedia.org/wiki/1_true_brace_style#K.26R_style) with no tabs and 2 spaces per indent
 * Filenames should start with a lowerCase letter, and different words should be capitalised, not split with underscores
 
### Code Outline

 * Core functionality goes in `js/core`, Plugins go in `js/plugins`. See `plugins/_examplePlugin.js` for an example layout
 * Plugins/core need to implement in init function, which is called when the document (and settings) have loaded.
 * Annoyingly, right now plugins still have to be loaded via a `<script>` tag in `main.html`    
