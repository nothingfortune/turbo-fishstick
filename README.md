# MoErgo Glove80 Custom Configuration for ZMK

## Scope of Expected Behaviors

glove80_mapping

custom keyboard mapping and related behaviors tied to glove80 by MoErgo

https://zmk.dev/docs/development/local-toolchain/setup

https://my.glove80.com/

Expected Behaviors

//// Basic Behaviors ////

1) Tapped
2) Tapped and Held
3) Held
4) Double Tapped
5) Triple Tapped


//// Dynamic Macros ////

Tap dance 2 taps dynamic macro - use case: just another hotkey and ability to assign macro

Tap dance 3 taps dynamic macro - use case: just another hotkey and ability to assign macro

Keypress and 2 key dynamic macro - use case: mainly cmd or windows shortcuts

Keypress and 3 key dynamic macro - use case: mainly cmd or windows shortcuts

2 Keypress combined on single Keypress dynamic macro - use case: configurable shortcuts for various programs

3 Keypress combined on single Keypress dynamic macro - use case: configurable shortcuts for various programs 

Tap dance 2 taps dynamic macro - use case: mapping additional commands to existing keys without changing layers. more than likely tied in to other dynamic macros via nesting

tap dance 3 taps dynamic macro - use case: mapping additional commands to existing keys without changing layers. more than likely tied in to other dynamic macros via nesting

//// Layer Modifiers ////

Toggle layer on tap, momentary layer on hold - use case: layer layer shift with ability to both toggle and completely shift layers

//// Smart Features ////

Smart Shift with double tap command - use case: osx basic shortcuts with autoshift. Intent is to have the default smartshift with built in cmd without having to move keys. Default shortcuts for items like copy paste without having to move from the key

Smart shift with double tap rctrl - use case: win basic shortcuts with autoshift. Intent is to have the default smartshift with built in cmd without having to move keys. Default shortcuts for items like copy paste without having to move from the key

//// Basic Functionality ////

Mouse click(s) - use case: Existing. Code pulled from existing lib.

Mouse scrolls - use case: Existing. Code pulled from existing lib.

Keypress and momentary layer on hold - use case: layer keystrokes with ability to temporarily 

Select and hold scroll arrows windows - use case: press and hold arrow keys and select entire words for delete or copy

Double tap arrow to select to beginning of line - use case:

Select and word scroll arrows OSX - use case: press and hold arrow keys and select entire words for delete or copy

    Shortcut Command

Select and word scroll arrows WIN Specific - use case: press and hold arrow keys and select entire words for delete or copy

    Shortcut Command (Windows): 

Sentence case?

Backspace with double tap hold deleting entire word - use case: OSX Specific - delete single characters on press, long press backspace entire words


Backspace with double tap hold deleting entire word - use case: OSX Specific - delete single characters on press, long press backspace entire words

    Shortcut Command(Windows): fn + Del


layer 0 (mac)
layer 1 (windows)
layer 2 (symbols)
layer 3 (numpad)
layer 4 (movement)
layer 5 (gaming)
layer 6 (magic)
layer 7 (lower)

https://my.glove80.com/#/layout/user/90978696-a856-477e-b54b-2fbe60e731c7

zmkfirmware/zmk#1474

## Resources
- The [official MoErgo Glove80 Support](https://moergo.com/glove80-support) web site. Glove80 documentation and other technical resources.
- The [official MoErgo Discord Server](https://moergo.com/discord). Instant conversations with other Glove80 users.

- The [official ZMK Documentation](https://zmk.dev/docs) web site. Find the answers to many of your questions about ZMK Firmware.
- The [official ZMK Discord Server](https://discord.gg/8cfMkQksSB). Instant conversations with other ZMK developers and users. Great technical resource!

- The [official Glove80 ZMK Distribution](https://github.com/moergo-sc/zmk). Repositiory for ZMK firmware customized for Glove80. 
 
## Instructions
1. Log into, or sign up for, your personal GitHub account.
2. Create your own repository using this repository as a template ([instructions](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template)) and check it out on your local computer.
3. Edit the keymap file(s) to suit your needs
4. Commit and push your changes to your personal repo. Upon pushing it, GitHub Actions will start building a new version of your firmware with the updated keymap.

## Firmware Files
To locate your firmware files and reflash your Glove80...
1. log into GitHub and navigate to your personal config repository you just uploaded your keymap changes to.
2. Click "Actions" in the main navigation, and in the left navigation click the "Build" link.
3. Select the desired workflow run in the centre area of the page (based on date and time of the build you wish to use). You can also start a new build from this page by clicking the "Run workflow" button.
4. After clicking the desired workflow run, you should be presented with a section at the bottom of the page called "Artifacts". This section contains the results of your build, in a file called "glove80.uf2"
5. Download the glove80.uf2
6. Flash the firmware to Glove80 according to the user documentation on the official Glove80 Glove80 Support website (linked above)

Your keyboard is now ready to use.
