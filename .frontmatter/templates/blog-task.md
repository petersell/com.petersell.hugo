---
title: Titel
description: Beschreibung ohne Komma
image: ""
author: Andreas Petersell
date: 
lastMod: null
draft: true
categories:
    - blogging
tags:
    - hugo
fmContentType: blog
---

In Markdown kann man standardmäßig nur Links zu Webseiten erstellen, die im selben Tab öffnen, nicht jedoch in einem neuen Tab geöffnet werden.
<!--more-->

Quelle: [How to target blank in md?](https://discourse.gohugo.io/t/how-to-target--blank-in-md/524/19)

### Anleitung

Das Attribut `target="_blank"` kann man mit Hilfe von Shortcodes in einer HTML-Datei realisieren.

#### Voraussetzung

Damit HTML-Code innerhalb der Markdown-Datei gerendert wird, muss einmalig in der `config.toml` folgender Eintrag gemacht werden:

```
[markup.goldmark.renderer]
unsafe = true
```
#### Arbeitsschritte

**(1)** - Einen neuen Ordner `shortcodes` im Hugo-Verzeichnis `layouts` erstellen

**(2)** - In der eigentlichen Markdown-Content-Datei muss der Shortcode folgendermaßen eingebunden werden:

```
{{% a_blank "Shortcodes linking" "https://www.petersell.de" %}}
```

Klickt man jetzt auf diesen Link *Shortcodes linking* mit der URL www.petersell.de, öffnet sich die Webseite in einem neuen Tab.

#### Weitere Quellen
- [gohugo.io - Create your own shortcodes](https://gohugo.io/templates/shortcode/)

