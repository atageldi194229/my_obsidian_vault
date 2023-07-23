## About
Provides [Dart Build System](https://github.com/dart-lang/build) builders for handling JSON.
[json_serializable](https://pub.dev/packages/json_serializable)

## Installation

```bash
dart pub add json_serializable --dev
```


## Setup [](https://pub.dev/packages/json_serializable#setup)

To configure your project for the latest released version of `json_serializable`, see the [example](https://github.com/google/json_serializable.dart/tree/master/example).

## Example [](https://pub.dev/packages/json_serializable#example)

Given a library `example.dart` with an `Person` class annotated with [`JsonSerializable`](https://pub.dev/documentation/json_annotation/4.8.1/json_annotation/JsonSerializable-class.html):

```dart
import 'package:json_annotation/json_annotation.dart';

part 'example.g.dart';

@JsonSerializable()
class Person {
  /// The generated code assumes these values exist in JSON.
  final String firstName, lastName;

  /// The generated code below handles if the corresponding JSON value doesn't
  /// exist or is empty.
  final DateTime? dateOfBirth;

  Person({required this.firstName, required this.lastName, this.dateOfBirth});

  /// Connect the generated [_$PersonFromJson] function to the `fromJson`
  /// factory.
  factory Person.fromJson(Map<String, dynamic> json) => _$PersonFromJson(json);

  /// Connect the generated [_$PersonToJson] function to the `toJson` method.
  Map<String, dynamic> toJson() => _$PersonToJson(this);
}
```

## Running the code generator
```bash
dart run build_runner build
```
