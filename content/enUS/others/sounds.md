---
title: Sounds
description: You can find all available sounds which can be used in GadgetsMenu plugin.
group: others
keywords: sounds
topics:
 - sounds
---

Looking for a sound but not sure what is the name? Check the link below to view the sound list. 


**Relevant Link:**
- [Sound List](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Sound.html)

## Sound only
**Format:**
```yaml
# Sound Format: [Sound]
# Volume and Pitch will be default as 1.0
Sound: 'ENTITY_EXPERIENCE_ORB_PICKUP'
```

## Sound with Volume
**Format:**
```yaml
# Sound Format: [Sound]:[volume]
# Pitch will be default as 1.0
Sound: 'ENTITY_EXPERIENCE_ORB_PICKUP:0.5'
```

## Sound with Volume and Pitch
**Format:**
```yaml
# Sound Format: [Sound]:[volume]:[pitch]
# Pitch range: 0.0 - 2.0
Sound: 'ENTITY_EXPERIENCE_ORB_PICKUP:1:2.0'
```