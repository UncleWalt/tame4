TAME 4: TwinCAT ADS Made Easy
=============================


Introduction
------------

TAME is JavaScript library created for an easy and comfortable access to the TwinCAT ADS WebService. The name is an 
acronym for „TwinCAT ADS Made Easy“ and stands also for „taming“ the complexity of ADS and AJAX requests. 
Originally a „wast product“ from the programming of a browser based visualisation for my home, it has become a (in my
opinion) useful little piece of software and I hope it will help others who want to develop their own visualisations. 
I'm not a professional programmer (in fact this is my first "serious" project), so don't get upset when you look at 
the code.

The library allows to exchange data with a TwinCAT PLC without any knowledge of ADS. The browser connects to the 
webserver running on the PLC device and the ADS commands are wrapped in AJAX/SOAP requests. Have a look at the
manual and the examples for more information.

If you want to know more about the basics of the access to the ADS WebService visit the Beckhoff website
[here] (http://infosys.beckhoff.com/content/1033/tc3_adswebservice/html/webservice_intro.htm).

TAME 4 became necessary because the synchronous XMLHttpRequest outside of workers is in the process of being removed
from the web platform. It's already deprecated in most browsers and will be removed over the years. TAME 3 uses
synchronous requests for fetching the symbol information and the TPY-file from the PLC. With asynchronous requests 
became a new 'onReady' function nessecary and the process of starting the client is different to TAME 3. If you want
to replace V3.x with V4 you have to change the way of starting your scripts! 


Features
--------

- Methods for read and write access to single variables, variable blocks, arrays and structures exists.

- Supported data types: BOOL, BYTE, WORD, DWORD, USINT, SINT, UINT, INT, UDINT, DINT, TIME, TOD, DT, DATE, REAL, LREAL
  and STRING. Bounds checking is implemented but can be switched off.

- Sum commands are supported (read and write).

- Handles are supported. Access to single elements of structures and arrays and also internal variables and parameters
  of FB's is possible.

- The TPY-file generated by TwinCAT can be used. The file contains information about the PLC, the symbols and the data 
  types. With these informations one no longer have to set NetId, port or alignment. Reading structures from the PLC the
  JavaScript objects can be built automatically without the need of structure definitions. Access to single elements of
  structures and arrays and also internal variables and parameters of FB's is possible even without using handles.

- Special „type“ named INT1DP: It's an INT variable in the PLC, but in JavaScript the variable is of type float with 
  1 decimal place (i.e. a value of 568 in the PLC is 56.8 in JavaScript).
  
- Built-in conversion of date and time values to formatted strings.

- REAL values can be rounded to a desired number of decimal places.

- Add prefix and suffix to values for a user defined output.

- Automatic structure padding for exchanging data with TwinCAT 2 and ARM-based devices (i.e. CX90xx) or with TwinCAT 3.

- Export/import functions for symbols and data types to/from JSON. Intented for the use with Tasker (Android).

- Force synchronous XMLHttpRequests for easier scripting in Tasker.


Requirements
------------

Requried is a running ADS WebService, look at the [Beckhoff Infosys] (http://infosys.beckhoff.com) for more information 
about the installation.


License
-------

TAME is dual licensed under the MIT and the GPLv3 license. 

Beckhoff® and TwinCAT® are registered trademarks of Beckhoff Automation GmbH.


