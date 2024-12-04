---
title: Hugo - Link im neuen Tab öffnen lassen
description: Einen Link in Markdown erstellen - der im neuen Tab öffnet
image: ""
author: Andreas Petersell
date: 2024-12-02T18:13:16.066Z
lastMod: null
draft: false
categories:
    - blogging
tags:
    - hugo
fmContentType: blog
---

In Markdown kann man standardmäßig nur Links zu Webseiten erstellen, die im selben Tab öffnen, nicht jedoch in einem neuen Tab geöffnet werden mit Hilfe des Attributs `target="_blank"`.
<!--more-->

Da ich inzwischen für das Schreiben meiner Hugo-Blogposts das Headless-CMS [Frontmatter](https://frontmatter.codes) nutze, möchte ich für einfache Texte wieder vermehrt Markdown nutzen. 

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

**(2)** - Im neuen Verzeichnis eine neue HTML-Datei erstellen. Ich nenne sie wie im Beispiel `a_blank.html`

**(3)** - Darin hineinkopieren:

```
<a target="_blank" href="{{ .Get 1 }}">{{ .Get 0 | markdownify }}</a>
```
**(4)** - In der eigentlichen Markdown-Content-Datei muss der Shortcode folgendermaßen eingebunden werden:

```
{{% a_blank "Shortcodes linking" "https://www.petersell.de" %}}
```

Klickt man jetzt auf diesen Link *Shortcodes linking* mit der URL www.petersell.de, öffnet sich die Webseite in einem neuen Tab.

#### Weitere Quellen
- [Raw HTML omitted Fehler](https://discourse.gohugo.io/t/hugo-0-60-0-raw-html-omitted-issue/22010/7)
- [gohugo.io - Create your own shortcodes](https://gohugo.io/templates/shortcode/)

