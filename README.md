# Flutter-Dart-The-Complete-Guide-Maximilian-Course-Note

Feel free to PR to improve or update this course note.

# Contents

- [Section 2 Flutter & Dart Basic | - Getting a Solid Foundation [Roll Dice App]](#section-2-flutter-and-dart-basic-getting-a-solid-foundation-roll-dice-app)

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

## Positional & Named Arguments

- Now we’ll look at what to put in the MaterialApp() widget.
  - We can put positional parameter
  - We can put a name parameter.
- So in the `MaterialApp()` we can put `home:` parameter followed by the `Text()` Widget provided by the Flutter team.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Text(),
  ));
}
```

## Combining Multiple Widgets

- In the `Text()` Widget there is a positional parameter that is required.
- So in the `Text()` Widget we must put some `string` value there.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Text("Hello, World"),
  ));
}
```

## Understanding “const” Values

- const helps Dart improve the run time performance.
- Because it reuses the value instead of duplicating another object value again.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MaterialApp(
    home: Text("Hello, World!"),
  ));
}
```

## Building More Complex Widget Trees

- To make our app beautiful we need a scaffold widget inside the above widgets.
- `MaterialApp()` Widget is a root widget for setting up the app.
- Scaffold takes an argument like body.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    const MaterialApp(
      home: Scaffold(
        body: Center(child: Text("Hello, World!")),
      ),
    ),
  );
}
```

## Understanding Value Types

- Dart is a type-safe language
  - All value you’re working with is a certain type.
    - `MaterialApp()` has the type of MaterialApp and Object and Widget.
  - Why the type existed?
    - The answer is some classes only accept a certain type.

## Configuring Widget & Understanding Objects

- There are lots more arguments that are accepted by the Scaffold widget beside `body:` among those is **`backgroundColor:`** if we ctrl + space we can see Color? the? mean we know it can be null.
- Object

## Working with “Configuration Objects” (Non-Wiget Objects)

- We introduced to new Widget called Container which accepts the argument like decoration:

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: Scaffold(
          body: Container(
        decoration: BoxDecoration(
          gradient: LinearGradient(
            colors:
          ),
        ),
        child: Center(
          child: Text("Hello World"),
        ),
      )),
    ),
  );
}
```

## Generics, Lists & Adding Gradient Colors

- Generics is a type that can be used in different types like lists. So by specifying the type in the <> we explicitly tell which type we will be using.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MaterialApp(
    home: Scaffold(
      body: Container(
        decoration: const BoxDecoration(
          gradient: LinearGradient(colors: [
            Color.fromARGB(255, 26, 2, 80),
            Color.fromARGB(255, 45, 7, 98)
          ]),
        ),
        child: const Center(
          child: Text("Hello VireakRoth!!"),
        ),
      ),
    ),
  ));
}
```

## How To Configure Widgets & Objects

- Ctrl + Space is a great way to see what value we can put.

- Another way is to google what we wanted to use.

## Practice Styling Text

- I personally use ctrl + space to see what I can do in a widget
- In my case, I want to style the text so I ctrl + space in the Text() widget.

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      home: Scaffold(
        body: Container(
          decoration: const BoxDecoration(
            gradient: LinearGradient(
              colors: [
                Color.fromARGB(255, 26, 2, 80),
                Color.fromARGB(255, 45, 7, 98)
              ],
              begin: Alignment.topLeft,
              end: Alignment.bottomRight,
            ),
          ),
          child: const Center(
            child: Text(
              "Hello VireakRoth!!",
              style: TextStyle(color: Colors.white, fontSize: 28),
            ),
          ),
        ),
      ),
    ),
  );
}
```

## Onwards to Custom Widgets: Why do you need them?

- As our source code becomes larger and larger we can’t comprehend what is going on if we put in one file. So what we can do is separate it into multiple files and reuse it.
- To separate the Widget we use the class keyword. We’ll see what it is in the next lecture.

## Understand Classes

- Widget → Object → Data Structure in Memory.
- So Object is a very crucial concept in Dart
- Those Objects are instantiated from Classes. Classes are like a blueprint for an Object.
- So in Object, there are two main components in it which are Data and Functionality.
- Therefore we also define our custom widgets as Classes.

## Building Custom Widgets

- We have to create a class that `extends` (inherited) a stateless or stateful widget.
- In that class, we need to have a `build()` method which returns the `Widget` type. Also, we need to add metadata or annotation `@override`
- `build()` must accept the parameter which is `context` then we return the value in that class.

```dart
class GradientContainer extends StatelessWidget {
  @override
  Widget build(context) {
    return Container(
      decoration: const BoxDecoration(
        gradient: LinearGradient(
          colors: [
            Color.fromARGB(255, 26, 2, 80),
            Color.fromARGB(255, 45, 7, 98)
          ],
          begin: Alignment.topLeft,
          end: Alignment.bottomRight,
        ),
      ),
      child: const Center(
        child: Text(
          "Hello VireakRoth!!",
          style: TextStyle(
            color: Colors.white,
            fontSize: 28,
          ),
        ),
      ),
    );
  }
}
```

## Working with Constructor Functions

- We often see the key parameter thing in the stateless or stateful widget what is it?
  - The reason is each class needs a constructor method which can be optional.
  - So the constructor function accepts a special argument which is `key`
  - Then we can forward it to the class we inherited from by using `:` or we can use a shortcut like this
    `const GradientContainer({super.key});`

## Splitting Code Across Files

- In this step, we learn we can write the custom widget in a different file and then import it to use in the main.dart file.

## Introducing Variables

- A variable is used to store value and reuse or modify it later.

## Variables & Types - Combining Two Key Concepts

- If we do not put the initial value the value in the variable will be dynamic. This can be error-prone so it is better to put Type? variable

## “final” & “const” - Special Kinds Of “Variables”

- If we knew the variable doesn’t change the value we use `final`
- We also can use const but when we use const we tell Dart that the value is compile time constant.

## Instance Variables (Properties) & Constructor Functions

- When we want our widget to be reusable we use the Constructor function.

```dart
child: Center(
   child: StyleText("PUN VIREAKROTH"),
),
```

- In the StyleText class, we need to add property and argument to the constructor class.

```dart
import 'package:flutter/material.dart';

