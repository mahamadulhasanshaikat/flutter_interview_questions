# Flutter Interview Questions — Part 4
# Low-Level Internals, CI/CD, Rendering Engine & Advanced Dart
---

## 1. What is the difference between Flutter's Skia and Impeller rendering engines?
### ✅ English Answer
Skia: The legacy 2D graphics engine used by Flutter. It compiles shaders at runtime (just-in-time), which can cause initial animation stutter, known as shader compilation jank.

Impeller: The modern rendering engine built specifically for Flutter. It precompiles a complete set of shaders at build time, completely eliminating shader compilation jank, and optimizes GPU workloads natively for Metal on iOS and Vulkan on Android.

### ✅ বাংলায় Answer
Skia: ফ্ল্যাটারের পুরোনো ২ডি রেন্ডারিং ইঞ্জিন। এটি রানটাইমে শেডার কম্পাইল করত, যার ফলে অ্যাপের প্রথমবার অ্যানিমেশন চলার সময় হালকা ল্যাগ বা ফ্রেম ড্রপ (Shader Jank) হতো।

Impeller: ফ্ল্যাটারের আধুনিক ও উন্নত রেন্ডারিং ইঞ্জিন। এটি বিল্ড হওয়ার সময়ই সব শেডার কম্পাইল করে নেয়, ফলে কোনো প্রকার অ্যানিমেশন জ্যাঙ্ক হয় না এবং iOS (Metal) ও Android (Vulkan)-এ অনেক বেশি স্মুথ পারফরম্যান্স দেয়।

## 2. What is a BuildContext and why is it important?
### ✅ English Answer
BuildContext is a locator handle that represents the location of a widget within the framework's Element Tree. It is used to traverse the tree to find ancestor widgets, inherit data (such as Theme.of(context), MediaQuery.of(context)), and obtain layout information. Each widget has its own unique BuildContext, passed via its build method.

### ✅ বাংলায় Answer
BuildContext হলো মূলত Element Tree-তে কোনো নির্দিষ্ট উইজেটের বর্তমান অবস্থানের ঠিকানা বা রেফারেন্স।

এর মাধ্যমে উইজেট ট্রির উপরের প্যারেন্টদের সাথে যোগাযোগ করা, থিম বা স্ক্রিন সাইজ জানা (Theme.of(context), MediaQuery.of(context)) এবং নেভিগেশন পরিচালনা করা যায়। প্রতিটি উইজেটের নিজস্ব একটি ইউনিক BuildContext থাকে।

## 3. How does the Event Loop work in Dart (Microtask Queue vs Event Queue)?
### ✅ English Answer
Dart is single-threaded and executes asynchronous code using an Event Loop with two priority queues:

Microtask Queue: Holds internal, short-lived tasks that must execute immediately before any other event (e.g., scheduleMicrotask).

Event Queue: Holds external events such as user input, I/O operations, timers, drawing events, and standard Future completions.

The Event Loop completely drains the Microtask Queue before processing the next item in the Event Queue.

### ✅ বাংলায় Answer
Dart-এর Event Loop মূলত দুটি কিউ (Queue) নিয়ে কাজ করে:

Microtask Queue: এটি সর্বোচ্চ প্রায়োরিটি পায়। কোনো কাজ খুব দ্রুত বা ইমিডিয়েট শেষ করতে এটি ব্যবহার করা হয়।

Event Queue: সাধারণ বাহ্যিক ইভেন্ট যেমন বাটন ক্লিক, টাইমার, ফাইল রিড/রাইট এবং সাধারণ Future-এর কাজগুলো এখানে জমা থাকে।

Event Loop সবসময় Microtask Queue-এর সব কাজ আগে শেষ করে, তারপর Event Queue থেকে একটি করে কাজ এক্সিকিউট করে।

## 4. What is the purpose of CustomPainter and how does it work?
### ✅ English Answer
CustomPainter is an API that allows developers to bypass standard layout widgets and directly draw arbitrary 2D shapes, custom paths, gradients, charts, and animations onto a Canvas.

It overrides two primary methods:

paint(Canvas canvas, Size size): Contains the actual drawing instructions using lines, arcs, circles, or paths.

shouldRepaint(covariant CustomPainter oldDelegate): Returns a boolean indicating whether the canvas needs to be repainted when new configurations are passed.

### ✅ বাংলায় Answer
CustomPainter এমন একটি ক্লাস যা দিয়ে সাধারণ উইজেটের বাইরে সরাসরি ক্যানভাসে দাগ কেটে কাস্টম শেইপ, লাইন, গ্রাফ, চার্ট বা জটিল ড্রয়িং আঁকা যায়।

এতে দুটি মূল মেথড ওভাররাইড করতে হয়:

paint(): ক্যানভাসের ওপর লাইন বা শেইপ আঁকার মূল কোড এখানে থাকে।

