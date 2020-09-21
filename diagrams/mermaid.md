# Diagrams

Mermaid-based easyScience project diagrams.

- About Mermaid: https://mermaid-js.github.io/mermaid
- Flow charts: https://mermaid-js.github.io/mermaid/#/flowchart
- Class diagrams: https://mermaid-js.github.io/mermaid/#/classDiagram
- Live editor: https://mermaidjs.github.io/mermaid-live-editor
- Chrome extension: https://chrome.google.com/webstore/detail/mermaid-diagrams/phfcghedmopjadpojhmmaffjmfiakfil
- Atom package: https://atom.io/packages/atom-mermaid

## Project structure

### easyScience

```mermaid
classDiagram

easyScience .. easyLibs
easyScience .. easyApps
```

[Kroki-based](https://kroki.io/) image

![](https://kroki.io/mermaid/svg/eNpLzkksLnbJTEwvSszl4kpNLK4MTs5MzUtOVdDTUwBxfTKTirGJOxYUFAMAnpAVfA==)

### easyLibs

```mermaid
classDiagram

easyCore --> easyExampleLib
easyExampleLib ..> easyDiffractionLib
easyExampleLib ..> easySpectroscopyLib
```

[Kroki-based](https://kroki.io/) image

![](https://kroki.io/mermaid/svg/eNpLzkksLnbJTEwvSszl4kpNLK50zi9KVdDVtVMAcVwrEnMLclJ9MpO4ULkKenoQFS6ZaWlFicklmfl5eFQFF6QmlxTlFyfnF1QCxQG7ViqD)

### easyApps

```mermaid
classDiagram

easyBaseAppLogic --> easyExampleApp
easyBaseAppGui --> easyExampleApp
easyExampleApp ..> easyDiffractionApp
easyExampleApp ..> easySpectroscopyApp
```

[Kroki-based](https://kroki.io/) image

![](https://kroki.io/mermaid/svg/eNpLzkksLnbJTEwvSszl4kpNLK50SixOdSwo8MlPz0xW0NW1UwAJulYk5hbkgMSR1biXZuJSgeAq6OlBVLhkpqUVJSaXZObn4VEVXJCaXFKUX5ycX1AJFAcA6fc5qg==)

### Repo structure

```mermaid
classDiagram

%% binding

easyCore --> easyExampleLib
easyExampleLib ..> easyDiffractionLib : Clone structure
easyExampleLib ..> easySpectroscopyLib : Clone structure

easyBaseAppLogic --> easyExampleApp
easyBaseAppGui --> easyExampleApp
easyExampleApp ..> easyDiffractionApp : Clone structure
easyExampleApp ..> easySpectroscopyApp : Clone structure

%%easyExampleLib --> easyExampleApp
%%easyDiffractionLib --> easyDiffractionApp
%%easySpectroscopyLib --> easySpectroscopyApp

%% easyLibs

class easyCore {
easyCore
-- Elements
---- Cell.py
-- Fitting
----- bumps.py
----- lmfit.py
----- fitting_template.py
----- Fitting.py
-- Objects
-- Utils
pyproject.toml, docs, etc.
}

class easyExampleLib {
easySkeletonLib
-- Calculators
---- calculator1.py
---- calculator2.py
-- Interfaces
---- interface1.py
---- interface2.py
---- interfaceTemplate.py
interface.py
model.py
pyproject.toml, docs, etc.
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

class easyExampleApp {
easyExampleApp
-- Logic
---- PyQmlProxy.py
-- Gui
---- Components
---- Globals
---- Pages
---- Resources
---- main.qml
-- main.py
pyproject.toml, docs, etc.
import_easyExampleLib()
import_easyBaseAppLogic()
import_easyBaseAppGui()
}

class easyDiffractionApp {
easyDiffractionApp
...
import_easyDiffractionLib()
import_easyBaseAppLogic()
import_easyBaseAppGui()
}

class easySpectroscopyApp {
easySpectroscopyApp
...
import_easySpectroscopyLib()
import_easyBaseAppLogic()
import_easyBaseAppGui()
}
```

[Kroki-based](https://kroki.io/) image

![](https://kroki.io/mermaid/svg/eNqlVE1v3CAQvfMruERqpdhSc-yhUup8qFKkJt30HLHs2CXlq4ClWKv-94KNbcx6N2l7Yx4z8ObNA8qJtVeMNIYIhM7O8JbJHZMNQkBsVykDuCg-4RBcvxChOdyxLVqGuCyHjCtW14ZQx5QM8EdccSUBW2da6loDx-o2GqgzylKlu_XCvvIzsXCp9Z1qGM1ZeTzNuW3ZsYw5XOMd4JO807qU93qhVzTreYXVkJOJN-YtucXcXLAxOSPUDzTgPsciRMOs8TTX_TRiVBT4moMA6axf-6gCzkvdhY0b5lwwRNFvbFuh7bATQi5q5uawHnKfHPjeiIN5J54Sz_y6ffZEw134u2PcIt1powJWOiX4Od4pas8xOFqi3ynxRMiB_uYncHC9ZOG0inDa-puViY3QCfgwkkmwi8jni3RgakIhVrExnosm6OIQekzancAQCLWDXscT_TGhlXFP4yzevV92nNli6HoJorJ89ZjcMVG9JXr8oOgj76mFjxYvcn_wSOf59no9OI82YCYBHw2RdhTurRZIXvg-e_LhvkvJBAnC9O6qfhAz-KxSvi8ZHT66PSxvudqSniL-Bla1ZnAB3riOw98aM_wC--y7CIeNcvjlffcg-L1RL10030A8p7hgFspIM7ozpelDQZgsfwmOxvWb_Ta_Jj_lBE9nuLrjKZ_w6SxC9nll9lq6-P8p5N_xocdXSGRP4N9Y_AFZc35M)

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

[Kroki-based](https://kroki.io/) image

![](https://kroki.io/mermaid/svg/eNpLzkksLnbJTEwvSszl4nJJLU4uyiwoyS9SsKnR1VUISAQKp5akFnHBWRAJn8SSkszkVHRhx5J8oCnJIDNhShSquTi1i1ITcxQSYYwkGCMZxijLzynNTdXQ5KrlAgDviC6W)