class StyleText extends StatelessWidget {
  StyleText(this.text, {super.key});

  final String text;

  @override
  Widget build(context) {
    return Text(
      text,
      style: const TextStyle(
        color: Colors.white,
        fontSize: 28,
      ),
    );
  }
}
```

## Practice: Reusable Widgets & Constructor Functions

```dart
body: GradientContainer(
          [
            Colors.deepPurple,
            Color.fromARGB(255, 56, 23, 67),
          ],
        ),
```

```dart
import 'package:flutter/material.dart';
import 'package:roll_dice/style_text.dart';

var startAlignment = Alignment.topLeft;
var endAlignment = Alignment.bottomRight;

class GradientContainer extends StatelessWidget {
  const GradientContainer(this.colors, {super.key});

  final List<Color> colors;

  @override
  Widget build(context) {
    return Container(
      decoration: BoxDecoration(
        gradient: LinearGradient(
          colors: colors,
          begin: Alignment.topLeft,
          end: Alignment.bottomRight,
        ),
      ),
      child: Center(
        child: StyleText("POK POUM CHANNAK"),
      ),
    );
  }
}
```

## Displaying Images & Using Multiple Constructor Functions

- Create a new folder called `assets`
- Then edit the `pubspec.yaml` file.

```dart
child: Image.asset(
          'assets/images/dice-2.png',
          width: 300,
        ),
```

## Adding Buttons & Using Functions As Values

- We’ve introduced `Column` Widget which is a children's `argument` that is to take a list of Widgets.
- When we implement a function for an argument like onPressed we do not call it with () we just called the function’s name and that is called Function as Value.

## Styling Buttons & Working with Padding

- First, we need to make the dice go center.
  - In the Column() widget it takes `mainAxisSize: MainAxisSize.min`
- Then we need to change the style of the button

```dart
return Container(
      decoration: BoxDecoration(
        gradient: LinearGradient(
          colors: colors,
          begin: Alignment.topLeft,
          end: Alignment.bottomRight,
        ),
      ),
      child: Center(
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: [
            Image.asset(
              'assets/images/dice-2.png',
              width: 300,
            ),
            const SizedBox(
              height: 20,
            ),
            TextButton(
              onPressed: () => "Roll Dice",
              style: TextButton.styleFrom(
                foregroundColor: Colors.white,
                textStyle: const TextStyle(fontSize: 20),
              ),
              child: const Text("Roll Dice"),
            )
          ],
        ),
      ),
    );
```

## How NOT To Build Interactive Widgets

- NOTE: If our class can change internally for example if we have a variable that will somewhat change in the future. That of course we can’t put const in front of the constructor.
- With the below widget, we can’t see the change of the dice image. Why?

```dart
import 'package:flutter/material.dart';
// import 'style_text.dart';

var startAlignment = Alignment.topLeft;
var endAlignment = Alignment.bottomRight;

class GradientContainer extends StatelessWidget {
  GradientContainer(this.colors, {super.key});

  final List<Color> colors;
  var activeDiceImage = 'assets/images/dice-2.png';

  void rollDice() {
    activeDiceImage = "assets/images/dice-4.png";
    print("Hello World");
  }

  @override
  Widget build(context) {
    return Container(
      decoration: BoxDecoration(
        gradient: LinearGradient(
          colors: colors,
          begin: Alignment.topLeft,
          end: Alignment.bottomRight,
        ),
      ),
      child: Center(
        child: Column(
          mainAxisSize: MainAxisSize.min,
          children: [
            Image.asset(
              activeDiceImage,
              width: 300,
            ),
            const SizedBox(
              height: 20,
            ),
            TextButton(
              onPressed: () => rollDice(),
              style: TextButton.styleFrom(
                foregroundColor: Colors.white,
                textStyle: const TextStyle(fontSize: 20),
              ),
              child: const Text("Roll Dice"),
            )
          ],
        ),
      ),
    );
  }
}
```

- The answer is that it is a Stateless widget. So we’ll learn about the Stateful widget in the next lecture.

## Introducing Stateful Widgets

- We use Stateful when there are data may change over time and it impacts on the UI. e.g. when we click on the button the image of the dice changes.

```dart
import 'package:flutter/material.dart';

class DiceRoller extends StatefulWidget {
  //...
}
```

- In Stateful Widget we don’t use the `build()` method but instead, we have the `createState()` method
- `createState()` returns the `State<Widget>` value type. And it returns the value `_ClassNameState`
