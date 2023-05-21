## Advanced Flutter widgets

Welcome to Session-2 of our Flutter tutorial series, where we'll explore advanced topics in Flutter development. In this session, we'll dive into customizing Flutter widgets to create unique user interfaces. We'll also learn about themes and styling, allowing us to maintain a consistent look and feel throughout our app. We'll build a student list screen using card widgets and display data in a ListView widget. Additionally, we'll cover creating custom widgets and extracting them into reusable components. Finally, we'll touch on advanced topics such as animations, layouts, and constraints, enabling us to create more dynamic and responsive apps. Let's get started on our journey to becoming proficient in advanced Flutter widgets!

### Customizing Flutter Widgets

Flutter provides a rich set of customizable widgets that allow you to build beautiful and interactive user interfaces. Let's take a look at an example of customizing a FlatButton widget:

```dart 
FlatButton(
  onPressed: () {
    // Button action
  },
  child: Text(
    'Click me!',
    style: TextStyle(
      fontSize: 16.0,
      fontWeight: FontWeight.bold,
      color: Colors.white,
    ),
  ),
  color: Colors.blue,
  shape: RoundedRectangleBorder(
    borderRadius: BorderRadius.circular(8.0),
  ),
),
```

You can customize other Flutter widgets in a similar way by modifying their properties and applying your desired styles.

### Themes and Styling

Themes in Flutter allow you to define a consistent and cohesive look for your app. Let's see an example of creating a custom theme for your app

```dart
ThemeData customTheme = ThemeData(
  primaryColor: Colors.deepPurple,
  accentColor: Colors.amber,
  fontFamily: 'Roboto',
  textTheme: TextTheme(
    headline6: TextStyle(
      fontSize: 20.0,
      fontWeight: FontWeight.bold,
      color: Colors.black,
    ),
    bodyText2: TextStyle(
      fontSize: 14.0,
      color: Colors.grey,
    ),
  ),
);
```

To apply this custom theme to your app, you can wrap your app's root widget with a Theme widget and provide the data property with your custom theme:

```dart
Theme(
  data: customTheme,
  child: MaterialApp(
    // Your app configuration
  ),
),
```

### Building the Student List Screen with Card Widgets

To build a student list screen, you can use Flutter's ListView widget along with Card widgets to display each student's information. Here's an example

```dart 
ListView.builder(
  itemCount: students.length,
  itemBuilder: (context, index) {
    final student = students[index];

    return Card(
      child: ListTile(
        leading: CircleAvatar(
          backgroundImage: NetworkImage(student.avatarUrl),
        ),
        title: Text(student.name),
        subtitle: Text(student.email),
        trailing: Icon(Icons.chevron_right),
        onTap: () {
          // Handle student selection
        },
      ),
    );
  },
),
```

You can customize the Card and ListTile widgets further to match your desired design and add additional functionality as needed.

Remember to adjust the code according to your specific requirements and data structures.

### Displaying Data in a ListView Widget

The ListView widget in Flutter is a versatile tool for displaying lists of data. Let's look at an example of how to use it to display a list of items:

```dart
ListView(
  children: <Widget>[
    ListTile(
      leading: Icon(Icons.person),
      title: Text('John Doe'),
      subtitle: Text('Software Engineer'),
    ),
    ListTile(
      leading: Icon(Icons.person),
      title: Text('Jane Smith'),
      subtitle: Text('Product Manager'),
    ),
    ListTile(
      leading: Icon(Icons.person),
      title: Text('Mark Johnson'),
      subtitle: Text('UX Designer'),
    ),
    // Add more ListTile widgets as needed
  ],
)
```

The ListView widget also supports dynamic lists using the ListView.builder constructor. This allows you to efficiently build large lists by providing a builder function that constructs the list items on demand.

### Creating Custom Widgets and Extracting Them into Reusable Components

Flutter allows you to create custom widgets by combining existing widgets or by extending the Widget class. Let's see an example of creating a custom button widget:

```dart 
class CustomButton extends StatelessWidget {
  final String text;
  final VoidCallback onPressed;

  CustomButton({required this.text, required this.onPressed});

  @override
  Widget build(BuildContext context) {
    return RaisedButton(
      onPressed: onPressed,
      child: Text(text),
    );
  }
}
```

