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

### easyApps

```mermaid
classDiagram

class easyBaseAppLogic {
├── easyBaseAppLogic
│⠀  ├── Utils
│⠀  ├── QtLogger.py
│⠀  └── Translate.py
└── pyproject.toml, docs, etc.
}

class easyBaseAppGui {
├── easyBaseAppGui
│⠀  ├── Animations
│⠀  ├── Charts
│⠀  ├── Components
│⠀  ├── Element
│⠀  ├── Globals
│⠀  ├── Resources
│⠀  └── Style
└── pyproject.toml, docs, etc.
}

classDiagram

class easyBaseAppLogic {
├── easyBaseAppLogic
│⠀  ├── Utils
│⠀  ├── QtLogger.py
│⠀  └── Translate.py
└── pyproject.toml, docs, etc.
}

class easyBaseAppGui {
├── easyBaseAppGui
│⠀  ├── Animations
│⠀  ├── Charts
│⠀  ├── Components
│⠀  ├── Element
│⠀  ├── Globals
│⠀  ├── Resources
│⠀  └── Style
└── pyproject.toml, docs, etc.
}

class easySkeletonApp {
├── easySkeletonApp
│└── Logic
│ └── Logic
│  └── Logic
│   └── Logic
│    └── Logic
│     └── Logic
│      └── Logic
│       └── Logic
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
