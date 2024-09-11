Sunaku's Keymap v36 for the "Glorious Engrammer" 🧑‍🚀🚀✨
- Intro & setup: https://github.com/sunaku/glove80-keymaps
- Release notes: https://github.com/sunaku/glove80-keymaps/releases/tag/v36
- Documentation: https://sunaku.github.io/moergo-glove80-keyboard.html#layers
- Discord forum: #glorious-engrammer channel in https://www.moergo.com/discord

Summary:
This release adds OS-native compose shortcuts as an alternative to Unicode character entry, fixes mod-morph nesting in the World layer, introduces consistent placement of editing keys on left-hand layers and home row mods on right-hand layers, adds one-handed usage to Mouse and System layers, improves Alt+Tab usability, updates my personal fine-tuned timings (custom difficulty level), and much more!

Changes:
- Base layer: revert thumb cluster arrows back to v34 for harmony with `<>` on Number layer.
- Set T4+T5 as ZMK combo for quicker Alt+Tab activation; move Number layer back under Cursor layer (like v34); remove chord shim on Number layer.
- DIFFICULTY_LEVEL no longer masks user-overrides defined at the very top of the "Custom Defined Behaviors" text box.
- DIFFICULTY_LEVEL also affects typing streaks now: Difficulty level 1: 300ms, 2: 250ms, 3: 200ms, 4: 150ms, 5: 100ms.  Thanks to @Mathijs-Bakker for helping test this feature.
- Bilateral layers: allow bilateral layers to be deleted, independent of `ENFORCE_BILATERAL`.
- Bilateral layers: fix compilation errors when `ENFORCE_BILATERAL` isn't defined.  Thanks to ~alizdavoodi on Discord for reporting this issue: https://discord.com/channels/877392805654306816/1193051200938049546/1213135160254533682
- Cursor layer: add Spacegram operators (Tab, Space, Enter, etc.) mirroring the Symbol layer.
- Number layer: reuse Cursor layer's left hand layout for selection and Spacegram operators.  Thanks to @AsafMah for requesting this feature in issue #6.
- Function layer: reuse Cursor layer's left hand layout for selection and Spacegram operators.
- Emoji layer: move smiling face into home block, pushing laughing faces just outside of it.
- Emoji layer: add shifted pairs for star sparkles and hand gestures in right thumb cluster.
- Emoji layer: tap RALT then U instead of RA(U) for WinCompose compatibility in en-GB locale.  Thanks to ~KG on Discord for reporting this issue and its solution: https://discord.com/channels/877392805654306816/1193051200938049546/1219403753275527219 and https://discord.com/channels/877392805654306816/1193051200938049546/1219414866939609340
- Emoji layer: fix Emoji input in macOS by converting UTF-32 into UTF-16 (see PR #7). Thanks to @viduranga for contributing this patch!
- Symbol layer: fill in right hand's central index finger column for non-Engrammer layouts.
- World layer: add `#define WORLD_USE_COMPOSE` setting to enable the use of OS-native shortcuts (instead of Unicode) for international characters on World layer.
- World layer: shield macros from mod-morph tree modifiers so that World+Ctrl+Shift+A can type Ä reliably with OS-native compose sequences. Thanks to the legendary @urob for guidance on solving this problem: https://discord.com/channels/719497620560543766/813882537436905552/1211574316794257418
- World layer: fix ability to type "¡" using WinCompose, which would previously emit "ă1\n".  Thanks to @frankbenoit for finding this workaround: https://github.com/samhocevar/wincompose/issues/323
- World layer: group consonants (ç ß ñ) into a single compound key (on letter C in Engram).
- World layer: move currency key to traditional shift key position on the left pinky finger.
- World layer: add µ micro sign (Greek letter MU) to bottom left corner (Magic key's location).
- Lower layer: fill in factory base layer &trans keys; restore Grave on left pinky "shift".
- Lower layer: swap Gaming & Typing toggles to reflect T6+T3 combo for Gaming/Base toggle.
- Mouse layer: reuse Symbol layer's right hand layout for home row mods; add one-handed keys.
- System layer: reuse Symbol layer's right hand layout for home row mods; add one-handed keys.
- System layer: add Context Menu key to both sides of the keyboard for cross & one-handed use, with mnemonics in Engram layout -- T: sTop/lock, S: sleep, N: shutdowN, R: RGB, M: monitor(screen)shot, F: scroll(freeze)lock, P: Pause.
- Adjust my preferred timing thresholds on the `#define DIFFICULTY_LEVEL 0` custom level, maintaining 80ms difference between holding time and typing streak timeouts:
  - Decrease HOMEY_HOLDING_TIME from 270ms to 240ms.
  - Decrease HOMEY_STREAK_DECAY from 250ms to 160ms.
  - Increase INDEX_HOLDING_TIME from 170ms to 180ms.
  - Decrease INDEX_STREAK_DECAY from 150ms to 100ms.
- README: update references to sections in Glove80 User Guide.  Thanks to @Nullthetical for contributing this patch.
- README: Ubuntu users need to add the Universe repository in order to install graphviz.  Thanks to ~ErrorCode on Discord for the "Unable to locate package graphviz" solution: https://discord.com/channels/877392805654306816/1193051200938049546/1210816321181196368
- README: add Factory and Magic layer diagrams; finish Lower layer diagram; add lots of documentation.

What are "Home Row Modifiers" (HRM)?
====================================

"Home Row Modifiers" (HRM) is a technique where modifier keys (like Ctrl, Alt, Shift, etc.) are mapped to keys located on the home row. The idea behind HRM is to reduce the need for finger stretching and movement away from the home row, thereby increasing typing efficiency and reducing strain. These HRM keys behave normally when tapped, sending their assigned character (such as the letter “A”) to the computer. But when held, they become modifier keys, sending their assigned modifier (such as Alt or Shift) to the computer instead.

Why not use the ZMK &mt behavior?
=================================

Although ZMK has built-in &mt (mod-tap) behavior [1] for implementing HRM, &mt does not always give the HRM experience. The main issue with HRM is the unintended activation of modifiers. The key to a good implementation of HRM is the correct differentiation between the typist's intention to type the home row key and the intention to type the modifier. Unfortunately the simplistic implementation of ZMK's &mt is not always up to the task.

What is a better HRM solution?
==============================

ZMK offers hold-tap capability [3] on which &mt is built. Hold-tap however is much more tuneable and powerful. To use ZMK's hold-tap capabilty. you will need to use the Custom Behavior capability of Glove80 Layout Editor.

Sunaku has developed a highly refined highly-refined HRM implementation using ZMK's hold-tap capability, extending Miryoku’s work. It is documented in his article "Taming home row mods with bilateral combinations" [3]. It looks deceptively simple, but the underlying theory is very complex. This layout is the embodiment of Sunaku's HRM implementation.

How to customize the HRM?
=========================

Everyone is different, with different typing speed and preferences. As a first step, set the DIFFICULTY_LEVEL to 1 (novice level, requiring 500ms of holding time to activate home row mods) in the Custom Defined Behaviors text box of the Glove80 Layout Editor:

	#define DIFFICULTY_LEVEL 1

Then, as you gain experience using home row mods and become more comfortable with them, you can gradually increase the level up to 5 (expert level).  Or better yet, set the value to 0 (custom level) and configure the timing thresholds directly (via similar #define settings) to suit your preferences.  You can even configure these home row mods individually, per finger!

Another area of configuration is the order of home row mods.  For instance, this example keymap uses the "GACS" order, where:
- "G" means `LGUI`, which is the Win key in Windows, Cmd in macOS, Super in Linux.
- "A" means `LALT`, which is the Alt key in Windows and Linux, Option in macOS.
- "C" means `LCTL`, which is the Control key in Windows, macOS, and Linux alike.
- "S" means `LSFT`, which is the Shift key in Windows, macOS, and Linux alike.

However, you can choose differently by simply editing the custom "&<left|right>_<finger> <mod> <key>" expression of each home row mod key you want to change and setting the first argument to your desired modifier keycode.  For example, suppose that you wanted to assign RSFT (right shift) on the right pinky finger:

	&right_pinky RSFT SEMI

Finally, if you wish to remove certain home row mods, such as AltGr on the ring finger's upper row key, simply change the key from being a Custom key to a regular &kp key in the Glove80 Layout Editor.

Credits
=======

This Glove80 layout, including this notes, draws heavily from Sunaku's "Taming home row mods with bilateral combinations" [3]. Part of this notes is copied directly from his article.

Resources
=========

[1] https://zmk.dev/docs/behaviors/mod-tap ZMK documentation on mod-tap
[2] https://zmk.dev/docs/behaviors/hold-tap ZMK documentation on hold-tap
[3] https://sunaku.github.io/home-row-mods.html "Taming home row mods with bilateral combinations" by Suraj N. Kurapati aka @sunaku
[4] https://github.com/sunaku/glove80-keymaps Sunaku's "Glorious Engrammer" keymap
[5] https://www.moergo.com/files/layout-editor-user-guide.pdf Glove80 Layout Editor Guide