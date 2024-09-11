# MoErgo Glove80 Custom Configuration for ZMK

![MoErgo Logo](moergo_logo.png)

This repo is the official ZMK configuration of the MoErgo Glove80 wireless split contoured keyboard. Use it to develop your own keymap and easily build your own ZMK firmware to run on your Glove80.

**NOTE: You can also customize the layout of your Glove80 keyboard with the Glove80 Layout Editor webapp. For most users Glove80 Layout Editor is the recommended and simpler option. More information is available at the official MoErgo Glove80 Support site (see resources below).**

These steps will get you using your keymap on your keyboard in the fastest time possible. It uses the GitHub Actions feature to build your firmware online.

If you are looking to dig deeper into ZMK and develop new functionality, it is recommended to follow the steps of installing ZMK as found on the official ZMK documentation site (linked below).

## Scope of Expected Behaviors

//// Dynamic Macros ////

Tap dance 2 taps dynamic macro - use case:

tap dance 3 taps dynamic macro - use case:

kp and 2 key dynamic macro - use case:

kp and 3 key dynamic macro - use case:

2 kp combined on single kp dynamic macro - use case:

3 kp combined on single kp dynamic macro - use case:

Tap dance 2 taps dynamic macro - use case:

tap dance 3 taps dynamic macro - use case:

//// Layer Modifiers ////

Smart Shift with double tap command - use case: osx basic shortcuts

Smart shift with double tap rctrl - use case: win basic shortcuts

toggle layer on tap, momentary layer on hold - use case:

//// Smart Features ////

//// Basic Functionality ////

mouse click(s) - use case:

mouse scrolls - use case:

keypress and momentary layer on hold - use case:

select and hold scroll arrows windows - use case:

double tap arrow to select to beginning of line - use case:

select and word scroll arrows OSX - use case:

sentence case?

backspace with double tap hold deleting entire word - use case:

layer 0 (mac) layer 1 (lower) layer 2 (lower) layer 3 (lower) layer 4 (lower) layer 5 (lower)

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
