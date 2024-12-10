# Dubit Flutter Adapter Example

### Introduction
The **Dubit Flutter Adapter** makes it easy to integrate Dubit video calls into your Flutter app. Here's a clean and functional example to get you started. Follow the steps below to implement the adapter in your project.

---

### Getting Started

**1. Initialize the Adapter:**

To start using the Dubit adapter, first, instantiate the `Dubit` object and set up an event listener to handle incoming events.

```dart
final dubit = Dubit();

dubit.onEvent.listen((event) {
    print('Received event data: ${event.label} ${event.value}');
});
```

---

**2. Join the call to listen the events:**

Use the `start` method to begin a call by providing the `webCallUrl`. Replace the URL with your specific Dubit video call link.

```dart
dubit.start(
    webCallUrl: 'https://trydubit.daily.co/${room_id}'
);
```

---

**3. Leave the Call:**

When you're ready to stop listening the events, simply call the `stop` method.

```dart
dubit.stop();
```

---

### Full Example Code

Here's the complete implementation:

```dart
import 'package:dubit_flutter_adapter/dubit_flutter_adapter.dart';

void main() {
  final dubit = Dubit();

  // Listen for events
  dubit.onEvent.listen((event) {
    print('Received event data: ${event.label} ${event.value}');
  });

  // Start the call
  dubit.start(webCallUrl: 'https://trydubit.daily.co/${room_id}');

  // Example: Stop the call (triggered by a button press or event)
  // dubit.stop();
}
```
