BitID implementation in PHP
===========================

PHP implementation of [BitID project/draft](https://github.com/bitid/bitid).

Based on the work of [scintill/php-bitcoin-signature-routines](https://github.com/scintill/php-bitcoin-signature-routines) and using [PHPECC classes](https://github.com/mdanter/phpecc)

Licensed under the Apache License, Version 2.0 (unless it's not compatible with the license of works used)

**Bitcoin Authentication Open Protocol**

Pure Bitcoin sites and applications shouldn’t have to rely on artificial identification methods such as usernames and passwords. BitID is an open protocol allowing simple and secure authentication using public-key cryptography.

Classical password authentication is an insecure process that could be solved with public key cryptography. The problem however is that it theoretically offloads a lot of complexity and responsibility on the user. Managing private keys securely is complex. However this complexity is already being addressed in the Bitcoin ecosystem. So doing public key authentication is practically a free lunch to bitcoiners.

**The protocol is described on the following BIP draft and is open for discussion :**

https://github.com/bitid/bitid/blob/master/BIP_draft.md

Demo
====

http://vps.madriguera.me/bitid-php/ (very basic, be gentle)


Installation
============
* Create a MySQL database, import struct.sql into it.
* Configure database information and server url in config.php


Notes
=====
* I tried to create a flexible library, some  work needs to be done to adapt it to your project

* Pure PHP implementation, no need of **bitcoind** (maybe add support for bitcoind in the future)

* GMP PHP extension is required (most shared hostings don't have it, another reason to implement bitcoind support)

* **isMessageSignatureValidSafe** is the same function as **isMessageSignatureValid** but the later with throw different exceptions on fail, while the former only return true/false (only for lazy programmers that don't handle exceptions)

* By default, it will only allow 1 user by IP to **try** login at the same time (once a user is logged, another user could start the login process), this example could be modify to allow several (no need to modify BitID)




