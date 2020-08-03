# Diagrams

Mermaid-based easyScience project diagrams.

* About Mermaid: https://mermaid-js.github.io/mermaid
* Flow charts: https://mermaid-js.github.io/mermaid/#/flowchart
* Class diagrams: https://mermaid-js.github.io/mermaid/#/classDiagram
* Live editor: https://mermaidjs.github.io/mermaid-live-editor
* Chrome extension: https://chrome.google.com/webstore/detail/mermaid-diagrams/phfcghedmopjadpojhmmaffjmfiakfil

## Project structure

### easyScience

```mermaid
classDiagram

easyScience .. easyLibs
easyScience .. easyApps
```

### easyLibs

```mermaid
classDiagram

easyCore --> easySkeletonLib
easySkeletonLib ..> easyExampleLib
easySkeletonLib --> easyDiffractionLib
easySkeletonLib --> easySpectroscopyLib
```

### easyApps

```mermaid
classDiagram

easyBaseAppLogic --> easySkeletonApp
easyBaseAppGui --> easySkeletonApp
easySkeletonApp ..> easyExampleApp
easySkeletonApp --> easyDiffractionApp
easySkeletonApp --> easySpectroscopyApp
```

### Repo structure

```mermaid
classDiagram

%% binding

easyCore --> easySkeletonLib
easySkeletonLib ..> easyExampleLib : Clone structure for every example
easySkeletonLib --> easyDiffractionLib : Clone structure
easySkeletonLib --> easySpectroscopyLib : Clone structure

easyBaseAppLogic --> easySkeletonApp
easyBaseAppGui --> easySkeletonApp
easySkeletonApp ..> easyExampleApp : Clone structure for every example
easySkeletonApp --> easyDiffractionApp : Clone structure
easySkeletonApp --> easySpectroscopyApp : Clone structure

%%easyExampleLib --> easyExampleApp
%%easyDiffractionLib --> easyDiffractionApp
%%%easySpectroscopyLib --> easySpectroscopyApp

%% easyLibs

class easyCore {
easyCore
-- Fitting
-- Objects
-- Utils
pyproject.toml, docs, etc.
}

class easySkeletonLib {
easySkeletonLib
-- Calculators
---- calculator1.py
-- Interfaces
---- interfaceTemplate.py
---- interface1.py
pyproject.toml, docs, etc.
}

class easyExampleLib {
easyExampleLib
-- Example1
-- Example2
...
import_easyCore()
}

class easyDiffractionLib {
easyDiffractionLib
...
import_easyCore()
}

class easySpectroscopyLib {
easySpectroscopyLib
...
import_easyCore()
}

%% easyApps

class easyBaseAppLogic {
easyBaseAppLogic
-- Utils
---- QtLogger.py
---- Translate.py
pyproject.toml, docs, etc.
}

class easyBaseAppGui {
easyBaseAppGui
-- Animations
-- Charts
-- Components
-- Element
-- Globals
-- Resources
-- Style
pyproject.toml, docs, etc.
}

class easySkeletonApp {
easySkeletonApp
-- Logic
---- PyQmlProxy.py
---- QtInterface.py
-- Gui
---- Components
---- Globals
---- Pages
---- Resources
---- main.qml
-- main.py
pyproject.toml, docs, etc.
}

class easyExampleApp {
easyExampleApp
-- Example1
-- Example2
import_easyExampleLib()
import_easyBaseAppLogic()
import_easyBaseAppGui()
import_Logic()
import_Gui()
}

class easyDiffractionApp {
easyDiffractionApp
...
import_easyDiffractionLib()
import_easyBaseAppLogic()
import_easyBaseAppGui()
import_Logic()
import_Gui()
}

class easySpectroscopyApp {
easySpectroscopyApp
...
import_easySpectroscopyLib()
import_easyBaseAppLogic()
import_easyBaseAppGui()
import_Logic()
import_Gui()
}
```

## Class diagrams

#### easyCore.Objects.Base

```mermaid
classDiagram

Descriptor <|-- Parameter
Parameter <|-- Lattice
Parameter <|-- Atom

class Lattice {
	+real a
	+real b
	+real c
	+real volume()
}
```