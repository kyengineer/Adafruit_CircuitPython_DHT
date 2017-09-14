
Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-dhtlib/badge/?version=latest
    :target: https://circuitpython.readthedocs.io/projects/dhtlib/en/latest/
    :alt: Documentation Status

.. image :: https://badges.gitter.im/adafruit/circuitpython.svg
    :target: https://gitter.im/adafruit/circuitpython?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge
    :alt: Gitter

CircuitPython support for the DHT11 and DHT22 temperature and humidity devices.

Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Usage Example
=============

Hardware Set-up
---------------

The DHT11 and DHT22 devices both need a pull-resistor on the data signal wire.  
This resistor is in the range of 1k to 5k.  Please check your device datasheet for the 
appropriate value.

Basics
------

Of course, you must import the library to use it:

.. code:: python

    import adafruit_dhtlib

The DHT type devices use single data wire, so import the board pin

.. code:: python

    from board import <pin>

Now, to initialize the DHT11 device:

.. code:: python

    dhtDevice = dht.DHT11(<pin>)

OR initialize the DHT22 device:

.. code:: python

    dhtDevice = dht.DHT22(<pin>)

Read temperature and humidity
----------------------------

First you must request data from the device by calling measure(). 
If measure() return 0 then the sensor data is ready

.. code:: python

    success = dhtDevice.measure()

Now get the temperature value and the humidity value

.. code:: python

    temperature = dhtDevice.temperature
    humidity = dhtDevice.humidity

If the measure() returns something other than 0, retry calling measure()
after 1/2 second.  Note that temperature and humidity values are not valid after
measure() returns something other than 0.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_dhtlib/blob/master/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.

API Reference
=============

.. toctree::
   :maxdepth: 2

   api