## Project structure

### easyScience

```
@startuml
!include C4_Component.puml

'LAYOUT_TOP_DOWN
'LAYOUT_AS_SKETCH()
'LAYOUT_WITH_LEGEND()

title easyScience diagram

Container_Boundary(easyLibs, "easyLibs") {
    Component(easyCore, "easyCore", "repo", "Allows users to ...")
    Component(easySkeletonLib, "easySkeletonLib", "repo", "Provides functionality related to ...")
    Component(easyExampleLib, "easyExampleLib", "repo", "Provides functionality related to ...")
    Component(easyDiffractionLib, "easyDiffractionLib", "repo", "Provides functionality related to ...")
    Component(easySpectorscopyLib, "easySpectorscopyLib", "repo", "Provides functionality related to ...")

    Rel(easyCore, easySkeletonLib, "Uses")
    Rel_Neighbor(easySkeletonLib, easyExampleLib, "Uses")
    Rel(easySkeletonLib, easyDiffractionLib, "Uses")
    Rel(easySkeletonLib, easySpectorscopyLib, "Uses")
}

Container_Boundary(easyApps, "easyApps") {
    Component(easyBaseAppLogic, "easyBaseAppLogic", "repo", "Allows users to ...")
    Component(easyBaseAppGui, "easyBaseAppGui", "repo", "Allows users to ...")
    Component(easySkeletonApp, "easySkeletonApp", "repo", "Provides functionality related to ...")
    Component(easyExampleApp, "easyExampleApp", "repo", "Provides functionality related to ...")
    Component(easyDiffractionApp, "easyDiffractionApp", "repo", "Provides functionality related to ...")
    Component(easySpectorscopyApp, "easySpectorscopyApp", "repo", "Provides functionality related to ...")

    Rel(easyBaseAppLogic, easySkeletonApp, "Uses")
    Rel(easyBaseAppGui, easySkeletonApp, "Uses")
    Rel_Neighbor(easySkeletonApp, easyExampleApp, "Uses")
    Rel(easySkeletonApp, easyDiffractionApp, "Uses")
    Rel(easySkeletonApp, easySpectorscopyApp, "Uses")
}

Rel_Neighbor(easyExampleLib, easyExampleApp, "Import")
Rel_Neighbor(easyDiffractionLib, easyDiffractionApp, "Import")
Rel_Neighbor(easySpectorscopyLib, easySpectorscopyApp, "Import")

@enduml
``` 

[Kroki-based](https://kroki.io/) diagram

![](https://kroki.io/c4plantuml/svg/eNqtVV1vgjAUfedXdL5Mk8Wn_QARiZoRNQNj9kQqXF2z2pK2bDPL_vuKQT4sOqPwQnO4556be-8pA6mwUOmOWg-ERTSNATnPocN3CWfAVD_JPlmPnv02XwZhMF-Eo_lqVgC2H_ovbuBMur0CW02DSei5Y3c20qiliKKAAMu9HxFgEaCY4K3AO8tyOFOYMBDhkKcsxmLfzeI8spZPqHM8dnrox0L6Kao6RDlcQB6VHTv6LCDh2dumlH9JlEoQEimO-v1-p9eQwv8ACoozrZJnqiDVhAvBP0kMEm1SFinCGaZE7ZEAihXElyTcb7xLKJQKJdCOwIhsNgIfOKVIHWxHyE8gUlzIiCf7SsPq6C1SB61XoJWpmsNZSpB5WTo0nAHZvq-5MMdoNL3ObCYYTbyGZDYkZ_2e3Ww7SY6bnR3PbPYQS9CfPb4lUR5dhW7Z9Jw_Tkk9oQbuMY7OcGIcjbRqnFKhBFo3TilSB9s3TqVhdfRu49SXxhxSw0ZXl-I_QrPjDpHGtC6YpyAY3b-GZHaydJxRY_USMEqc6gEJpZkG7fQqaCz2PN24FJrrLhJYA2Cx_sf-AeVYi_0=)
