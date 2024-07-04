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

