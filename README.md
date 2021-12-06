# Social Stream
Consolidate your live social messaging streams

- Supports live automated two-way chat messaging with Facebook, Youtube, and Twitch
- Includes a "feature chat" overlay, selectable via the dockable dashboard
- Supports bot-commands and automated chat responses, with custom logic plugin support.

Social Stream makes use of VDO.Ninja's data-transport API to stream data securely between browser windows with extremely low latency and all for free!

### Video walk-thru

https://youtu.be/w4jbZS5QgJs

### To install

This extension should work with Chromium-based browser on systems that support webRTC. This includes Chrome, Edge, and Brave.

Currently you must download, extract, and load the browser extension manually.  It is not available yet in the browser's web store.

Link to download: https://github.com/steveseguin/social_stream/archive/refs/heads/main.zip

Once extracted into a folder, you can go here to load it: chrome://extensions/

![image](https://user-images.githubusercontent.com/2575698/142858940-62d88048-5254-4f27-be71-4d99ea5947ab.png)

Ensure you have Developer Mode enabled; then you can just load the extension via the load unpacked button and selecting the folder you extracted the fiels to.

![image](https://user-images.githubusercontent.com/2575698/142857907-80428c61-c192-4bff-a1dc-b1a674f9cc4a.png)

You're ready to start using it! 

Please note that you will need to manually update the extension to access newer versions; it currently does not auto update.

### To use

Open Twitch or Youtube "Pop out" chat; or just go to your Facebook Live chat while connected to Ethernet or WiFi. You must not minimize or close these windows, but they can be left in the background or moved to the side.

Then, press the Social Stream chrome extension button and ENABLE streaming of chat data. (Red implies disabled. Green is enabled)

![image](https://user-images.githubusercontent.com/2575698/142856707-0a6bc4bd-51b4-4cd0-9fa3-ef5a1adfcbf7.png)

Using the provided two links, you can manage the social stream of chat messages and view selected chat messages as overlays.

![image](https://user-images.githubusercontent.com/2575698/142935393-4ca90418-a645-45e3-8e37-f4884e16457a.png)

You can hold ALT on the keyboard to resize elements in OBS, allowing you to crop the chat stream if you want to hide aspects like the time or source icon.

Clicking on a message will have it appear in the overlay link. You can press the clear button to hide it or use the &showtime=20000 URL option added to the overlay page to auto-hide it after 20-seconds (20,000 ms).

![image](https://user-images.githubusercontent.com/2575698/142854951-fe1f34c9-0e24-495f-8bfe-a33ab69fa7cb.png)

There is a &darkmode option, but the default is white, for the dock.

![image](https://user-images.githubusercontent.com/2575698/142855585-45c11625-c01c-4cc0-bfe0-cde4aed5fc44.png)

A good resolution for the overlay is either 1280x222 or 1920x220; you can specify this in the OBS browser source.  You can edit the style of the overlay using the OBS CSS style input text box.

![image](https://user-images.githubusercontent.com/2575698/142855680-74f6055d-7b79-4e9a-ae7d-909c7f677a24.png)

If using the automated chat response options, like auto-hi, you must ensure the Youtube/Twitch/Facebook chat input options are enabled and that you are able to send a chat message. Manually entering a chat message into the pop-out window or into the Facebook live chat area first can help ensure things are working are intended, else automated message may not be sent.

### Customize

- &lightmode (Enables the dark-mode for the chat stream)

- &scale=2 (doubles size/resolution of all elements)
- &notime (hides the date in the chat stream)
- &hidesource (hides the youtube/twitch/fb icons from the stream)
- &compact (Removes the spacing between name and message)

To customize the overlay, you can edit the CSS, in either the OBS browser source style-sheet section, or by editing the and using the index.html file.

- &showtime=20000 (auto-hides selected messages after 20s)
- &showsource (shows the youtube/twitch/fb icons next to the name)

#### Auto responding / custom actions

You can create your own custom auto-responding triggers or other actions by including a custom.js file.

Included in the code is the custom_sample.js file, which you can rename to custom.js to get started. Included in it is the `&auto1` trigger, which  auto responds "1" to any message that is also "1".  You need to add `&auto1` to the dock's URL to activate it.

It's fairly easy to modify the `auto1` trigger to do whatever you want. You can also customize or removee the URL-parameter trigger needed to activate it.

### Togglable Menu Commands 

These are some generic auto-reply commands that can be toggled on/off via the extension's menu. They do not need a custom.js file to work

- !joke  (tells a random geeky dad joke)
- hi  (Welcomes anyone who says "hi" into chat)

### Hotkey (MIDI / Streamlabs) support

There's a toggle to enable MIDI hotkey support. This allows a user to issue commands to the extension when active, such as issue predefined chat messages to all social destinations.

The hotkeys can be issued via MIDI, which can be applied to a Streamdeck also via a virtual MIDI device. The MIDI actions available currently include:

Using Control Change MIDI Commands, on channel 1:

- command 102, with value 1: Say "1" into all chats
- command 102, with value 2: Say "LUL" into all chats
- command 102, with value 3: Tell a random joke into all chats
	
![image](https://user-images.githubusercontent.com/2575698/144830051-20b11caa-ba63-4223-80e1-9315c479ebd6.png)

The MIDI plugin can be found in the Streamdeck store pretty easily. If using Windows, you can find a virtual MIDI loopback device here: https://www.tobias-erichsen.de/software/loopmidi.html  There are some for macOS as well.

Feedback welcomed

### Support

You can find me on discord over at https://discord.vdo.ninja (steve), offering free support in channel #chat-overlay-support 

Feedback and feature requests are welcomed
