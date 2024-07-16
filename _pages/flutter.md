---
title: Flutter
author: DomDom
date: 2022-02-05
category: Jekyll
layout: post
---


# Notes about Flutter


In dart private and public are determined by the name, if it starts with an underscore it's private.

Future are a little bit like promises in javascript

``` dart
Future<String> fetchUserData() {
  return Future.delayed(Duration(seconds: 2), () => "User data");
}

void main() async {
  print("Fetching user data...");
  String userData = await fetchUserData();
  print(userData);
}
```


State management
You have to choose the Right Tool: Whether it's:
 - Provider
 - Riverpod
 - Bloc



 a call to SetState rebuild the widget.


   if you let the package version empty in the pubspec, you will get the latest version



### factory
The factory keyword in Flutter (and Dart) is used to define a special type of constructor called a factory constructor. Here's a concise explanation:

Purpose: Factory constructors allow you to control object creation, potentially returning an instance from a cache or a subclass.
Key features:

Can return an existing instance instead of always creating a new one
Can return instances of subclasses
Don't have access to this keyword


Basic syntax:
dartCopyclass MyClass {
  factory MyClass() {
    // Custom logic for creating or returning an instance
  }
}

Use cases:

Implementing the Singleton pattern
Caching instances
Returning different subclass instances based on conditions




Scaffold is typically used as the root widget for each screen in your app, providing a consistent structure across different pages or views.

Map<String, dynamic> seems the way to do JSON.
dynamic is equivalent to unknown type

.. means "then" 

``` dart
    ModesModel()..loadConfig()
```
call to ModelsModel() constructor and then loadConfig  it's a chain.


  