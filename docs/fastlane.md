# Fastlane Summary

![](images/fastlane_summary.png)

</br>

## Installation

Make sure you have the latest version of the Xcode command line tools installed:

```
xcode-select --install
```

Install _fastlane_ using
```
[sudo] gem install fastlane -NV
```
or alternatively using `brew cask install fastlane`

</br>

## Setup

Requirement: Open the Appfile and replace the package name with the application's package name.

</br>

## Available Actions
### Android
#### android compile
```
fastlane android compile
```
Compile debug and test sources
#### android lint
```
fastlane android lint
```
Execute Android lint
#### android assemble
```
fastlane android assemble
```
Assemble source and test APKs
#### android unit_test
```
fastlane android unit_test
```
Execute unit tests
#### android instrumentation_test
```
fastlane android instrumentation_test
```
Execute instrumentation test on Emulator

</br>

## Fastlane Plugin

The Fastlane template uses a plugin to create and boot up an Android emulator. Once the emulator is running, the instrumentation tests are executed. Installation of the plugin can be found in the Pluginfile.

To use the plugin in the fastlane template. Add the lane with the following configuration:

```
automated_test_emulator_run(
    AVD_setup_path: "fastlane/avd_setup.json",
    AVD_recreate_new: false,
    AVD_clean_after: false,
    gradle_task: "connectedDebugAndroidTest")
```

The automated_test_emulator_run configuration requires the setup json file. The avd_setup.json defines the properties of the emulator that will be used. To change the emulator type, modify or create a new avd configuration JSON file and refer it into the automated_test_emulator_run configuration in the lane.

----

More information about fastlane can be found on [fastlane.tools](https://fastlane.tools).
The documentation of fastlane can be found on [docs.fastlane.tools](https://docs.fastlane.tools).