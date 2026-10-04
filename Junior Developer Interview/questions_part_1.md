# Flutter Interview Questions — Part 1

## Dart & Flutter Fundamentals — Junior Developer
---

## 1. What is Dart?
### ✅ English Answer
Dart is a programming language developed by Google. Flutter uses Dart to build cross-platform applications for Android, iOS, web, and desktop. Dart supports object-oriented programming, asynchronous programming, null safety, and strong typing.

### ✅ বাংলায় Answer
Dart হলো Google-এর তৈরি একটি programming language। Flutter দিয়ে Android, iOS, Web বা Desktop application তৈরি করতে আমরা Dart ব্যবহার করি।

Dart-এর মধ্যে OOP, asynchronous programming, null safety এবং strong typing-এর মতো features আছে।

---

## 2. What is the difference between final and const in Dart?
### ✅ English Answer
final: A runtime constant. Its value can be determined when code executes (e.g., final now = DateTime.now();), but once assigned, it cannot be changed.

const: A compile-time constant. Its value must be known before compiling the code and is deeply immutable (e.g., const pi = 3.1416;).

### ✅ বাংলায় Answer
final: রানটাইম কনস্ট্যান্ট। কোড চালু হওয়ার পর এর মান নির্ধারণ হতে পারে (যেমন API রেসপন্স বা বর্তমান সময়)। একবার মান পেলে তা আর পরিবর্তন করা যায় না।

const: কম্পাইল-টাইম কনস্ট্যান্ট। কোড রান করার আগেই এর নির্দিষ্ট মান জানা থাকতে হয় এবং এটি কোনোভাবেই পরিবর্তনযোগ্য নয়।

---

## 3. What is the difference between context.watch(), context.read(), and context.select() in Provider?
### ✅ English Answer
"context.watch<T>() listens to changes and rebuilds the widget when data updates. context.read<T>() reads the value once without listening, which is ideal for button click handlers. context.select<T, R>() listens to a specific property and rebuilds only when that exact sub-value changes."

### ✅ বাংলায় Answer
"context.watch() পুরো মডেলের পরিবর্তনের দিকে নজর রাখে, তাই কোনো ডাটা পরিবর্তন হলেই পুরো উইজেটটি রিবিল্ড হয়। context.read() শুধু একবার ডাটা রিড করে কিন্তু লিসেন করে না, তাই বাটন ক্লিক বা ফাংশন কল করার জন্য এটি সেরা। আর context.select() ব্যবহার করা হয় সুনির্দিষ্ট কোনো ফিল্ড পরিবর্তনের ওপর নজর রাখতে; এতে অপ্রয়োজনীয় উইজেট রিবিল্ড এড়ানো যায়।"

---

## 4. Why is Dart single-threaded, and how do you handle heavy computation?
### ✅ English Answer
"Dart runs on an event loop with a single thread. If we execute heavy operations like huge JSON decoding on the main thread, the UI will freeze and drop frames. We solve this by offloading the task to an Isolate or using the compute() function to run it in a separate memory space."

### ✅ বাংলায় Answer
"ডার্ট সিঙ্গেল-থ্রেডেড এবং এটি ইভেন্ট লুপের মাধ্যমে কাজ করে। এখন মেইন থ্রেডে যদি খুব বড় হিসাব-নিকাশ বা বিশাল জেএসন পার্সিং চালানো হয়, তবে অ্যাপ ফ্রেম ড্রপ করবে বা ল্যাগ করবে। এই সমস্যা সমাধানের জন্য আমরা ডার্ট আইসোলেট (Isolate) অথবা compute() ফাংশন ব্যবহার করি, যা ব্যাকগ্রাউন্ডে আলাদা মেমোরি থ্রেডে কাজটি সম্পন্ন করে।"

---

## 5. What is Flutter?
### ✅ English Answer
Flutter is an open-source UI toolkit developed by Google for building cross-platform applications from a single codebase. It uses Dart as its programming language and provides a rich collection of customizable widgets.

### ✅ বাংলায় Answer
Flutter হলো Google-এর তৈরি একটি UI toolkit। এর সবচেয়ে বড় সুবিধা হলো একই codebase ব্যবহার করে Android, iOS, Web এবং Desktop এর জন্য application তৈরি করা যায়।

Flutter-এ UI তৈরি করার জন্য মূলত widget ব্যবহার করা হয়।

---

