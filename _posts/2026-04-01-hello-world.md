---
title: "Welcome to my blog"
date: 2026-04-01 12:00:00 +0200
categories: [Meta, Dev]
tags: [flutter, godot, blog]
image:
  path: assets/img/avatar.jpg
  alt: DomDumont
---

Hey, I'm **Dominique** — developer, game maker, tinkerer.

I've been building mobile apps and game prototypes for a while, mostly in silence.
This blog is where I stop doing that.

## What I'll write about

- **Flutter & Dart** — mobile dev tips, state management, things that tripped me up
- **Godot** — game dev experiments and postmortems
- **Tools & workflow** — git tricks, CI/CD, automation
- **App releases** — when I ship something, I'll announce it here

## A quick taste

Here's the kind of thing you'll find — a Flutter snippet I use all the time:

```dart
extension ContextExtension on BuildContext {
  bool get isMobile => MediaQuery.of(this).size.width < 600;
}
```

And a Godot GDScript one:

```gdscript
func _ready() -> void:
    print("Hello from %s" % name)
```

## Stay tuned

Posts will be irregular — I write when I have something worth sharing, not on a schedule.

If you want to follow along, there's an RSS feed at the bottom of the page.