shouldRepaint(): ডাটা পরিবর্তন হলে ক্যানভাস পুনরায় ড্র করতে হবে কিনা তা চেক করে ট্রু বা ফলস রিটার্ন করে পারফরম্যান্স রক্ষা করে।

## 5. How do you configure CI/CD pipelines for Flutter applications?
### ✅ English Answer
A continuous integration and continuous deployment (CI/CD) pipeline (e.g., GitHub Actions, Codemagic, Bitrise) automates building and shipping apps:

Static Analysis & Linting: Runs dart analyze and dart format --output=none --set-exit-if-changed to enforce code quality.

Automated Testing: Runs flutter test to ensure all unit and widget tests pass.

Build & Signing: Securely injects signing keys, keystores, provisioning profiles, and environment variables to build release binaries (.aab for Android, .ipa for iOS).

Distribution: Automatically uploads the build artifacts to Google Play Internal Testing, Apple TestFlight, or Firebase App Distribution.

### ✅ বাংলায় Answer
GitHub Actions বা Codemagic দিয়ে ফ্ল্যাটার অ্যাপের অটোমেশন (CI/CD) পাইপলাইন সেটআপ করা হয়:

কোড কোয়ালিটি চেক: কোড পুশ করার সাথে সাথে স্বয়ংক্রিয়ভাবে flutter analyze ও ফরম্যাটিং চেক হয়।

অটোমেটেড টেস্ট: সব flutter test রান হয়ে কোনো বাগ আছে কিনা যাচাই করা হয়।

অটো বিল্ড ও সাইনিং: সিক্রেট কি (Keystore বা Certificates) ব্যবহার করে রিলিজ ফাইল (.aab বা .ipa) বিল্ড করা হয়।

ডেলিভারি: স্বয়ংক্রিয়ভাবে Google Play Console (Internal Track) বা Apple TestFlight-এ বিল্ডটি আপলোড হয়ে যায়।

## 6. What are Streams, StreamControllers, and the difference between Single-subscription and Broadcast Streams?
### ✅ English Answer
Stream: A source of asynchronous sequence data.

StreamController: A controller that allows producing and sinking events into a stream while listening to its state.

Single-subscription Stream: Allows only one listener across its entire lifetime. If a second listener attaches, an exception is thrown (e.g., reading a file buffer).

Broadcast Stream: Allows multiple listeners at the same time. Listeners can register and unregister dynamically, and all active listeners receive events simultaneously (e.g., global event bus or click streams).

### ✅ বাংলায় Answer
Stream: সময়ের সাথে সাথে ধারাবাহিকভাবে আসা ডেটার একটি পাইপলাইন।

StreamController: স্ট্রিমের ভেতর ডেটা পাঠানো (sink.add) এবং কন্ট্রোল করার মূল ব্যবস্থা।

Single-subscription Stream: এতে লাইফটাইমে মাত্র একজন লিসেনার ডেটা শুনতে পারে। দ্বিতীয় কেউ লিসেন করতে গেলে এরর দেখায় (যেমন: ফাইল রিড করা)।

Broadcast Stream: এতে একই সাথে একাধিক লিসেনার যুক্ত হতে পারে এবং একসাথে সবার কাছে ডেটা পাঠানো যায় (যেমন: লাইভ চ্যাট বা ক্লিক ইভেন্ট)।

## 7. What is the difference between ephemeral state and app state?
### ✅ English Answer
Ephemeral State (Local State): State that is neatly contained within a single widget and does not affect the rest of the application (e.g., the current page in a PageView, selected tab in a BottomNavigationBar, text inside a single field). Usually managed with setState().

App State (Global/Shared State): State that needs to be shared across many parts of the application or maintained across user sessions (e.g., user authentication status, e-commerce shopping cart, user profile data). Handled using state management libraries like Provider, Riverpod, or BLoC.

### ✅ বাংলায় Answer
Ephemeral State (লোকাল স্টেট): যা কেবল একটি নির্দিষ্ট উইজেটের ভেতরেই সীমাবদ্ধ এবং পুরো অ্যাপে এর প্রভাব পড়ে না (যেমন: পেজ ভিউয়ার কারেন্ট ইনডেক্স, ড্রপডাউন সিলেক্ট করা)। এটি setState() দিয়ে ম্যানেজ করা যায়।

App State (গ্লোবাল স্টেট): যা পুরো অ্যাপের একাধিক স্ক্রিনে দরকার হয় এবং অনেক উইজেটকে প্রভাবিত করে (যেমন: ইউজার লগইন স্ট্যাটাস, কার্টের পণ্য তালিকা)। এটি প্রোভাইডার, রিভারপড বা ব্লকের মতো স্টেট ম্যানেজমেন্ট দিয়ে পরিচালনা করতে হয়।