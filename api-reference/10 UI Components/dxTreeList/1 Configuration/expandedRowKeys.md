---
id: dxTreeList.Options.expandedRowKeys
type: Array<any>
default: []
firedEvents: optionChanged
---
---
##### shortDescription
Specifies keys of the initially expanded rows.

---
Setting this property expands only the specified rows, but not their parents. If a to-be-expanded row lies deep in the hierarchy, make sure to include keys of all rows that nest it.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/TreeList/Overview/"
}

#####See Also#####
- [autoExpandAll](/api-reference/10%20UI%20Components/dxTreeList/1%20Configuration/autoExpandAll.md '/Documentation/ApiReference/UI_Components/dxTreeList/Configuration/#autoExpandAll')
- [Expand and Collapse Rows](/concepts/05%20UI%20Components/TreeList/60%20Expand%20and%20Collapse%20Rows/20%20API.md '/Documentation/Guide/UI_Components/TreeList/Expand_and_Collapse_Rows/#API')
