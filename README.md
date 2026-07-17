# Veylance

Ever wanted to conveniently change your scooter’s configured speed without pulling out your phone, opening the manufacturer’s app, and navigating through several menus?

**Veylance** is an Android application that lets you quickly apply selected scooter settings through a simple interface, background triggers, or external automation tools.

> [!WARNING]
> Veylance is an unofficial third-party application. It is not affiliated with, endorsed by, or supported by Segway-Ninebot or any scooter manufacturer.

**Using an iPhone? Use [Velo](https://github.com/derotti77/Velo)!**

## Features

* Configure the maximum speed for:

  * ECO mode
  * DRIVE mode
  * SPORT mode
* Configure the motor start speed
* Optionally set the scooter voice volume to 0% when connecting
* Save and reuse scooter pairing information
* Automatically reconnect when a connection attempt fails
* Optional persistent Bluetooth connection for faster setting changes
* Trigger settings without opening the app:

  * Shake the phone
  * Press Volume Up and Volume Down
  * Send an Android intent from Tasker or another automation app
* Light, dark, and system themes

## Supported scooters

Veylance is currently designed and tested for the:

* **Segway-Ninebot Max G3**

Support for other models is not guaranteed.

Do not attempt to use the application with an unsupported scooter unless you understand the risks.

## Installation

Download the latest APK from the GitHub Releases page.

Before installing it, Android may ask you to allow installations from your browser or file manager.

After installation:

1. Turn on Bluetooth.
2. Open Veylance.
3. Select your scooter.
4. Enter or confirm the scooter serial number.
5. Pair the scooter when requested.
6. Select the settings you want to apply.
7. Press **Connect, apply settings, disconnect**.

When pairing for the first time, Veylance may ask you to press the scooter’s power button.

## Background triggers

### Shake phone

When enabled, shaking the phone applies the configured settings.

This uses an Android foreground service and displays a persistent notification while active.

### Volume Up + Volume Down

When enabled, pressing Volume Up and Volume Down triggers Veylance.

This feature requires enabling the Veylance Accessibility Service in Android settings.

The Accessibility Service is used only to detect the configured volume-button combination.

### Always Stay Connected

The experimental **Always Stay Connected** option keeps an authenticated Bluetooth connection open to the scooter.

This can make subsequent setting changes faster, but may:

* Increase battery usage
* Keep a persistent notification visible
* Prevent another scooter app from connecting at the same time
* Reconnect automatically when the connection is interrupted

## External Intent API

Veylance can be triggered from Tasker, MacroDroid, ADB, or another Android application.

Enable **Allow external intent calls** inside Veylance first.

### Intent action

```text
network.sga.dev.scooterhackingcontributions.veylance.android.APPLY_SPEED
```

### Package

```text
network.sga.dev.scooterhackingcontributions.veylance.android
```

### Target

```text
Broadcast Receiver
```

An optional `speed` extra may be supplied to override the saved SPORT-mode speed.

When no speed extra is supplied, Veylance applies the settings currently saved in the app.

## Permissions

Depending on the enabled features, Veylance may request:

* Bluetooth scanning and connection permissions
* Nearby devices permission
* Notification permission
* Vibration access
* Foreground service access
* Accessibility Service access
* Permission to ignore battery optimizations

Not every permission is required for basic manual operation.

## Safety and legal notice

Changing a scooter’s configured speed may:

* Violate local traffic laws
* Make the scooter illegal to operate on public roads
* Void the manufacturer’s warranty
* Increase braking distance
* Increase motor, controller, and battery temperatures
* Increase the risk of injury or component failure

You are responsible for checking the laws and regulations applicable in your location.

Only operate modified settings on private property or in locations where doing so is legal and safe.

Veylance does not bypass the physical limitations of the scooter. Entering an unusually high value does not mean the scooter can safely or physically reach that speed.

## Disclaimer

This software is provided without warranty.

The developer is not responsible for:

* Damage to a scooter, phone, battery, motor, controller, or other equipment
* Personal injury
* Data loss
* Loss of warranty
* Fines, legal consequences, or regulatory violations
* Problems caused by unsupported scooter models or firmware versions

Use Veylance entirely at your own risk.

## Privacy

Veylance does not require an account.

Scooter information and application settings are stored locally on the device.

The application does not need to send scooter credentials to a remote server to perform its core functions.

## Contributing

Bug reports, testing results, and contributions are welcome.

When reporting a problem, include:

* Phone model
* Android version
* Scooter model
* Scooter firmware version, when known
* Veylance version
* A clear description of what happened
* Relevant logs with sensitive information removed

Do not publicly post pairing keys, private signing keys, passwords, or other credentials.

## Author

Made with ❤️ by [SchattenWolf2008@sga.network](https://sga.network)
