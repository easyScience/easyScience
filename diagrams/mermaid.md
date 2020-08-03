# Diagrams

Mermaid-based easyScience project diagrams.

-   About Mermaid: <https://mermaid-js.github.io/mermaid>
-   Flow charts: <https://mermaid-js.github.io/mermaid/#/flowchart>
-   Class diagrams: <https://mermaid-js.github.io/mermaid/#/classDiagram>
-   Live editor: <https://mermaidjs.github.io/mermaid-live-editor>
-   Chrome extension: <https://chrome.google.com/webstore/detail/mermaid-diagrams/phfcghedmopjadpojhmmaffjmfiakfil>

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

[Kroki-based](https://kroki.io/) diagram

![](https://kroki.io/mermaid/svg/eNq1VE1r3DAQvetX6LLQQtaQHnsopJs0FALNdtNz0SqzrlpZciW5xJj-92osf8iyDbuQ3mZGM0-jN2_EJbP2VrDcsIKQzYYehXoWKicEmK132gDdbj9QdA6_QILT6kEcSeLTLAs5dy-sKCVg6D3dSa2AWmcq7ioPdNKGwh8wNYWQNoPpr7oVp5Nh3IkQnkGtFh5K4M5oy3VZL1e2pR-ZhZuyfNC54LP3-YM46b4SqymRn1KAoUspwJoFChahVgtjCpYr_ZiTWfW1Y-9dTjKI5eZ87maJ_JWOWplh3OdYQjgqkA5qawbhke2WfhLOoRq9-eX408NYNL85IS0p69JojGVOF_KKPmturyg4npG_MWyskyZVDsLtmOSVZE4bRPcBPgSus7LGlM_KgTkxDl2G6P0n8IQxByEvPmlLz-0xmkVocQzg9Z13HdnvSJZlRBSlNu57T9mbt1PYZHwBeho8ByYdbMfiNLoO1I3bj34y7skSNrO9HAfd8rp3PpqDGYh-MkzZnvpzeY52ukmWHO-7UaJgSEwrs90PZoLgdtq_S4EK3p2Ewtto3kt9ZG2L9CtYXZmgEHpwtd_tSxWK69qki41wPSHefKz3hXw0-qUemNi7QZ6dXMNz0sYn_SIUy3s9x817t2BCZb8LSXr7cimPb4k-lTUpR7IZhe_FE8VjaSye-DeP8SQtnK2txthq8q8lip4uzv9tL_3F5yu30GCyka_f4T8jU9R2)

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
