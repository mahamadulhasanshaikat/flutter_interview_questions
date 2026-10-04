## Flutter Interview Questions — Part 2
## Advanced Dart, State Management & Architecture — Mid level Developer

---

## 1. What is the difference between synchronous and asynchronous programming in Dart?
### ✅ English Answer
Synchronous: Code executes sequentially, line by line. Each task must finish before the next one starts, meaning long tasks can block UI execution.

Asynchronous: Tasks run without blocking the main execution thread. Dart uses the Event Loop alongside async, await, Future, and Stream to process background I/O operations while keeping the UI responsive.

### ✅ বাংলায় Answer
Synchronous: কোড পর্যায়ক্রমে একটির পর একটি লাইন এক্সিকিউট হয়। একটি কাজ শেষ না হওয়া পর্যন্ত পরের কাজটি শুরু হয় না, যার ফলে ভারী কাজে UI আটকে (freeze) যেতে পারে।

Asynchronous: মূল থ্রেড না থামিয়েই দীর্ঘমেয়াদী কাজ (যেমন নেটওয়ার্ক কল বা ফাইল রিড) সম্পন্ন করে। Dart-এ Event Loop, async, await, Future এবং Stream ব্যবহার করে UI সচল রাখা হয়।

## 2. What is State Management and why is it needed?
### ✅ English Answer
State is any data that exists in memory and shapes the current UI presentation. State management provides a predictable, organized way to update data, share state across deep widget hierarchies, and trigger rebuilds only for specific components instead of relying on inefficient state lifting or passing arguments down multiple constructor layers.

### ✅ বাংলায় Answer
অ্যাপ্লিকেশনের স্ক্রিনে যা কিছু দেখানো হয় এবং মেমরিতে যেসব ডেটা সংরক্ষিত থাকে তা-ই স্টেট।

অ্যাপের সাইজ বড় হলে এক স্ক্রিন থেকে অন্য স্ক্রিনে ডেটা সহজে শেয়ার করতে, উইজেটের ভেতর দিয়ে অপ্রয়োজনীয় প্রপস পাসিং এড়াতে এবং শুধুমাত্র নির্দিষ্ট উইজেট রিবিল্ড করে পারফরম্যান্স ভালো রাখতেই স্টেট ম্যানেজমেন্ট প্রয়োজন।

## 3. Compare Provider, Riverpod, and BLoC.
### ✅ English Answer
Provider: A wrapper around InheritedWidget. It relies heavily on BuildContext, making it simple for small-to-medium apps but prone to runtime lookup exceptions.

Riverpod: A compile-safe rewrite of Provider. It does not depend on BuildContext, supports global provider declaration, and eliminates ProviderNotFoundException.

BLoC (Business Logic Component): An event-driven architecture based on reactive Streams. It completely separates business logic from UI, making it ideal for large-scale enterprise applications requiring strict testability.

### ✅ বাংলায় Answer
Provider: InheritedWidget-এর ওপর ভিত্তি করে তৈরি। এটি BuildContext-এর ওপর সরাসরি নির্ভরশীল। ছোট বা মাঝারি প্রজেক্টের জন্য চমৎকার, তবে রানটাইম এররের সম্ভাবনা থাকে।

Riverpod: Provider-এর আধুনিক রূপ। এটি BuildContext ছাড়াই কাজ করে, সম্পূর্ণ compile-time safe এবং রানটাইমে প্রোভাইডার খুঁজে না পাওয়ার কোনো ঝুঁকি থাকে না।

BLoC: স্ট্রিম (Stream) এবং ইভেন্ট-ভিত্তিক আর্কিটেকচার। এটি UI থেকে বিজনেস লজিককে সম্পূর্ণ আলাদা রাখে, যা বড় প্রজেক্ট ও টেস্টেবল কোড লেখার জন্য সবচেয়ে জনপ্রিয়।

## 4. Explain Flutter's Three Trees: Widget, Element, and RenderObject.
### ✅ English Answer
Widget Tree: Immutable configurations and declarative blueprints of what the UI should look like. Cheap to create and dispose.

