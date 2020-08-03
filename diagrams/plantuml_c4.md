-   Kroki: <https://kroki.io/>

## Project structure

### easyScience

    @startuml
    !include C4_Component.puml

    'LAYOUT_TOP_DOWN
    LAYOUT_AS_SKETCH()
    'LAYOUT_WITH_LEGEND()

    title easyScience diagram

    Container_Boundary(easyLibs, "easyLibs") {
        Component(easyCore, "easyCore", "repo", "Allows users to sign in to the internet banking system")
        Component(easySkeletonLib, "easySkeletonLib", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")
        Component(easyExampleLib, "easyExampleLib", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")
        Component(easyDiffractionLib, "easyDiffractionLib", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")
        Component(easySpectorscopyLib, "easySpectorscopyLib", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")

        Rel(easyCore, easySkeletonLib, "Uses")
        Rel_Neighbor(easySkeletonLib, easyExampleLib, "Uses")
        Rel(easySkeletonLib, easyDiffractionLib, "Uses")
        Rel(easySkeletonLib, easySpectorscopyLib, "Uses")
    }

    Container_Boundary(easyApps, "easyApps") {
        Component(easyBaseAppLogic, "easyBaseAppLogic", "repo", "Allows users to sign in to the internet banking system")
        Component(easyBaseAppGui, "easyBaseAppGui", "repo", "Allows users to sign in to the internet banking system")
        Component(easySkeletonApp, "easySkeletonApp", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")
        Component(easyExampleApp, "easyExampleApp", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")
        Component(easyDiffractionApp, "easyDiffractionApp", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")
        Component(easySpectorscopyApp, "easySpectorscopyApp", "Spring Bean", "Provides functionality related to singing in, changing passwords, etc.")

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

<https://kroki.io/c4plantuml/svg/eNrFVsFO4zAQvfsrvL1AJcSJD6BNK0BbtWhThPYUuck0tXDGlu0sRIh_xy6hSXDKcmnbS8cv8zyvmZmnXhvLtC0LQX5xTEWZAY2ukkgWSiKgvVT-ETmbjf4uHpbJcnGfTBaPc1KfR3ES_54uo9vz4S7n8W55m8ymN9P5xKHEciuAAjNVnHLAFGjGWa5ZQUgk0TKOoJOxLDFjujr3eTO-Mhd08BkOhvSVUPfZidpmRVJDneXDgYs1KOm_R0LIZ0NLA9pQK6nhOVKOPrQbcJEFjWDpiuETx5yaylgoBsOeKvETCLASnZC6WAvxtWKl_RVjYOiP91r-4xkYui4xtVwiE9xWVINgFrIPMZh7BscLmm7Yx0ExY56lztzvBpte9kqZvrBCCWiUNMBxhUz4eq3Z9tJGTBc8rqBYQWqlNqlUVatRXfSQkraa_oBoDWY4PA8GTC3fpSZz4PlmJXU4ZkGzu8x-QtCUn5DCF1ez3vYu50ipz-X04Z7lHDMD7vFM5jyts9vQgZa1LnFT8m5NBxzYHlyRL_bgkJPYQ6OkAU5mD42YLng6e2g1qosezR66qxEOUc_etuf6f4R-X9lmBlPyjUXsCEE3f0IK33jjK4HGttUFEu9cI7V1zID21fB6xe6nB9bXr3t3ASHXgJn7M_QOvXss_Q==>
