
# Flutter Session Manager

A simple and efficient singleton class for managing session data in Flutter applications using the `shared_preferences` package. This `SessionManager` allows you to easily store, retrieve, and manage session data of various types.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)
- [Methods](#methods)
- [License](#license)
- [Contributing](#contributing)
- [Acknowledgments](#acknowledgments)

## Features

- Singleton pattern ensures a single instance throughout the app.
- Supports multiple data types: `String`, `int`, `bool`, `double`, `List<String>`, and JSON objects.
- Easy-to-use methods for setting, getting, removing, and clearing session data.

## Installation

Add the following dependency to your `pubspec.yaml` file:

```yaml
dependencies:
  shared_preferences: ^2.0.0  # Check for the latest version
```

## Usage

- Import the SessionManager

```dart
import 'path/to/your/session_manager.dart';
```

- Initialize

```dart
final sessionManager = SessionManager();
```

- Save data

```dart
await sessionManager.set('username', 'john_doe');
await sessionManager.set('age', 30);
await sessionManager.set('isLoggedIn', true);
```

- Retrieve data

```dart
String? username = await sessionManager.get('username');
int? age = await sessionManager.get('age');
bool? isLoggedIn = await sessionManager.get('isLoggedIn');
```

- Check if key exists

```dart
bool exists = await sessionManager.containsKey('username');
```

- Remove a key

```dart
await sessionManager.remove('username');
```

- Clear all session data

```dart
await sessionManager.clear();
```

## Example

Here’s a quick example of how you might use SessionManager in a login flow:

```dart
void login(String username, String password) async {
  // Perform authentication...
  if (isAuthenticated) {
    await sessionManager.set('username', username);
  }
}
```

## Method

```dart
set(String key, dynamic value)
```

Saves the specified value under the given key.

```dart
get(String key)
```

Retrieves the value associated with the specified key.

```dart
getObject(String key)
```

Retrieves and decodes an object stored as a JSON string.

```dart
containsKey(String key)
```

Checks if the specified key exists in the session.

```dart
remove(String key)
```

Removes the specified key and its associated value.

```dart
clear()
```

Clears all session data.

```dart
reload()
```

Reloads the preferences (automatically handled but can be called if needed).

## License

This project is licensed under MIT License

## Contributing

Contributions are always welcome!

Feel free to open a pull request or issue.

## Acknowledgements

- Shared Preferences for providing a simple way to persist data.
