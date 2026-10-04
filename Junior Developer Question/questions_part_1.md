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

---

## 8. What is StatelessWidget?
### ✅ English Answer
StatelessWidget is a widget whose state does not change during its lifetime. It is suitable for UI components that depend only on the values passed to them and do not need to manage their own changing state.

### ✅ বাংলায় Answer
যে widget এর নিজের কোনো পরিবর্তনশীল state নেই, সেখানে StatelessWidget ব্যবহার করি।

যেমন একটা সাধারণ title:
class MyTitle extends StatelessWidget {
  const MyTitle({super.key});

  @override
  Widget build(BuildContext context) {
    return const Text('Hello Flutter');
  }
}

---

## 9. What is StatefulWidget?
### ✅ English Answer
StatefulWidget is a widget that can maintain and update mutable state during its lifetime. When the state changes, Flutter can rebuild the widget to reflect the updated data.

### ✅ বাংলায় Answer
যে UI-এর data বা state পরিবর্তন হতে পারে, সেখানে StatefulWidget ব্যবহার করা হয়।

যেমন counter:
int count = 0;
Button চাপলে:
setState(() {
  count++;
});
এখানে count পরিবর্তন হচ্ছে, তাই StatefulWidget ব্যবহার করা যায়।

---

## 10. What is the difference between StatelessWidget and StatefulWidget?
### ✅ English Answer
StatelessWidget: Immutable. Its configuration cannot change dynamically during its lifetime unless its parent widget rebuilds with new values.

StatefulWidget: Mutable. It maintains an independent State object that persists across frames and triggers UI rebuilds whenever setState() is executed.

### ✅ বাংলায় Answer
StatelessWidget: এটি অপরিবর্তনশীল (Immutable)। একবার তৈরি হলে এর ভেতরের কোনো ডেটা বা UI একা একা পরিবর্তন হতে পারে না।

StatefulWidget: এটি পরিবর্তনশীল (Mutable)। এর সাথে একটি নিজস্ব State অবজেক্ট থাকে এবং setState() কল করে যেকোনো সময় স্ক্রিনের UI আপডেট করা যায়।

---

## 11. How do you structure MVVM in your Flutter projects?"   
### ✅ English Answer
I separate the project into three distinct layers: Model, View, and ViewModel. The Model handles data structures and JSON parsing. The ViewModel extends ChangeNotifier, handles business logic and API requests, and exposes data to the UI. The View consists solely of presentation widgets that observe the ViewModel and never contain core business rules."

### ✅ বাংলায় Answer
আমি কোডকে তিনটি স্পষ্ট স্তরে ভাগ করি। মডেল লেয়ারে শুধু ডেটা ক্লাস এবং সিরিয়ালাইজেশন থাকে। ভিউমডেল লেয়ারে সব বিজনেস লজিক এবং এপিআই কল থাকে, যা ChangeNotifier দিয়ে স্টেট আপডেট করে। আর ভিউ লেয়ারে কেবল ইউআই উইজেট থাকে; সেখানে সরাসরি কোনো বিজনেস লজিক থাকে না, এটি শুধু ভিউমডেল থেকে ডাটা নিয়ে ডিসপ্লে করে।

---

## 12. Why do you use GoRouter instead of regular Navigator?"
### ✅ English Answer
GoRouter provides a declarative routing API that simplifies deep linking, manages complex path and query parameters seamlessly, and makes route authentication guards straightforward through top-level redirects.  

### ✅ বাংলায় Answer
ন্যাভিগেটর ১.০ বেশ ইম্পারেটিভ এবং বড় অ্যাপে রাউট কন্ট্রোল করা জটিল। গো-রাউটারে খুব সহজে ডিক্লারেটিভ উপায়ে রাউট লেখা যায়, ডিপ লিঙ্কিং সেটআপ করা সহজ এবং ইউজার লগইন আছে কি না তা যাচাই করে সরাসরি রিডাইরেক্ট গার্ড বসানো যায়।

---

### 13. Explain the lifecycle of a StatefulWidget.
### ✅ English Answer
The lifecycle executes in the following sequence:

createState(): Creates the mutable state object.

initState(): Called once when the widget enters the tree; used for one-time initialization.

didChangeDependencies(): Invoked right after initState() or whenever an InheritedWidget dependency changes.

build(): Returns the UI tree; re-runs every time setState() is called.

didUpdateWidget(): Invoked when the parent widget updates configuration and passes new properties.

