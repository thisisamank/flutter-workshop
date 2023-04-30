## Flutter Widgets and Navigation

Welcome to Day 2 of our Flutter development course! In this session, we'll dive into the world of Flutter widgets and navigation. We'll cover the essential Flutter material design widgets, including the Scaffold widget and its components, and explore how to create a navigation stack with the Navigator widget. Additionally, we'll delve into user input and forms, implementing text fields and other form widgets, and how to handle validation and errors. Finally, we'll build the profile creation screens using material design widgets. By the end of this session, you'll have a solid understanding of how to build beautiful and functional user interfaces in Flutter. 

### Flutter Material Design Widgets, Including the Scaffold Widget and Its Components

Flutter Material Design Widgets are a set of UI elements that adhere to the Material Design guidelines established by Google. These widgets are optimized for mobile devices and provide a consistent look and feel across all apps built with Flutter. One of the most important widgets in Material Design is the Scaffold widget, which serves as a container for the main elements of a screen, including the app bar, body, and bottom navigation.

```less
import 'package:flutter/material.dart';

class MyHomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('My App'),
      ),
      body: Center(
        child: Text('Hello World!'),
      ),
    );
  }
}
```
### Navigation and Routing in Flutter

Navigation and routing are essential concepts in Flutter, allowing you to move between different screens or "routes" in your app. Flutter provides a powerful Navigator widget that manages the navigation stack and makes it easy to push new routes onto the stack or pop existing routes off the stack.
```less
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => SecondScreen()),
);
```

### Creating a Navigation Stack with the Navigator Widget

To create a navigation stack in Flutter, you simply need to push new routes onto the stack using the Navigator widget. Each new route will be added to the top of the stack, allowing users to navigate back to previous screens using the device's back button or a custom button in your app.
```less
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => SecondScreen()),
);

// Later, in the SecondScreen widget...
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => ThirdScreen()),
);
```

### User Input and Forms

User input and forms are a crucial part of many apps, allowing users to enter data and interact with your app in meaningful ways. Flutter provides several built-in form widgets, including TextFields, Checkboxes, and RadioButtons, that make it easy to create forms in your app.
```less
TextField(
  decoration: InputDecoration(
    hintText: 'Enter your name',
  ),
);
```

### Implementing Text Fields and Other Form Widgets

TextFields and other form widgets allow users to enter and submit data in your app. Flutter provides several built-in form widgets that make it easy to create forms in your app, including TextFields, Checkboxes, and RadioButtons.
```php
bool _isChecked = false;

Checkbox(
  value: _isChecked,
  onChanged: (bool value) {
    setState(() {
      _isChecked = value;
    });
  },
  title: Text('Option 1'),
);
```

### Validation and Error Handling in Forms

Validation and error handling are essential parts of any form in your app. Flutter provides several built-in form validation functions, including validator functions that allow you to check whether the user's input meets certain criteria.
```less
final _formKey = GlobalKey<FormState>();
String _email;

Form(
  key: _formKey,
  child: TextFormField(
    decoration: InputDecoration(
      hintText: 'Enter your email',
    ),
    validator: (value) {
      if (!value.contains('@')) {
        return 'Please enter a valid email address';
      }
      return null;
    },
    onSaved: (value) {
      _email = value;
    },
  ),
);
```

### Building the Profile Creation Screens Using Material Design Widgets

Material Design widgets are an excellent choice for building beautiful and functional user interfaces in your app. You can use these widgets to create a range of different screens and components, including profile creation screens.
```less
final _formKey = GlobalKey<FormState>();
String _firstName, _lastName;

Form(
  key: _formKey,
  child: Column(
    children: [
      TextFormField(
        decoration: InputDecoration(
          hintText: 'Enter your first name',
        ),
        validator: (value) {
          if (value.isEmpty) {
            return 'Please enter your first name';
          }
          return null;
        },
        onSaved: (value) {
          _firstName = value;
        },
      ),
      TextFormField(
        decoration: InputDecoration(
          hintText: 'Enter your last name',
        ),
        validator: (value) {
          if (value.isEmpty) {
            return 'Please enter your last name';
          }
          return null;
        },
        onSaved: (value) {
          _lastName = value;
        },
      ),
      RaisedButton(
        child: Text('Submit'),
        onPressed: () {
          if (_formKey.currentState.validate()) {
            _formKey.currentState.save();
            // Do something with the user's input
          }
        },
      ),
    ],
  ),
);
```