By creating custom widgets, you can encapsulate complex functionality or UI patterns into reusable components. This promotes code reuse and simplifies maintenance.

### Advanced Topics: Animations, Layouts, and Constraints

Flutter offers powerful tools for creating animations, designing layouts, and applying constraints to widgets. Let's explore these advanced topics briefly:

Animations: Flutter provides animation classes and widgets, such as AnimationController and AnimatedBuilder, to create smooth and interactive animations. For example, you can animate the opacity, position, or size of a widget based on user interactions or specific events.

Layouts: Flutter offers a variety of layout widgets, including Column, Row, Stack, and Flex, to arrange and position widgets within a user interface. These widgets allow you to create complex and responsive layouts for different screen sizes and orientations.

Constraints: Flutter's layout system uses constraints to define the size and position of widgets. You can apply constraints using widgets like Container, Expanded, and AspectRatio to control how widgets adapt to available space. Constraints ensure that your UI maintains a consistent appearance across various devices.

Here are some detailed examples of each :

#### Animations

Here are a few examples of animations using Flutter widgets:

1. AnimatedContainer:
The `AnimatedContainer` widget allows you to animate changes to its properties, such as size, color, and padding. Here's an example of animating the size and background color of a container:

```dart
class MyWidget extends StatefulWidget {
  @override
  _MyWidgetState createState() => _MyWidgetState();
}

class _MyWidgetState extends State<MyWidget> {
  bool _isLarge = false;

  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () {
        setState(() {
          _isLarge = !_isLarge;
        });
      },
      child: AnimatedContainer(
        duration: Duration(seconds: 1),
        width: _isLarge ? 200.0 : 100.0,
        height: _isLarge ? 200.0 : 100.0,
        color: _isLarge ? Colors.blue : Colors.red,
      ),
    );
  }
}
```

In this example, tapping on the container triggers the animation. The container's width, height, and background color smoothly transition between the defined values based on the `_isLarge` boolean flag.

2. AnimatedOpacity:
The `AnimatedOpacity` widget allows you to animate the opacity of its child widget. Here's an example:

```dart
class MyWidget extends StatefulWidget {
  @override
  _MyWidgetState createState() => _MyWidgetState();
}

class _MyWidgetState extends State<MyWidget> {
  bool _isVisible = true;

  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        AnimatedOpacity(
          duration: Duration(seconds: 1),
          opacity: _isVisible ? 1.0 : 0.0,
          child: Text('Hello, Flutter!'),
        ),
        ElevatedButton(
          onPressed: () {
            setState(() {
              _isVisible = !_isVisible;
            });
          },
          child: Text('Toggle Visibility'),
        ),
      ],
    );
  }
}
```

In this example, the `Text` widget inside the `AnimatedOpacity` widget fades in and out when the "Toggle Visibility" button is pressed. The opacity smoothly transitions between 1.0 (visible) and 0.0 (invisible) based on the `_isVisible` boolean flag.

3. Hero Animation:
The Hero animation allows you to animate the transition of a widget between two screens. It's commonly used to create smooth transitions for images or other visual elements. Here's a simplified example:

```dart
class Screen1 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () {
        Navigator.push(
          context,
          MaterialPageRoute(
            builder: (context) => Screen2(),
          ),
        );
      },
      child: Hero(
        tag: 'imageTag',
        child: Image.asset('assets/image.png'),
      ),
    );
  }
}

class Screen2 extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return GestureDetector(
      onTap: () {
        Navigator.pop(context);
      },
      child: Hero(
        tag: 'imageTag',
        child: Image.asset('assets/another_image.png'),
      ),
    );
  }
}
```

In this example, when the image in `Screen1` is tapped, it smoothly transitions to `Screen2`, where a different image is displayed. The `Hero` widget with the same `tag` enables the animation between the two screens.

These examples demonstrate just a few possibilities for animations in Flutter. With the wide range of animation classes and widgets available, you can create complex and engaging animations to enhance your app's user experience.

#### Layouts 

Here are a few examples of layout widgets in Flutter:

1. Column:
The `Column` widget allows you to vertically stack multiple widgets. Here's an example:

```dart
Column(
  children: <Widget>[
    Text('Widget 1'),
    Text('Widget 2'),
    Text('Widget 3'),
  ],
)
```