deactivate(): Invoked when the widget is temporarily removed from the tree.

dispose(): Permanent removal; used to cancel streams, timers, and text/animation controllers.

### ✅ বাংলায় Answer
StatefulWidget-এর লাইফসাইকেল ধাপগুলো হলো:

createState(): স্টেট অবজেক্ট তৈরি করে।

initState(): উইজেট লোড হওয়ার সময় মাত্র একবার রান হয় (ইনিশিয়াল সেটআপের জন্য)।

didChangeDependencies(): initState()-এর পর অথবা ডিপেন্ডেন্সি পরিবর্তন হলে কল হয়।

build(): UI ড্র করে; প্রতিবার স্টেট পরিবর্তন হলে এটি আবার রান হয়।

didUpdateWidget(): প্যারেন্ট উইজেট নতুন কনফিগারেশন পাঠালে এটি কল হয়।

deactivate(): উইজেট ট্রি থেকে সাময়িকভাবে সরে গেলে এটি রান হয়।

dispose(): উইজেট স্থায়ীভাবে মুছে গেলে মেমরি ফ্রি করতে (কন্ট্রোলার ও স্ট্রিম বন্ধ করতে) এটি ব্যবহার করা হয়।

## 14. What is the difference between Hot Reload and Hot Restart?
### ✅ English Answer
Hot Reload: Injects updated code changes into the running Dart VM without resetting the current application state. It is very fast and preserves your current UI position.

Hot Restart: Destroys the current state, resets all global and static variables, and reruns the application from the entry point main().

### ✅ বাংলায় Answer
Hot Reload: অ্যাপের কারেন্ট স্টেট (ডাটা বা স্ক্রিনের অবস্থান) ঠিক রেখে খুব দ্রুত পরিবর্তিত কোড রানটাইমে পাঠিয়ে দেয়।

Hot Restart: অ্যাপের সম্পূর্ণ স্টেট ক্লিয়ার বা রিসেট করে এবং একদম শুরু থেকে (main() ফাংশন থেকে) পুনরায় চালু করে।

## 15. What is the difference between main() and runApp() in Flutter?
### ✅ English Answer
main(): The predefined programmatic entry point of every Dart application where execution begins.

runApp(): A Flutter framework function called within main() that takes a Widget, makes it the root of the widget tree, and inflates it onto the screen.

### ✅ বাংলায় Answer
main(): ডার্ট প্রোগ্রামের এন্ট্রি পয়েন্ট; এখান থেকেই প্রোগ্রাম এক্সিকিউশন শুরু হয়।

runApp(): ফ্ল্যাটারের একটি মেথড যা রুট উইজেটটিকে গ্রহণ করে এবং পুরো স্ক্রিনে রেন্ডার করে ডিসপ্লেতে দেখায়।

## 16. What is the difference between Future and Stream in Dart?
### ✅ English Answer
Future: Delivers a single asynchronous event or error over time (e.g., an HTTP API request).

Stream: Delivers an asynchronous sequence of multiple continuous data events over time (e.g., chat messages, geolocation tracking, web-sockets).

### ✅ বাংলায় Answer
Future: একবার মাত্র একক রেসপন্স বা ডেটা দেয় (যেমন: কোনো API কল বা ডাটাবেজ থেকে ডেটা আনা)।

Stream: সময়ের সাথে সাথে ধারাবাহিকভাবে একাধিক ডেটা পাঠাতে থাকে (যেমন: লাইভ চ্যাট মেসেজ, রিয়েল-টাইম লোকেশন ট্র্যাকিং)।


## 17. What is pubspec.yaml and why is it used?
### ✅ English Answer
pubspec.yaml is the project configuration file in Flutter. It is used to:

Manage project metadata (name, description, version).
Define Dart and Flutter SDK environment constraints.
Add and manage external package dependencies and dev dependencies.
Declare application assets such as images, SVGs, audio files, and custom fonts.

### ✅ বাংলায় Answer
pubspec.yaml হলো ফ্ল্যাটার প্রজেক্টের কনফিগারেশন ফাইল। এটি ব্যবহৃত হয়:

প্রজেক্টের নাম, ভার্সন ও ডেসক্রিপশন নির্ধারণ করতে।
থার্ড-পার্টি লাইব্রেরি বা প্যাকেজ অ্যাড ও ম্যানেজ করতে।
প্রজেক্টের জন্য ইমেজ, আইকন ও কাস্টম ফন্ট ডিক্লেয়ার বা লিংক করতে।


