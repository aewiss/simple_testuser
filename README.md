# TestUser Class

The `TestUser` class provides utility methods for testing UI interactions in Flutter applications using the Flutter testing framework.

## Methods

### `tapButtonByKey({required Key key, required WidgetTester tester})`

Taps a button identified by a key.

- `key`: The key of the button to tap.
- `tester`: The `WidgetTester` instance.

### `tapButtonByLabel({required String label, required WidgetTester tester})`

Taps a button identified by its text label.

- `label`: The text label of the button to tap.
- `tester`: The `WidgetTester` instance.

### `writeToInputField({required Key key, required WidgetTester tester, required String text})`

Writes text to an input field identified by a key.

- `key`: The key of the input field.
- `tester`: The `WidgetTester` instance.
- `text`: The text to write to the input field.

### `logIn({required String username, required Key usernameInputKey, required String password, required Key passwordInputKey, required WidgetTester tester, required Key loginButtonKey})`

Simulates a login action by entering a username, password, and tapping the login button.

- `username`: The username to enter.
- `usernameInputKey`: The key of the username input field.
- `password`: The password to enter.
- `passwordInputKey`: The key of the password input field.
- `tester`: The `WidgetTester` instance.
- `loginButtonKey`: The key of the login button.

## Usage

You can use the `TestUser` class in your Flutter widget tests to simulate user interactions. Here's an example:

```dart
void main() {
  testWidgets('Test login functionality', (WidgetTester tester) async {
    await tester.pumpWidget(MyApp());

    final TestUser testUser = TestUser();

    await testUser.logIn(
      username: 'username',
      usernameInputKey: Key('username_input'),
      password: 'password',
      passwordInputKey: Key('password_input'),
      tester: tester,
      loginButtonKey: Key('login_button'),
    );

    // Add your assertions here
  });
}
