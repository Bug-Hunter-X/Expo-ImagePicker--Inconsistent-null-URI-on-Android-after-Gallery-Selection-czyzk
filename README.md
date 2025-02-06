# Expo ImagePicker Null URI Bug on Android

This repository demonstrates a bug encountered when using Expo's ImagePicker with a custom camera component on Android.  After selecting an image from the device's gallery, the returned URI is sometimes null, leading to app crashes or errors. This behavior is inconsistent and device-dependent.

## Bug Description

The `ImagePicker.launchImageLibraryAsync()` function from Expo's `expo-image-picker` library sometimes returns an object with a `null` URI property, even when an image is successfully selected. This occurs seemingly randomly across different Android devices.

## Reproduction

1. Clone this repository.
2. Run `npm install`.
3. Run the app on an Android device (the issue is less likely to be reproduced on iOS).
4. Open the image picker and select an image from your gallery.
5. Observe that in some cases, the app may crash or display an error due to the null URI.

## Solution

The solution involves adding more robust error handling and asynchronous handling to check that the URI is valid and handle the case where it's not.  See `bugSolution.js` for an example of how to properly check for null and handle the situation gracefully.