5. How does Flutter optimize list rendering with ListView.builder compared to a simple Column?
✅ English Answer
Column / ListView(children: []): Renders and instantiates all children simultaneously into memory upon layout, regardless of whether they are visible on screen. This can cause high memory usage and dropped frames when displaying large lists.

ListView.builder: Employs viewport-based lazy loading. It only instantiates, lays out, and paints items currently visible within the scroll viewport plus a small cache extent. As items scroll off-screen, their resources are reclaimed or recycled.

✅ বাংলায় Answer
Column বা ListView(children: []): লিস্টে যতগুলো আইটেম থাকে, তাদের সবগুলোকে স্ক্রিনে আসার আগেই একসাথে মেমরিতে রেন্ডার করে। ফলে ডেটা বেশি হলে মেমরি বেড়ে গিয়ে অ্যাপ হ্যাং বা ক্র্যাশ করতে পারে।

ListView.builder: এটি অলসভাবে (Lazy Loading) কাজ করে। ব্যবহারকারী স্ক্রিনে স্ক্রল করে যতটুকু অংশ দেখছেন, ঠিক ততটুকু অংশই মেমরিতে তৈরি ও রেন্ডার করে। আইটেম স্ক্রিনের বাইরে চলে গেলে তা রিসাইকেল করে মেমরি মুক্ত রাখে।

36. What is the RepaintBoundary widget and how does it prevent frame drops?
✅ English Answer
RepaintBoundary isolates a specific subtree of widgets into a separate display list on the GPU:

Normally, if one widget repaints, its entire ancestor or sibling branch might be forced to repaint.

Wrapping a frequently changing widget (such as an animation, video player, or continuous progress bar) inside a RepaintBoundary prevents paint propagation, ensuring only the isolated subtree is repainted without affecting static surrounding layouts.

✅ বাংলায় Answer
RepaintBoundary উইজেট ট্রির কোনো নির্দিষ্ট অংশকে গ্রাফিক্স মেমরিতে আলাদা একটি লেয়ারে আইসোলেট বা বিভক্ত করে রাখে:

সাধারণত স্ক্রিনের একটি ছোট উইজেট ড্র (Repaint) হলে তার আশেপাশের প্যারেন্ট বা চাইল্ড উইজেটগুলোও অপ্রয়োজনীয়ভাবে ড্র হতে পারে।

বারবার অ্যানিমেট হওয়া কোনো উইজেটের চারপাশে RepaintBoundary ব্যবহার করলে পেইন্টিং সীমাবদ্ধ থাকে, যার ফলে স্থির অংশগুলো বারবার রেন্ডার না হয়ে অ্যাপের ৬০/১২০ FPS স্মুথ থাকে।

37. What is Dependency Injection (DI) and how is it handled in Flutter?
✅ English Answer
Dependency Injection (DI) is a software design pattern where classes receive their dependencies from an external source rather than instantiating them internally:

Service Locator (get_it): Acts as a global registry where dependencies (e.g., API clients, database repositories) are registered as singletons, factories, or lazy singletons and retrieved on demand without relying on BuildContext.

Inherited-based DI (Provider / Riverpod): Injects dependencies scoped to the widget tree lifecycle, naturally coupling teardown to widget removal.

✅ বাংলায় Answer
Dependency Injection (DI) হলো এমন একটি প্যাটার্ন যেখানে কোনো ক্লাসের ভেতরে অন্য অবজেক্ট তৈরি না করে বাইরে থেকে তা সরবরাহ করা হয়:

Service Locator (get_it): একটি সেন্ট্রাল রেজিস্ট্রি হিসেবে কাজ করে, যেখান থেকে পুরো অ্যাপের যেকোনো জায়গা থেকে API সার্ভিস বা ডাটাবেজ রিপোজিটরি সরাসরি কল করা যায় (কোনো BuildContext লাগে না)।

Tree-scoped DI (Provider/Riverpod): উইজেট ট্রির মাধ্যমে ডিপেন্ডেন্সি ইনজেক্ট করে, যাতে কোনো স্ক্রিন বন্ধ হলে তার সাথে সম্পর্কিত ডেটাও স্বয়ংক্রিয়ভাবে মেমরি থেকে মুছে যায়।

38. How does Flutter manage responsive UI across different screen sizes and orientations?
✅ English Answer
MediaQuery: Retrieves runtime screen dimensions, pixel density, orientation, and safe area paddings.

