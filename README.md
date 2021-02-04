# latex-nomnoml
LaTeX package to interface with `nomnoml` (npm)

Source : https://github.com/Kochise/latex-nomnoml

![nomnoml-no](https://memegenerator.net/img/instances/48933296/nom-nom-n-no.jpg)

## installation

Get `nvm` for `Windows` : https://github.com/coreybutler/nvm-windows/releases<br>
Uncompress/install it where you need.<br>

```batch
\>cd nvm
\nvm>nvm install 12.17.0
\nvm>nvm use 12.17.0
\nvm>node -v
v12.17.0
\nvm>npm install --global nomnoml
\nvm>npm install --global nomnoml-cli

xcopy /c /h /e /r /q /y latex-nomnoml <miktex>\texmfs\install\tex\latex\nomnoml
start "" "<miktex>\miktex-portable.cmd"
```

Refresh the filename database.<br>
Update the package database.<br>
You should be ready to go.<br>

Alternatively, you can use https://github.com/Kochise/win_portable

## usage

See https://github.com/skanaar/nomnoml<br>
See https://github.com/prantlf/nomnoml-cli<br>

In your preamble :

```latex
\def\imagepath{./images}
\graphicspath{{\imagepath/}}
\usepackage[imagepath=\imagepath]{nomnoml}
```

In your document :

```latex
%\begin{nomnoml}[width]{caption}{refname}
\begin{nomnoml}[8cm]{nomnoml caption example}{nomnomlexample}
[Pirate|eyeCount: Int|raid();pillage()|
  [beard]--[parrot]
  [beard]-:>[foul mouth]
]

[<table>mischief | bawl | sing || yell | drink]

[<abstract>Marauder]<:--[Pirate]
[Pirate]- 0..7[mischief]
[jollyness]->[Pirate]
[jollyness]->[rum]
[jollyness]->[singing]
[Pirate]-> *[rum|tastiness: Int|swig()]
[Pirate]->[singing]
[singing]<->[rum]

[<start>st]->[<state>plunder]
[plunder]->[<choice>more loot]
[more loot]->[st]
[more loot] no ->[<end>e]

[<actor>Sailor] - [<usecase>shiver me;timbers]
\end{nomnoml}
```

![smcat](https://raw.githubusercontent.com/Kochise/latex-nomnoml/master/nomnoml.png)

## options

What is available through `nomnoml-cli` (not `nomnoml`) :

```
# Output usage information
-h, --help

# Output the version number
-V, --version

# File with nomnoml source to read from
-i, --input <path>

# File for the image output to write to
-o, --output <path>

# Output format (png or svg) /!\ OUTPUT ONLY PNG DATA
-f, --format <format>

# Width of the canvas to draw on
-w, --width <pixels>

# Height of the canvas to draw on
-h, --height <pixels>
```

Yeah, there are two `-h`...

Cannot be specified on a group basis, only in the preamble.<br>
Just add the requested parameters without the leading/separator dash(es).<br>

```latex
\usepackage[V]{nomnoml}
```

or :

```latex
\usepackage[height={pixels}]{nomnoml}
```

Avoid :

```
h, help		: because useless
V, version	: because useless, unless debug log
i, input	: because used by the provided text
o, output	: because using the refname
```

## limitations

Your imagination.

## greetings

Based on https://github.com/dakusui/latex-ditaa<br>
Also interested into https://github.com/sile-typesetter/sile<br>
