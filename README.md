# POKEDEX

An example of React Native application with Redux state manager

## Screenshots

![ScreenShot](/screenshot/pokedex.jpg)

## PokeApi

PokeAPI is used to obtain all the images and information of pokemon.

https://pokeapi.co/

## Running project

After starting your virtual device in you local :

```
$ react-native run-android
```

Above comment will also start Metro-Bundler which loads dependency graph of the project
If you want to restart it :

```
$ npm start react-native
```

## Bugs I ran into when setting up the project
When setting up the project, I ran into quite a few bugs
The first was a conflict with the target SDK. Lower SDK's don't support runtime permissions as mentioned here (https://stackoverflow.com/questions/45163008/android-failed-to-finalize-session-26-new-target-sdk-22-doesnt-support-runti)
The solution is to change the targetSdkVersion specified in the ./android/app/build.gradle file
For this project I had to update it to version 28

Unfortunately the newer SDK version doesn't come with clearTextSupport which causes the error "Unable to load script from assets index.android.bundle"
As discovered here (https://stackoverflow.com/questions/44446523/unable-to-load-script-from-assets-index-android-bundle-on-windows) the solution is to add the line android:usesCleartextTraffic="true" to the AndroidManifest.xml file

Additional errors that may be related to the incompatible SDK version included:
java.io.IOException: Could not delete path '_____' 
This source (https://stackoverflow.com/questions/50798533/java-io-ioexception-could-not-delete-path-c-users-nirma-language-app-build-ge) suggests that it does not have permissions to delete the temporary folder. They recommend deleting it manually which worked for me. This happened several times so don't worry if you have to delete multiple folders

Unable to resolve module 'redux' ... Module does not exist in the module map
I'm still not sure why this happened. I checked package.json and redux was listed as a dependency
After some searching (https://github.com/facebook/react-native/issues/18931) a comment here mentioned installing redux fixes their issue
running 'npm install redux' fixes the issue

## Adding Google fonts for android app
The .tff files were obtained from Google fonts.
The list of fonts in this project are:
  Aldrich-Regular
  AntDesign
  Entypo
  EvilIcons
  Feather
  FontAwesome
  Foundation
  Ionicons
  MaterialCommunityIcons
  MaterialIcons
  Octicons
  PressStart2P-Regular
  Roboto_medium
  rubicon-icon-font
  SimpleLineIcons
  Zocial

## Demonstration
![](/screenshot/Demonstration.gif)

## This project is originally done by: Sercanesen
This is a fork of Sercanesen's pokedex project. I take no credit in their creative work.