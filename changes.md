##Release Notes:
0.1.3
* #25 fix to issue handling password change
* Updates crypto dependency to version `com.scottyab:aes-crypto:0.0.3` to help with issue #18

0.1.2
* #22 Internal changed to local reference to shared pref file and keys from static, as this made it impossible to have multiple secure preference files.
* #15 fixed typos, specifically `destroyKeys()`
* New constructor where you can supply your own keys to aid with issue #18.
* Additional unit tests

0.1.1
* Fixed build issue referencing 'com.scottyab:aes-crypto' dependency (previous pointed to snapshot repo)
* Minor tweek to build file so doesn't error if you don't have the sample app signing config

0.1.0
This release is a major refactor of the guts of secure prefs, which is *Not backwards compatible* with 0.4.0 and older versions _yet!_. So if you have an existing app using this don't upgrade. I'll be looking to add migration into a later release.

* uses a new and stronger [Crypto library](https://github.com/scottyab/java-aes-crypto) under the hood
* includes PRNG fixes that effects JellyBean devices as per [google dev blog article](http://android-developers.blogspot.nl/2013/08/some-securerandom-thoughts.html)
* supports password based key generation so the key is not persisted
* change password supported
* updated sample app
* removed test project and added tests as part of main project
* refactored library project to standard gradle structure
* published to maven central/added github release


0.0.4
* Gradle support thanks @yelinaung
* Fix for OnPreferenceChanged listener @richardleggett

0.0.3

* Added test Project
* Updated sample ready for playstore upload

0.0.2

* Added methods to get/set strings un-encrypted
* Added backup PBKDF function in case PBKDF2WithHmacSHA1 not supported
* Refactored code to make it easier to change the AES mode and PBKDF function.
* Increased iterations of PBKDF from 1000 to 2000.

0.0.1

* Initial import to github I've modified the project structure.
* Included the Android base64 class so library can be used by Android 2.1+.
* Enhanced the sample project dumps current prefs to illustrate the fact they are stored encrypted and Base64 encoded.