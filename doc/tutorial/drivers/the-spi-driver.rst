The SPI Driver
--------------------

Many small computers like the Raspberry Pi have an Serial Peripheral Interface
or SPI bus, which allows the machine to directly control LEDs.

This driver controls this


**Example**: The ``driver`` section of a project using Serial communication

.. code-block:: yaml

    driver:
      typename: .serial
      ledtype: LPD8806
      c_order: GRB
      gamma: 2.5
      device_id: 2


Serial Driver Fields
=========================


``ledtype``
  LED protocol type - see below for details

``dev``
  Serial device address/path. If not set, the first serial device
  found will be used.

``c_order``
  RGB color order - see below for details

``gamma``

``spi_speed`` (default ``2``)
  SPI datarate for applicable LED types, in MHz

``restart_timeout`` (default ``3``)
  Seconds to wait between reconfigure reboot and reconnection attempt

``device_id``
  Device ID to connect to.  If not set, connect to the first device ID
  found on the device

hardwareID (default ``'1D50:60AB'``)
   A valid USB VID:PID (vendor id : product id) pair.  The default is the
   VID:PID pair for the AllPixel

baudrate (default ``921600``)
  Baud rate to connect to serial device




``ledtype``
================

The Serial Driver already understands many brands and varieties of RGB LED
strips out of the box.  They are identified by a string called the ``LEDTYPE``.

+ APA102
+ APA104
+ LPD1886
+ LPD8806
+ NEOPIXEL
+ P9813
+ SK9822
+ SM16716
+ TM1803
+ TM1804
+ TM1809
+ UCS1903
+ WS2801
+ WS2811
+ WS2811_400
+ WS2812
+ WS2812B
+ GENERIC  # No processing

If you don't see your brand of LED strip, just ask the `mailing list
<https://groups.google.com/d/forum/maniacal-labs-users>`_\ . It's very likely
that it's either a variant of one of the above, or we can figure out how to
handle it.


Color Order
===============

The ``c_order`` field sets the order of the color RGB components in the  LED
strips - which are unfortunately different between different brands.





Basic Usage
===============





[TODO-API: embed or point to generated documentation for serial/driver.py]

LEDTYPE
^^^^^^^

The Serial Driver needs to have an LEDTYPE set to identify the LED chipset and
hardware.  This must be one of these values: [TODO-API: point to or embed generated
documentation for ledtype.py]

.. bp-code-block:: footer

   shape: [61, 13]
   animation:
     typename: $bpa.matrix.MathFunc
     palette: bold
     func: 8
