# GlitchBob LPC

Voltage glitching automation tool to break protection on NXP LPC microcontrollers.

The glitch circuit can be controlled by a Raspberry Pi Pico or other low-cost development board.

## TODO

These are issues identified in the prototype:

- The potentiometer polarity is swapped.
    - 0v should be fully counterclockwise, and +VCC should be fully clockwise.
- The potentiometer is upside down.
    - Rotate the footprint 180 degrees.
- No good place to put the rubber feet.
    - Move through-hole components or find smaller feet.
- Still has some wasted surface area with traces spread out.
    - Change 8-pin header pinout to optimize routing.
    - Move traces closer together to prevent ground plane islands.
- `R3` is a bit too close to the serial port.
    - Move `R3` so it is more easily reachable for assembly.

And this is a wish-list for improvements:

- Replace 8-pin header with Raspberry Pi Pico header footprint.
- Add a 7-segment display for low-voltage measurement.
    - Use Raspberry Pi Pico's ADC.
    - 7-Segment driver can be inexpensively built with:
        - [`74LVC244A`](https://www.mouser.com/ProductDetail/Nexperia/74LVC244APW118?qs=me8TqzrmIYXA4kTVlk0VcA%3D%3D) - Octal buffer/line-driver
        - [`74LV4052`](https://www.mouser.com/ProductDetail/Nexperia/74LV4052PW118?qs=me8TqzrmIYXk9tz3ZPOozg%3D%3D) - 4-channel analog multiplexer/demultiplexer
        - [`LTC-5723HR`](https://www.mouser.com/ProductDetail/Lite-On/LTC-5723HR?qs=WxFF5lh7QM2ytJdX1EhJKQ%3D%3D) - 4-digit 7-segment display with common cathode
