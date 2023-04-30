### Creating a new Flutter Project

To create a new Flutter project, follow these steps:

1. Open your terminal or command prompt.
1. Navigate to the directory where you want to create the project.
1. Run the following command and replace ***'my_app'*** with the name of your app :

```bash
  flutter create my_app
```
This will create a new Flutter project with the default project structure.

### The structure of a Flutter app

A typical Flutter app has the following structure:
```bash 
  my_app/
    android/
    ios/
    lib/z
      main.dart
    test/
    pubspec.yaml
```
* ***'android/'*** and ***'ios/'*** contain the Android and iOS specific project files respectively.
* ***'lib/'*** contains the Dart code for the app.
* ***'main.dart'*** is the entry point of the app.
* ***'test/'*** contains the unit and integration tests for the app.
* ***'pubspec.yaml'*** contains the dependencies and metadata for the app.

### The role of the pubspec.yaml file

The ***'pubspec.yaml'*** file is used to define the dependencies and metadata for the app. Here's an example ***'pubspec.yaml'*** file:

```yaml
  name: my_app
  description: My awesome Flutter app
  version: 1.0.0

  dependencies:
    flutter:
      sdk: flutter
    http: ^0.13.0

  dev_dependencies:
    flutter_test:
      sdk: flutter

  flutter:
    assets:
      - assets/images/
```

In this example, the ***'dependencies'*** section specifies that the app depends on the ***'http'*** package. The ***'flutter'*** section specifies that the ***'assets/images/'*** directory should be included in the app's assets. The ***'dev_dependencies'*** section specifies that the ***'flutter_test'*** package is used for testing.

### Introduction to Widgets and Elements

In Flutter, everything is a widget. A widget is a description of part of a user interface. A widget might describe part of a button, a label, or even an entire screen.

Here's an example of a simple widget that displays some text:

```java
class MyTextWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text('Hello, world!');
  }
}
```
In this example, ***'Text'*** is a built-in widget that displays a piece of text. The ***'build()'*** method is responsible for returning the widget to be displayed.

### Material Widgets vs Cupertino Widgets

Flutter provides two different sets of widgets for building apps: Material Design widgets and Cupertino widgets.

Here's an example of a ***'RaisedButton'*** using Material Design:

```less
  RaisedButton(
    onPressed: () {},
    child: Text('Press me'),
  )
```
And here's an example of a ***'CupertinoButton'*** using Cupertino design:

```less 
  CupertinoButton(
    onPressed: () {},
    child: Text('Press me'),
  )
```
In both cases, the ***'onPressed'*** property specifies what should happen when the button is pressed, and the ***'child'*** property specifies what should be displayed on the button.

### Scanffold

The ***'Scaffold'*** widget provides a basic structure for your app. It typically includes an app bar, a body area, and optionally, a bottom navigation bar.

Here's an example of a simple app that uses a ***'Scaffold'***:

```less 
  class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'My App',
      home: Scaffold(
        appBar: AppBar(
          title: Text('My App'),
        ),
        body: Center(
          child: Text('Hello, world!'),
        ),
      ),
    );
```