Element Tree: The structural backbone that manages the lifecycle of widgets and coordinates updates between configurations and screen rendering.

RenderObject Tree: The mutable engine responsible for measuring sizes, computing layout constraints, and painting pixels directly onto the display canvas.

### ✅ বাংলায় Answer
Widget Tree: স্ক্রিন কেমন দেখাবে তার ডিক্লারেটিভ ব্লুপ্রিন্ট বা কনফিগারেশন। এটি তৈরি ও মুছে ফেলা অত্যন্ত হালকা (lightweight)।

Element Tree: উইজেট ও রেন্ডার অবজেক্টের মধ্যকার সেতুবন্ধন। এটি স্টেট এবং উইজেটের লাইফসাইকেল পরিচালনা করে।

RenderObject Tree: স্ক্রিনের সাইজ হিসাব করা, লেআউট পজিশনিং নির্ধারণ করা এবং সরাসরি ডিসপ্লেতে ড্র (paint) করার মূল দায়িত্ব পালন করে।

## 5. What are Dart Isolates and when should you use them?
### ✅ English Answer
Dart is single-threaded and runs on an Event Loop. Asynchronous operations handle waiting for I/O, but heavy CPU computations can drop frames and freeze UI. An Isolate is an independent execution worker with its own dedicated memory heap and event loop. Isolates communicate through port-based message passing. They should be used for heavy JSON parsing, cryptography, audio/image processing, or complex data filtering.

### ✅ বাংলায় Answer
Dart মূলত একটি Single-threaded ভাষা যা Event Loop-এ চলে। async/await শুধু ডেটার জন্য অপেক্ষা করে, কিন্তু ভারী হিসাব-নিকাশ করলে মেইন থ্রেড জ্যাম হয়ে স্ক্রিন ল্যাগ করে।

Isolate হলো আলাদা একটি মেমরি এবং থ্রেড যেখানে ব্যাকগ্রাউন্ডে ভারী কাজ করানো হয়। বিশাল আকারের JSON পার্সিং, ইমেজ বা ভিডিও প্রসেসিং এবং ভারী গাণিতিক হিসাবের ক্ষেত্রে Isolate ব্যবহার করা হয়।

## 6. How do you prevent and detect Memory Leaks in Flutter?
### ✅ English Answer
Prevention: Always dispose controllers (TextEditingController, ScrollController, AnimationController) and cancel StreamSubscriptions or periodic Timers inside the dispose() method.

Detection: Use the Flutter DevTools Memory Profiler to inspect memory allocations, examine memory snapshots, and identify retained objects that fail garbage collection.

### ✅ বাংলায় Answer
প্রতিরোধ: উইজেট বন্ধ হওয়ার সময় dispose() মেথডের ভেতরে সব ধরনের কন্ট্রোলার (TextEditingController, AnimationController, ScrollController) ক্লোজ করতে হবে এবং চলমান StreamSubscription বা Timer ক্যানসেল করতে হবে।

শনাক্তকরণ: Flutter DevTools-এর Memory Profiler ব্যবহার করে অ্যাপের মেমরি স্ন্যাপশট দেখে অপ্রয়োজনীয় অবজেক্ট শনাক্ত ও সমাধান করা যায়।

## 7. How does Flutter communicate with Native Code using Platform Channels?
### ✅ English Answer
Flutter connects to native host platforms via Platform Channels using message serialization:

MethodChannel: Used for named, one-off asynchronous method invocations between Dart and native code (Kotlin/Java on Android, Swift/Objective-C on iOS).

EventChannel: Used for continuous native data streams (e.g., streaming device sensor or battery readings).

BasicMessageChannel: Used for continuous bidirectional message passing.

### ✅ বাংলায় Answer
Flutter প্ল্যাটফর্ম চ্যানেলের মাধ্যমে মেসেজ পাস করে নেটিভ কোডের সাথে যোগাযোগ করে:

MethodChannel: ডার্ট থেকে নেটিভ ফাংশন কল করতে বা নেটিভ প্ল্যাটফর্ম থেকে একক ফলাফল পেতে ব্যবহৃত হয়।