In this example, three `Text` widgets are stacked vertically in a column.

2. Row:
The `Row` widget allows you to horizontally align multiple widgets. Here's an example:

```dart
Row(
  children: <Widget>[
    Text('Widget 1'),
    Text('Widget 2'),
    Text('Widget 3'),
  ],
)
```

In this example, three `Text` widgets are aligned horizontally in a row.

3. Stack:
The `Stack` widget allows you to overlap multiple widgets. Here's an example:

```dart
Stack(
  children: <Widget>[
    Container(
      width: 200,
      height: 200,
      color: Colors.blue,
    ),
    Container(
      width: 150,
      height: 150,
      color: Colors.red,
    ),
    Container(
      width: 100,
      height: 100,
      color: Colors.green,
    ),
  ],
)
```

In this example, three `Container` widgets are stacked on top of each other, creating a layered effect.

4. Expanded:
The `Expanded` widget is often used in combination with `Column` or `Row` to distribute remaining space among its children. Here's an example:

```dart
Column(
  children: <Widget>[
    Text('Widget 1'),
    Expanded(
      child: Text('Widget 2'),
    ),
    Text('Widget 3'),
  ],
)
```

In this example, the middle `Text` widget (Widget 2) will expand to occupy any remaining vertical space within the `Column`.

5. Flexible:
The `Flexible` widget is similar to `Expanded` but allows you to specify a flex factor to control the distribution of space. Here's an example:

```dart
Row(
  children: <Widget>[
    Flexible(
      flex: 2,
      child: Container(
        color: Colors.blue,
      ),
    ),
    Flexible(
      flex: 1,
      child: Container(
        color: Colors.red,
      ),
    ),
    Flexible(
      flex: 3,
      child: Container(
        color: Colors.green,
      ),
    ),
  ],
)
```

In this example, the available horizontal space is divided among the `Container` widgets based on their flex values (2:1:3).

These examples showcase just a few of the layout widgets available in Flutter. By utilizing these widgets and combining them creatively, you can create diverse and responsive user interfaces for your Flutter applications.

#### Constraints

Here are a few examples of using constraints in Flutter widgets:

1. Container:
The `Container` widget allows you to apply constraints to its child widget using properties such as `width`, `height`, and `constraints`. Here's an example:

```dart
Container(
  width: 200.0,
  height: 200.0,
  color: Colors.blue,
  child: Text('Hello, Flutter!'),
)
```

In this example, the `Container` widget enforces a fixed width and height of 200.0 pixels for its child `Text` widget.

2. Expanded:
The `Expanded` widget is often used to fill available space within a `Row` or `Column`. It expands to occupy any remaining space after other widgets have been laid out. Here's an example:

```dart
Row(
  children: <Widget>[
    Expanded(
      child: Container(
        color: Colors.blue,
        child: Text('Widget 1'),
      ),
    ),
    Expanded(
      child: Container(
        color: Colors.red,
        child: Text('Widget 2'),
      ),
    ),
  ],
)
```

In this example, the `Expanded` widgets allow the two `Container` widgets to share the available horizontal space equally.

3. SizedBox:
The `SizedBox` widget allows you to specify fixed dimensions for empty space. It can be used to add spacing between widgets or enforce specific dimensions. Here's an example:

```dart
Row(
  children: <Widget>[
    Container(
      width: 100.0,
      height: 100.0,
      color: Colors.blue,
    ),
    SizedBox(width: 20.0),
    Container(
      width: 100.0,
      height: 100.0,
      color: Colors.red,
    ),
  ],
)
```

In this example, the `SizedBox` widget adds a horizontal spacing of 20.0 pixels between the two `Container` widgets.

4. AspectRatio:
The `AspectRatio` widget allows you to enforce a specific aspect ratio for its child widget. It ensures that the child widget maintains a specified width-to-height ratio. Here's an example:

```dart
AspectRatio(
  aspectRatio: 16 / 9,
  child: Container(
    color: Colors.blue,
    child: Text('Aspect Ratio Widget'),
  ),
)
```

In this example, the child `Container` widget maintains a width-to-height ratio of 16:9, regardless of the available space.

These examples demonstrate how you can apply constraints using various widgets in Flutter. By utilizing constraints effectively, you can control the size, positioning, and behavior of widgets to create visually appealing and responsive user interfaces.