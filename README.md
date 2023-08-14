# Flutter-Dart-The-Complete-Guide-Maximilian-Course-Note

Feel free to PR to improve or update this course note.

# Contents

- [Section 2 Flutter & Dart Basic | - Getting a Solid Foundation [Roll Dice App]](#section-2-flutter-and-dart-basic-getting-a-solid-foundation-roll-dice-app)
- [What's included in ISI-Survey](#whats-included-in-isi-survey)

# Section 2 Flutter and Dart Basic Getting a Solid Foundation Roll Dice App

## New project app

- The folder with the platform name contains platform-related files.
- Typing there’s no need to change anything flutter will make changes accordingly
- The files and folder in that platform name will also be important when we publish our app to those platforms.
- test folder is the folder for testing our main application test
- .file_name contained the configuration
- metadata about internal stuff and metadata of our project.
- analysis_options.yaml is a flutter file that displays warnings and errors in our code.
- app_name.iml is contained metadata info for building the app.
- The different between pubspec.yaml and pubspec.lock is pubspec.yaml Declare the dependencies and configuration for a flutter project. On the otherhand pubspec.lock Locks the versions of the dependencies used in the project.

## Dart to Machine Code

- The dart code isn’t understood by any of the platforms when executing
  - This means it first needs to be parsed and compiled to machine code finally it executes in the user devices.

## Starting From Scratch: Function

- The first thing and most essential is `runApp()` it’s job is get app up and running or show some user interface on the screen.

```dart
void main() {
  runApp();
}
```

## Importing Feature From package

- In the last lecture, we see the error in runApp why? because we didn’t import the runApp code that was written behind the scenes.
- To solve this we first make sure there is flutter dependency in the pubspec.yaml file then import it in the main.dart file

```dart
import 'package:flutter/material.dart';

void main() {
  runApp();
}
```

## How Flutter Apps Start's

- main function is a special function that doesn’t need to be called.
- It’s the starting point of the app.

## Understand Widget

- We talk about function and widget
  - Some functions need argument some do not.
  - So if we didn’t put anything in the runApp as an argument how could runApp know what to display
  - That is why we put something called a widget or widget tree for runApp to display
  - And flutter uses that widget to build UI and Flutter come with various kinds of widgets like layout, and components, or we can even build a custom widget.

## Using the first widget & passing value to a function

- We have to use at least two core basic widgets in `runApp()` to display some UI
  - First `MaterialApp()` It looks like a function but it’s not it’s a class. When we pass `MaterialApp()` to `runApp()` as an argument we tell the flutter we use `MaterialApp()` widget on the screen.
  - We then need to pass another widget in `MaterailApp()` but, we’ll look at that in the next lesson.