## 6. Why do you use Flutter? / Why do you choose Flutter for mobile app development?
### ✅ English Answer
I choose Flutter because it allows me to build cross-platform applications using a single codebase. It provides a rich widget system, fast development with hot reload, good performance, and makes it easier to maintain UI consistently across platforms.

### ✅ বাংলায় Answer
আমি Flutter ব্যবহার করি কারণ একটা codebase দিয়েই Android এবং iOS-এর জন্য application তৈরি করা যায়।

এছাড়া Hot Reload-এর কারণে code পরিবর্তন করার পর খুব দ্রুত result দেখা যায়। Flutter-এর widget system-এর কারণে UI তৈরি এবং maintain করাও সহজ।

### ⭐ Interview Tip
শুধু "Flutter is easy" বলবে না।
এই points গুলো mention করতে পারো:

- Single codebase
- Cross-platform development
- Hot Reload
- Rich widget system
- Good performance
- Easy UI maintenance

---

## 7. What is a Widget?
### ✅ English Answer
A widget is the basic building block of a Flutter UI. Everything in Flutter's UI is represented as a widget, such as text, buttons, layouts, images, and even the application itself.

### ✅ বাংলায় Answer
Flutter-এর UI-এর প্রায় সবকিছুই widget দিয়ে তৈরি।
যেমন:
Text(), ElevatedButton(), Container()
সহজ ভাবে বললে, Flutter UI এর building block হলো Widget।

## 8. What is StatelessWidget?
✅ English Answer
StatelessWidget is a widget whose state does not change during its lifetime. It is suitable for UI components that depend only on the values passed to them and do not need to manage their own changing state.

✅ বাংলায় Answer
যে widget এর নিজের কোনো পরিবর্তনশীল state নেই, সেখানে StatelessWidget ব্যবহার করি।

যেমন একটা সাধারণ title:
class MyTitle extends StatelessWidget {
  const MyTitle({super.key});

  @override
  Widget build(BuildContext context) {
    return const Text('Hello Flutter');
  }
}

## 9. What is StatefulWidget?
✅ English Answer
StatefulWidget is a widget that can maintain and update mutable state during its lifetime. When the state changes, Flutter can rebuild the widget to reflect the updated data.

✅ বাংলায় Answer
যে UI-এর data বা state পরিবর্তন হতে পারে, সেখানে StatefulWidget ব্যবহার করা হয়।

যেমন counter:
int count = 0;
Button চাপলে:
setState(() {
  count++;
});
এখানে count পরিবর্তন হচ্ছে, তাই StatefulWidget ব্যবহার করা যায়।

## 10. What is the difference between StatelessWidget and StatefulWidget?
✅ English Answer
A StatelessWidget does not manage mutable state internally, while a StatefulWidget can maintain and update mutable state. StatelessWidget is useful for static or externally controlled UI, while StatefulWidget is useful when the UI needs to change based on local state.

✅ বাংলায় Answer
StatelessWidget	              StatefulWidget
নিজের state পরিবর্তন করে না	      State পরিবর্তন করতে পারে
তুলনামূলক simple	            State management দরকার হয়
Static UI-এর জন্য ভালো	        Dynamic UI-এর জন্য ভালো
build() থাকে	               State class থাকে

Example:
Login page-এর static logo → StatelessWidget হতে পারে।
Password show/hide করা → StatefulWidget দিয়ে করা যায়।

## 11. How do you structure MVVM in your Flutter projects?"   

✅ English Answer
I separate the project into three distinct layers: Model, View, and ViewModel. The Model handles data structures and JSON parsing. The ViewModel extends ChangeNotifier, handles business logic and API requests, and exposes data to the UI. The View consists solely of presentation widgets that observe the ViewModel and never contain core business rules."

✅ বাংলায় Answer
আমি কোডকে তিনটি স্পষ্ট স্তরে ভাগ করি। মডেল লেয়ারে শুধু ডেটা ক্লাস এবং সিরিয়ালাইজেশন থাকে। ভিউমডেল লেয়ারে সব বিজনেস লজিক এবং এপিআই কল থাকে, যা ChangeNotifier দিয়ে স্টেট আপডেট করে। আর ভিউ লেয়ারে কেবল ইউআই উইজেট থাকে; সেখানে সরাসরি কোনো বিজনেস লজিক থাকে না, এটি শুধু ভিউমডেল থেকে ডাটা নিয়ে ডিসপ্লে করে।