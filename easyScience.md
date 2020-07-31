# Diagrams

Mermaid-based easyScience project diagrams.

* About Mermaid: https://mermaid-js.github.io/mermaid
* Flow charts: https://mermaid-js.github.io/mermaid/#/flowchart
* Class diagrams: https://mermaid-js.github.io/mermaid/#/classDiagram
* Live editor: https://mermaidjs.github.io/mermaid-live-editor

## Project structure

### easyScience

```mermaid
graph LR

easyScience -.- easyApps
easyScience -.- easyLibs 

subgraph easyLibs
end
subgraph easyApps
end
```

### easyLibs

```mermaid
graph LR

subgraph easyLibs
	easyCore --> easySkeletonLib

	easySkeletonLib -.-> easyExampleLib
	easySkeletonLib --> easyDiffractionLib
	easySkeletonLib --> easySpectroscopyLib
end
subgraph easyApps
	easyExampleLib --> easyExampleApp
	easyDiffractionLib --> easyDiffractionApp
	easySpectroscopyLib --> easySpectroscopyApp
end
```

### easyApps

```mermaid
graph LR

subgraph easyApps
	easyBaseAppLogic --> easySkeletonApp
	easyBaseAppGui --> easySkeletonApp

	easySkeletonApp -.-> easyExampleApp
	easySkeletonApp --> easyDiffractionApp
	easySkeletonApp --> easySpectroscopyApp
end

subgraph easyLibs
	easyExampleApp --- easyExampleLib
	easyDiffractionApp --- easyDiffractionLib
	easySpectroscopyApp --- easySpectroscopyLib
end
```

## Repo structure

### easyScience (small)

```mermaid
classDiagram

easyCore --> easySkeletonLib
easySkeletonLib ..> easyExampleLib
easySkeletonLib --> easyDiffractionLib
easySkeletonLib --> easySpectroscopyLib

easyBaseAppLogic --> easySkeletonApp
easyBaseAppGui --> easySkeletonApp
easySkeletonApp ..> easyExampleApp
easySkeletonApp --> easyDiffractionApp
easySkeletonApp --> easySpectroscopyApp

%%easyExampleLib --> easyExampleApp
%%easyDiffractionLib --> easyDiffractionApp
%%%easySpectroscopyLib --> easySpectroscopyApp
```

### easyScience (medium)

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
import easyCore()
}

class easyDiffractionLib {
easyDiffractionLib
...
import easyCore()
}

class easySpectroscopyLib {
easySpectroscopyLib
...
import easyCore()
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
import easyExampleLib()
import easyBaseAppLogic()
import easyBaseAppGui()
import Logic()
import Gui()
}

class easyDiffractionApp {
easyDiffractionApp
...
import easyDiffractionLib()
import easyBaseAppLogic()
import easyBaseAppGui()
import Logic()
import Gui()
}

class easySpectroscopyApp {
easySpectroscopyApp
...
import easySpectroscopyLib()
import easyBaseAppLogic()
import easyBaseAppGui()
import Logic()
import Gui()
}
```

## Class diagrams

```mermaid
classDiagram

	Descriptor <|-- Parameter
	Parameter <|-- Lattice
	Parameter <|-- Atom

	class Descriptor {
	}

	class Parameter {
	}

	class Lattice {
		+real a
		+real b
		+real c
		+real volume()
		fa:fa-ban qwe
	}

	class Atom {
	}
```
