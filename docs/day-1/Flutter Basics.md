### Creating a new Flutter Project
___

To create a new Flutter project, follow these steps:

1. Open your terminal or command prompt.
1. Navigate to the directory where you want to create the project.
1. Run the following command and replace ***'my_app'*** with the name of your app :

```bash
  flutter create my_app
```
This will create a new Flutter project with the default project structure.

### The structure of a Flutter app
___

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
___

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
___

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
___

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
___

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

### Container, SizedBox, Padding, Center
___

* **'Container'** : A container widget is used to contain and style other widgets. It can be used to add padding, margins, borders, and background colors to the widget inside it. Here's an example:

```less 
  Container(
  padding: EdgeInsets.all(16.0),
  margin: EdgeInsets.all(16.0),
  decoration: BoxDecoration(
    color: Colors.white,
    border: Border.all(color: Colors.grey),
    borderRadius: BorderRadius.circular(10.0),
  ),
  child: Text('This is a container'),
)
```
* **'SizedBox'** : A sized box widget is used to add a fixed size to a widget. It's useful for adding space between widgets. Here's an example:
```less 
  SizedBox(
  height: 20.0,
  width: 20.0,
  child: Container(color: Colors.blue),
)
```
* **'Padding'** :  A padding widget is used to add padding around a widget. It's similar to the ***'Container'*** widget but with less functionality. Here's an example:

```less
  Padding(
  padding: EdgeInsets.all(16.0),
  child: Text('This is a padded text'),
)
```

* **'Center'** : A center widget is used to center a widget within its parent. Here's an example:

```less 
  Center(
  child: Text('This is centered'),
  ) 
```

### Row, Column
---

* **'Row'** : A row widget is used to arrange widgets horizontally in a row. Here's an example:

```less 
  Row(
  children: [
    Text('Widget 1'),
    Text('Widget 2'),
    Text('Widget 3'),
    ],
  ) 
```

* **'Column'** : A column widget is used to arrange widgets vertically in a column. Here's an example:

```less
  Column(
  children: [
    Text('Widget 1'),
    Text('Widget 2'),
    Text('Widget 3'),
    ],
  )
```

### Basic widgets such as text, image, and button widgets
___

* **'Text'** : A text widget is used to display text. Here's an example:

```scss
  Text('Hello, world!')
```

* **'Image'** : An image widget is used to display images. Here's an example:

```rust 
  Image.network('https://example.com/image.jpg')
```
* **'RaisedButton'** : A raised button widget is used to create a button with a raised appearance. Here's an example:

```less 
  RaisedButton(
    onPressed: () {},
    child: Text('Press me'),
  )
```

### Styling widgets with themes and styling properties
___

Flutter provides several ways to style widgets. You can either use individual styling properties or use themes to apply a consistent style across the app.

Here's an example of using individual styling properties to style a ***'Text'*** widget:

```less 
  Text(
  'Hello, world!',
  style: TextStyle(
    color: Colors.blue,
    fontSize: 24.0,
    fontWeight: FontWeight.bold,
    ),
  )
```

And here's an example of using a theme to apply a consistent style across the app:

```less 
  MaterialApp(
  theme: ThemeData(
    primaryColor: Colors.blue,
    fontFamily: 'Roboto',
    textTheme: TextTheme(
      headline1: TextStyle(fontSize: 24.0, fontWeight: FontWeight.bold),
      bodyText1: TextStyle(fontSize: 16.0),
      ),
    ),
   home: MyHomePage(),
  )
```

### Creating the login/signup screens using basic widgets
----

```less 

  import 'package:flutter/material.dart';

class LoginScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Login'),
      ),
      body: Center(
        child: Padding(
          padding: EdgeInsets.all(16.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              TextField(
                decoration: InputDecoration(
                  hintText: 'Email',
                ),
              ),
              SizedBox(height: 16.0),
              TextField(
                decoration: InputDecoration(
                  hintText: 'Password',
                ),
                obscureText: true,
              ),
              SizedBox(height: 16.0),
              RaisedButton(
                onPressed: () {},
                child: Text('Login'),
              ),
              FlatButton(
                onPressed: () {},
                child: Text('Don\'t have an account? Sign up'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}

class SignupScreen extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Sign up'),
      ),
      body: Center(
        child: Padding(
          padding: EdgeInsets.all(16.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              TextField(
                decoration: InputDecoration(
                  hintText: 'Email',
                ),
              ),
              SizedBox(height: 16.0),
              TextField(
                decoration: InputDecoration(
                  hintText: 'Password',
                ),
                obscureText: true,
              ),
              SizedBox(height: 16.0),
              RaisedButton(
                onPressed: () {},
                child: Text('Sign up'),
              ),
              FlatButton(
                onPressed: () {},
                child: Text('Already have an account? Login'),
              ),
            ],
          ),
        ),
      ),
    );
  }
}
```

In this example, we create two separate screens - one for login and one for sign up. Each screen is a **'Scaffold'** widget that contains a **'Column'** widget that holds the various input fields and buttons. We use **'TextField'** widgets to collect the user's email and password, and use **'RaisedButton'** and **'FlatButton'** widgets to handle the login and sign up buttons. We also add some basic padding and spacing to make the layout more visually appealing.

**-------------------------------------**