EventChannel: নেটিভ থেকে অনবরত স্ট্রিম ডেটা (যেমন সেন্সর ডেটা বা ব্যাটারি লেভেল মনিটরিং) ডার্টে পাঠাতে ব্যবহৃত হয়।

BasicMessageChannel: দুইমুখী সাধারণ মেসেজ আদান-প্রদানে ব্যবহৃত হয়।

## 8. What is the difference between Imperative Routing (Navigator 1.0) and Declarative Routing (GoRouter / Navigator 2.0)?
### ✅ English Answer
Navigator 1.0: Imperative stack-based routing using explicit push/pop methods (Navigator.push(), Navigator.pop()). Difficult to synchronize with web browser URL bars and complex deep links.

GoRouter / Navigator 2.0: Declarative and URL-path driven. It treats routing as application state, making deep linking, query parameters, web forward/back navigation, and auth-based redirection seamless.

### ✅ বাংলায় Answer
Navigator 1.0: স্ক্রিন পুশ এবং পপ (push/pop) করার ইম্পারেটিভ পদ্ধতি। সাধারণ মোবাইল অ্যাপের জন্য সহজ হলেও ওয়েব ব্রাউজারের URL বা ডিপ লিঙ্কিং হ্যান্ডেল করা জটিল।

GoRouter (Navigator 2.0): ইউআরএল পাথ-ভিত্তিক ডিক্লারেটিভ রাউটিং। এটি অ্যাপের বর্তমান স্টেট দেখে স্ক্রিন রেন্ডার করে, যা ওয়েব রাউটিং, ডিপ লিঙ্কিং এবং লগইন রিডাইরেকশনের জন্য আদর্শ।

## 9. How do you optimize Flutter app performance and reduce unnecessary rebuilds?
### ✅ English Answer
Mark immutable widgets with the const constructor to avoid rebuilding static trees.

Break large monolithic widgets into smaller modular components.

Use targeted listeners/selectors (e.g., context.select() in Provider or BlocSelector in BLoC) rather than listening to broad states.

Avoid performing expensive computations or network instantiation inside the build() method.

Use lazy-loaded lists (ListView.builder) instead of rendering whole collections inside single children containers.

### ✅ বাংলায় Answer
উইজেটের আগে const ব্যবহার করা, যাতে প্রতিবার অপ্রয়োজনীয়ভাবে রিবিল্ড না হয়।

বড় উইজেটকে ভেঙে ছোট ছোট আলাদা উইজেটে ভাগ করা।

সম্পূর্ণ প্রোভাইডার লিসেন না করে নির্দিষ্ট ডেটার জন্য সিলেক্টর (context.select() বা BlocSelector) ব্যবহার করা।

build() মেথডের ভেতরে কোনো ভারী হিসাব বা API কল না রাখা।

বড় লিস্ট দেখানোর জন্য সাধারণ কলামের বদলে ListView.builder ব্যবহার করা।

10. What is an Offline-First architecture and how is it implemented?
### ✅ English Answer
An offline-first architecture ensures that an application functions seamlessly without an active internet connection.

Local storage (SQLite/Hive/ObjectBox) acts as the single source of truth for the UI.

When a user performs operations, data is committed locally first.

A background synchronization service queues API sync requests, detects network connectivity changes, and syncs updates to the remote server once the connection is restored.

### ✅ বাংলায় Answer
অফলাইন-ফার্স্ট আর্কিটেকচার নিশ্চিত করে যে ইন্টারনেট সংযোগ না থাকলেও অ্যাপ যাতে স্বাভাবিকভাবে ব্যবহার করা যায়।

UI সবসময় লোকাল ডাটাবেজ (যেমন SQLite, Hive) থেকে ডেটা পড়ে প্রদর্শিত হয়।

ব্যবহারকারী কোনো পরিবর্তন করলে তা প্রথমে লোকাল ডাটাবেজে সেভ হয়।

ব্যাকগ্রাউন্ড সিঙ্ক সার্ভিস নেটওয়ার্ক কানেকশন পেলেই কিউ (Queue) থেকে ডেটা রিমোট সার্ভারে পাঠিয়ে সিঙ্ক সম্পন্ন করে।