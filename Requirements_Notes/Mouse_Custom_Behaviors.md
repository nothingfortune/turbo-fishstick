

//////////////////////////////////////////////////////////////////////////
//
// Mouse keys (control mouse via keyboard) -- requires PR23 beta firmware:
// select "community.pr23.mouse-keys" from the drop-down menu located at
// Glove80 Layout Editor > Settings > Advanced Settings > Firmware Version
//
// - https://github.com/moergo-sc/zmk/pull/23
// - https://gist.github.com/krissen/dd27082e7ab0575619c7a31f4d2ec7ae
// - https://github.com/zmkfirmware/zmk/compare/main...urob:zmk:mouse-3.2
//
//////////////////////////////////////////////////////////////////////////

//
// MOUSE_MOTION_DELAY defines how long to wait (milliseconds) before starting
// to move the mouse pointer.
//
#ifndef MOUSE_MOTION_DELAY
#define MOUSE_MOTION_DELAY 0
#endif

//
// MOUSE_MOTION_ACCELERATION_EXPONENT sets how the mouse pointer accelerates:
//
// acceleration exponent 0: uniform speed
// acceleration exponent 1: uniform acceleration
// acceleration exponent 2: uniform jerk
//
#ifndef MOUSE_MOTION_ACCELERATION_EXPONENT
#define MOUSE_MOTION_ACCELERATION_EXPONENT 1
#endif

//
// MOUSE_MOTION_TIME_TO_MAXIMUM_SPEED defines how long to wait (milliseconds)
// before the mouse pointer speed is suddenly boosted to the maximum value.
//
#ifndef MOUSE_MOTION_TIME_TO_MAXIMUM_SPEED
#define MOUSE_MOTION_TIME_TO_MAXIMUM_SPEED 300
#endif

//
// MOUSE_MOTION_MAXIMUM_SPEED defines how quickly the mouse pointer can move.
//
#ifndef MOUSE_MOTION_MAXIMUM_SPEED
#define MOUSE_MOTION_MAXIMUM_SPEED 1800
#endif

//
// MOUSE_SCROLL_DELAY defines how long to wait (milliseconds) before starting
// to move the mouse pointer.
//
#ifndef MOUSE_SCROLL_DELAY
#define MOUSE_SCROLL_DELAY 0
#endif

//
// MOUSE_SCROLL_ACCELERATION_EXPONENT sets how the mouse pointer accelerates:
//
// acceleration exponent 0: uniform speed
// acceleration exponent 1: uniform acceleration
// acceleration exponent 2: uniform jerk
//
#ifndef MOUSE_SCROLL_ACCELERATION_EXPONENT
#define MOUSE_SCROLL_ACCELERATION_EXPONENT 1
#endif

//
// MOUSE_SCROLL_TIME_TO_MAXIMUM_SPEED defines how long to wait (milliseconds)
// before the mouse pointer speed is suddenly boosted to the maximum value.
//
#ifndef MOUSE_SCROLL_TIME_TO_MAXIMUM_SPEED
#define MOUSE_SCROLL_TIME_TO_MAXIMUM_SPEED 300
#endif

//
// MOUSE_SCROLL_MAXIMUM_SPEED defines how quickly the mouse wheel can scroll.
//
#ifndef MOUSE_SCROLL_MAXIMUM_SPEED
#define MOUSE_SCROLL_MAXIMUM_SPEED 10
#endif
/*HACK*/};
#if __has_include(<zmk/events/mouse_tick.h>)
    // ==== MOUSE-KEY <section begins> ====
    #define ZMK_MOUSE_DEFAULT_MOVE_VAL MOUSE_MOTION_MAXIMUM_SPEED
    #define ZMK_MOUSE_DEFAULT_SCRL_VAL MOUSE_SCROLL_MAXIMUM_SPEED
    #include <dt-bindings/zmk/mouse.h>
    &mmv {
      delay-ms = <MOUSE_MOTION_DELAY>;
      acceleration-exponent = <MOUSE_MOTION_ACCELERATION_EXPONENT>;
      time-to-max-speed-ms = <MOUSE_MOTION_TIME_TO_MAXIMUM_SPEED>;
    };
    &msc {
      delay-ms = <MOUSE_SCROLL_DELAY>;
      acceleration-exponent = <MOUSE_SCROLL_ACCELERATION_EXPONENT>;
      time-to-max-speed-ms = <MOUSE_SCROLL_TIME_TO_MAXIMUM_SPEED>;
    };
    // ==== MOUSE-KEY <section ends> =====
#else
    #define mkp none
    #define mmv none
    #define msc none
    #define LCLK
    #define MCLK
    #define RCLK
    #define MB1
    #define MB2
    #define MB3
    #define MB4
    #define MB5
    #define MB6
    #define MB7
    #define MB8
    #define MOVE_UP
    #define MOVE_DOWN
    #define MOVE_LEFT
    #define MOVE_RIGHT
    #define SCRL_UP
    #define SCRL_DOWN
    #define SCRL_LEFT
    #define SCRL_RIGHT
#endif
/*HACK*//{