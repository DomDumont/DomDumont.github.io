---
title: Godot
author: DomDom
date: 2022-02-05
category: Jekyll
layout: post
---


# Notes about Godot

When you need to know of your game is launched from the editor or directly, you can use a custom feature

![alt text](/assets/img/godot_export_custom_feature.png)


and in your code, test the presence of this feature :

``` python
if OS.has_feature("standalone"):
    print("Running an exported build.")
    
else:
    print("Running from the editor.")    
```