LayoutBuilder: Provides parent layout constraints (boxConstraints.maxWidth), allowing conditional rendering based on parent widget bounds rather than total device screen size.

Flexibility Widgets: Using Expanded, Flexible, FittedBox, and Wrap allows elements to scale, stretch, or flow into multi-line layouts gracefully.

✅ বাংলায় Answer
MediaQuery: ডিভাইসের মোট স্ক্রিন সাইজ, হাইট, উইডথ এবং ওরিয়েন্টেশন (পোর্ট্রেট/ল্যান্ডস্কেপ) জানতে ব্যবহৃত হয়।

LayoutBuilder: নির্দিষ্ট উইজেটের প্যারেন্ট সাইজ (বক্স কনস্ট্রেইন্ট) পরিমাপ করে সে অনুযায়ী বড় স্ক্রিনে গ্রিড বা ছোট স্ক্রিনে কলাম দেখানোর সিদ্ধান্ত নিতে ব্যবহৃত হয়।

ফ্লেক্সিবল উইজেটস: Expanded, Flexible, FittedBox, এবং Wrap ব্যবহার করে রেসপনসিভ ও অভিযোজনযোগ্য লেআউট তৈরি করা হয়।

39. What are Keys inside AnimatedList and ReorderableListView?
✅ English Answer
In dynamic lists where items can be reordered, inserted, or dismissed, Flutter matches widgets to elements by type. If every item has the same widget type without an explicit identity, Flutter cannot track which item shifted, leading to incorrect visual state animations or corrupted checkmarks/inputs.

Providing a persistent ValueKey(item.id) to each item guarantees that the framework tracks the exact element state through layout recalculations and transitions.

✅ বাংলায় Answer
লিস্টের আইটেম যখন ড্র্যাগ করে সরানো হয় (Reorderable) অথবা অ্যানিমেশন দিয়ে রিমুভ করা হয়, তখন Flutter উইজেটের টাইপ দেখে সিদ্ধান্ত নেয়। যদি প্রতিটি রো দেখতে একই রকম হয় তবে ফ্রেমওয়ার্ক কনফিউজড হয়ে ভুল আইটেমের স্টেট আপডেট করে ফেলতে পারে।

প্রতিটি রোতে ইউনিক ValueKey(item.id) দিলে Flutter সঠিকভাবে বুঝতে পারে কোন আইটেমটি স্থানান্তরিত বা ডিলিট হচ্ছে, যার ফলে সঠিক অ্যানিমেশন এবং স্টেট অক্ষুণ্ণ থাকে।

40. What are the best practices for reducing app size in production?
✅ English Answer
App Bundles: Build Android App Bundles (flutter build appbundle) instead of fat APKs so Google Play delivers device-tailored APKs.

Resource Optimization: Compress images, convert assets to modern formats like WebP or vector SVGs, and avoid uncompressed audio files.

Font Subsetting: Remove unused font weights and glyphs, or fetch fonts dynamically via google_fonts.

ProGuard & R8: Enable code shrinking and resource minification in android/app/build.gradle.

Tree Shaking & Obfuscation: Flutter automatically tree-shakes unused icons (e.g., --shrink-resources). Use --obfuscate --split-debug-info to strip debug symbols into separate mapping files.

✅ বাংলায় Answer
১. App Bundle: বড় সাইজের universal APK না বানিয়ে flutter build appbundle ব্যবহার করা, যাতে প্লে-স্টোর প্রতিটি ফোনের জন্য আলাদা ছোট APK দেয়।
২. ছবি ও অ্যাসেট অপ্টিমাইজেশন: ভারী PNG/JPG-এর বদলে WebP বা SVG ব্যবহার করা এবং ছবি কম্প্রেস করে রাখা।
৩. ফন্ট ম্যানেজমেন্ট: অপ্রয়োজনীয় ফন্ট ডিক্লেয়ার না করা এবং ফন্ট প্যাকেজ অপ্টিমাইজ করা।
৪. R8 ও Minification: অ্যান্ড্রয়েডে ProGuard বা R8 অন করে অব্যবহৃত লাইব্রেরি কোড ছাঁটাই করা।
৫. কোড ও আইকন ট্রি-শেকিং: --split-debug-info ব্যবহার করে অ্যাপ সাইজ কমানো এবং রিলিজ বিল্ডে মেমরি অপ্টিমাইজেশন বজায় রাখা।