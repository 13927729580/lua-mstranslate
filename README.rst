===============
lua-mstranslate
===============

:Author: Arezqui Belaid and Joshua Patten
:Description: Lua wrapper for text-to-speech synthesis with Microsoft Translate
:Contributors: `list of contributors <https://github.com/newfies-dialer/lua-mstranslate/graphs/contributors>`_
:License: MIT


Lua Microsoft Translate Wrapper
-------------------------------

lua-mstranslate is a library to produce a text-to-speech file using `Microsoft Translate`_ web services.

In order to utilize this service you must sign up for Microsoft Translator service and register an application. More information on creating a Microsoft account is located at the `getting started with Microsoft Translator API`_ page.


Quickstart
----------

::

    MSTranslate = require "mstranslate"

    CLIENT_ID = 'XXXXXXXXXXXX'
    CLIENT_SECRET = 'YYYYYYYYYYYYYY'
    SERVICE_URL = 'http://api.microsofttranslator.com/V2/Http.svc/Speak'

    tts_mstranslate = MSTranslate:new(CLIENT_ID, CLIENT_SECRET, SERVICE_URL, directory)

    TEXT = "This is a test of the Microsoft Translate text to speech service."
    LANG = 'EN'
    tts_mstranslate:prepare(TEXT, LANG)
    output_filename = tts_mstranslate:run()

    print("Recorded TTS = "..output_filename)


Features
--------

* Produce text to speech in different languages

Dependencies
------------

There are a few dependencies: md5, lfs and lua-curl.
We use this version of lua curl : http://msva.github.com/lua-curl/

To install md5 and lfs::

    luarocks install md5
    luarocks install luafilesystem


To install lua-curl::

    cd /usr/src/
    wget https://github.com/msva/lua-curl/archive/master.zip -O lua-curl.zip
    unzip lua-curl.zip
    cd lua-curl-master
    cmake . && make install


Feedback
--------

Feedback are more than welcome, post bugs and feature requests on github:

http://github.com/newfies-dialer/lua-mstranslate/issues


Extra information
-----------------

Newfies-Dialer, an Open Source Voice BroadCasting Solution, uses this module to synthetize audio files being play to the end-user.
Further information about Newfies-Dialer can be found at http://www.newfies-dialer.org

This module is built and supported by Star2Billing : http://www.star2billing.com

Similar library in Python : http://github.com/newfies-dialer/python-mstranslate


Source download
---------------

The source code is currently available on github. Fork away!

http://github.com/newfies-dialer/lua-mstranslate


.. _Microsoft Translate: http://www.microsoft.com/en-us/translator/translatorapi.aspx
.. _getting started with Microsoft Translator API: https://www.microsoft.com/en-us/translator/getstarted.aspx
