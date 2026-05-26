# Calculator

A simple Flutter calculator application with a dark UI. The app allows users to enter mathematical expressions and evaluate them using the `math_expressions` package.

## Features

- Clean dark-themed calculator interface
- Basic arithmetic operations:
  - Addition `+`
  - Subtraction `-`
  - Multiplication `*`
  - Division `/`
- Decimal input support
- Clear all input using `AC`
- Delete the last entered character using `DEL`
- Expression evaluation using `math_expressions`
- Reusable custom button widget

## Tech Stack

- **Flutter**
- **Dart**
- **Material UI**
- **math_expressions** package

## Project Structure

```text
Calculator/
├── android/                 # Android platform files
├── ios/                     # iOS platform files
├── linux/                   # Linux desktop platform files
├── macos/                   # macOS desktop platform files
├── web/                     # Web platform files
├── windows/                 # Windows desktop platform files
├── lib/
│   ├── main.dart            # App entry point
│   ├── calculator.dart      # Calculator screen and logic
│   └── Components/
│       └── my_button.dart   # Reusable calculator button widget
├── test/
│   └── widget_test.dart     # Flutter widget test file
├── pubspec.yaml             # Project dependencies and configuration
└── README.md
```

## Dependencies

Main dependency used in this project:

```yaml
math_expressions: ^3.1.0
```

This package is used to parse and evaluate the calculator expression entered by the user.

## Getting Started

### Prerequisites

Make sure Flutter is installed on your machine.

Check Flutter installation:

```bash
flutter doctor
```

### Installation

Clone or download the project, then open the project folder:

```bash
cd Calculator
```

Install project dependencies:

```bash
flutter pub get
```

Run the app:

```bash
flutter run
```

## Running on Specific Platforms

Run on Android emulator or device:

```bash
flutter run -d android
```

Run on Chrome:

```bash
flutter run -d chrome
```

Run on Windows:

```bash
flutter run -d windows
```

Run on macOS:

```bash
flutter run -d macos
```

Run on Linux:

```bash
flutter run -d linux
```

## Build Commands

Build Android APK:

```bash
flutter build apk
```

Build Android App Bundle:

```bash
flutter build appbundle
```

Build Web version:

```bash
flutter build web
```

Build Windows app:

```bash
flutter build windows
```

## How the App Works

The app stores the current expression in the `userInput` variable. When the user presses the `=` button, the expression is parsed and evaluated using `math_expressions`.

Main calculation logic:

```dart
void equalPress() {
  Parser p = Parser();
  Expression expression = p.parse(userInput);
  ContextModel contextModel = ContextModel();

  double eval = expression.evaluate(EvaluationType.REAL, contextModel);
  answer = eval.toString();
}
```

## Notes / Future Improvements

The current version is a basic calculator. The following improvements can be added later:

- Add error handling for invalid expressions
- Prevent `DEL` from crashing when input is empty
- Complete support for `+/-` and `%` operations
- Fix the number layout if needed
- Update the default Flutter widget test to match the calculator UI
- Improve UI responsiveness for different screen sizes
- Add calculation history
- Format answers to remove unnecessary decimal zeros

## License

This project is for learning and practice purposes. Add a license file if you plan to publish or share it publicly.

