---
id: dxDiagram.import(data, updateExistingItemsOnly)
---
---
##### shortDescription
Imports the diagram data.

##### param(data): String
The diagram data in JSON format.

##### param(updateExistingItemsOnly?): Boolean
**true** to apply diagram data without rewriting diagram items; **false** to apply diagram data and replace diagram items with items from the data parameter.

---
The [export](/api-reference/10%20UI%20Components/dxDiagram/3%20Methods/export().md '/Documentation/ApiReference/UI_Components/dxDiagram/Methods/#export') method allows you to save information about a diagram's layout, appearance, and shape positions. Use the **import** method to load this data on demand.

The diagram import updates the [bound data source](/concepts/05%20UI%20Components/Diagram/10%20Data%20Binding '/Documentation/Guide/UI_Components/Diagram/Data_Binding/')'s field values. If the values are not changed, the corresponding events (for instance, **onInserted** and **onUpdated**) do not fire.

[note] The Diagram stores an opened diagram's data in its own text format. Do not modify the data the [export](/api-reference/10%20UI%20Components/dxDiagram/3%20Methods/export().md '/Documentation/ApiReference/UI_Components/dxDiagram/Methods/#export') method returns because a modified document can be loaded incorrectly.

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/Diagram/Overview/"
}