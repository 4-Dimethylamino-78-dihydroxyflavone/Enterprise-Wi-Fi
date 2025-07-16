# Enterprise Wi-Fi
This updated Android NVIDIA Shield TV does not by default have a user interface for setting up Enterprise Wi-Fi networks. These networks, use the [Extensible Authentication Protocol (EAP)](https://en.wikipedia.org/wiki/Extensible_Authentication_Protocol), a framework for authenticating your device with the Wi-Fi network by providing both a username and password.

These types of networks are common at businesses, where only particular users should be accessing the network, or at universities where content is audited.

As stated above, though there is no user interface for connecting to these networks, the system has APIs for programmatically connecting. To aid those in the situations above, this app provides a useful interface for making connections.

There is another app that fulfills this need on Android TV, although I have found a number of issues with how it works.

## Features
* Connection details can be saved and updated
* Automatically fills in fields where possible
* Shows logs of connection status to show you progress is happening
* Can display a QR code of the network to connect your other devies

<img src='https://github.com/ITVlab/Enterprise-Wi-Fi/blob/master/promo/device-2016-09-07-012808.png?raw=true' />

<img src='https://github.com/ITVlab/Enterprise-Wi-Fi/blob/master/promo/device-2016-09-07-012756.png?raw=true' />

### Western Sydney University preset
When the SSID **Western Wifi** is selected, the app automatically configures the connection using PEAP and MSCHAPV2 with the domain `westernsydney.edu.au`. It will also apply the `DigiCertGlobalRootG2` CA certificate if available in the system store. If the certificate is missing you will be prompted to install it from **Settings → Security → Install certificates**.

### Android 10 and newer
Starting with Android 10, third-party apps can no longer directly add Wi‑Fi configurations. On these versions the app now uses **network suggestions**. After you press Connect you will be asked to confirm the suggestion in the system Wi‑Fi settings.
## Building
To build with recent Android Studio, update the Gradle wrapper and plugin. This repo now targets SDK 34 and uses Gradle plugin 8.1.0. Run `./gradlew assembleDebug` to create an APK.

