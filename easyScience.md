# Diagrams

Mermaid-based easyScience project diagrams.

* About Mermaid: https://mermaid-js.github.io/mermaid
* Live editor: https://mermaidjs.github.io/mermaid-live-editor

## Flow charts

Manual: https://mermaid-js.github.io/mermaid/#/flowchart

### easyScience

```mermaid
graph LR
	easyScience -.- easyApps
	easyScience -.- easyLibs 

	subgraph easyLibs
		%%a[...]
	end
	subgraph easyApps
		%%b[...]
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
```

## Class diagrams

Manual: https://mermaid-js.github.io/mermaid/#/classDiagram

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
