---
id: GridBaseColumn.editorOptions
type: any
---
---
##### shortDescription
Configures the default UI component used for [editing](/api-reference/10%20UI%20Components/GridBase/1%20Configuration/editing '{basewidgetpath}/Configuration/editing/') and filtering in the [filter row](/api-reference/10%20UI%20Components/GridBase/1%20Configuration/filterRow '{basewidgetpath}/Configuration/filterRow/').

---
In this object, you can specify the default UI component's properties (except **onValueChanged**, which you can specify in [onEditorPreparing](/api-reference/10%20UI%20Components/dxDataGrid/1%20Configuration/onEditorPreparing.md '{basewidgetpath}/Configuration/#onEditorPreparing')).

The default editor UI component depends on the column configuration. The following table illustrates the dependency:

<table class="dx-table">
    <tr>
        <th colspan="2">Column Configuration</th>
        <th>Default Editor</th>
    </tr>
    <tr>
        <td rowspan="4"><a href="{basewidgetpath}/Configuration/columns/#dataType">dataType</a>:</td>
        <td>"date" <br> "datetime"</td>
        <td><a href="/Documentation/ApiReference/UI_Components/dxDateBox/Configuration/">DateBox</a></td>
    </tr>
    <tr>
        <td>"number"</td>
        <td><a href="/Documentation/ApiReference/UI_Components/dxNumberBox/Configuration/">NumberBox</a></td>
    </tr>
    <tr>
        <td>"boolean"</td>
        <td><a href="/Documentation/ApiReference/UI_Components/dxCheckBox/Configuration/">CheckBox</a></td>
    </tr>
    <tr>
        <td>"string" <br> "object"</td>
        <td><a href="/Documentation/ApiReference/UI_Components/dxTextBox/Configuration/">TextBox</a></td>
    </tr>
    <tr>
        <td colspan="2"><a href="{basewidgetpath}/Configuration/columns/lookup/">lookup</a> is defined</td>
        <td><a href="/Documentation/ApiReference/UI_Components/dxSelectBox/Configuration/">SelectBox</a></td>
    </tr>
</table>

Because of this dependency, **editorOptions** cannot be typed and are not implemented as nested configuration components in Angular, Vue, and React. In these frameworks, specify **editorOptions** with an object. We recommend that you declare the object outside the configuration component in Vue and React to prevent possible issues caused by unnecessary re-rendering.

---
##### Angular

    <!-- tab: app.component.html -->
    <dx-{widget-name} ... >
        <dxi-column ...
            [editorOptions]="{ format: 'currency', showClearButton: true }">
        </dxi-column>
    </dx-{widget-name}>

    <!-- tab: app.module.ts -->
    import { BrowserModule } from '@angular/platform-browser';
    import { NgModule } from '@angular/core';
    import { AppComponent } from './app.component';

    import { Dx{WidgetName}Module } from 'devextreme-angular';

    @NgModule({
        declarations: [
            AppComponent
        ],
        imports: [
            BrowserModule,
            Dx{WidgetName}Module
        ],
        providers: [ ],
        bootstrap: [AppComponent]
    })
    export class AppModule { }

##### Vue

    <!-- tab: App.vue -->
    <template>
        <Dx{WidgetName} ... >
            <DxColumn ...
                :editor-options="columnEditorOptions"
            />
        </Dx{WidgetName}>
    </template>

    <script>
    import 'devextreme/dist/css/dx.light.css';

    import Dx{WidgetName}, {
        DxColumn
    } from 'devextreme-vue/{widget-name}';

    export default {
        components: {
            Dx{WidgetName},
            DxColumn
        },
        data() {
            return {
                columnEditorOptions: { format: 'currency', showClearButton: true }
            }
        }
    }
    </script>

##### React

    <!-- tab: App.js -->
    import React from 'react';

    import 'devextreme/dist/css/dx.light.css';

    import {WidgetName}, {
        Column
    } from 'devextreme-react/{widget-name}';

    class App extends React.Component {
        columnEditorOptions = { format: 'currency', showClearButton: true };

        render() {
            return (
                <{WidgetName} ... >
                    <Column ...
                        editorOptions={this.columnEditorOptions}
                    />
                </{WidgetName}>
            );
        }
    }
    export default App;

---

#include common-demobutton with {
    url: "https://js.devexpress.com/Demos/WidgetsGallery/Demo/DataGrid/CustomEditors/"
}

Other properties that allow editor customization include:

- **columns[]**.[editCellTemplate](/api-reference/_hidden/dxTreeListColumn/editCellTemplate.md '{basewidgetpath}/Configuration/columns/#editCellTemplate')         
Use it to replace the default editor.

- [onEditorPreparing](/api-reference/10%20UI%20Components/dxDataGrid/1%20Configuration/onEditorPreparing.md '{basewidgetpath}/Configuration/#onEditorPreparing')         
Use it to:
    - Change the editor type.
    - Override the default editor's **onValueChanged** handler.
    - [Dynamically change editor properties in the editing state](/concepts/05%20UI%20Components/DataGrid/99%20How%20To/Dynamically%20Change%20Editor%20Properties%20in%20the%20Editing%20State.md '/Documentation/Guide/UI_Components/DataGrid/How_To/Dynamically_Change_Editor_Properties_in_the_Editing_State/').
    - Implement other customization cases.

#####See Also#####
- **columns[]**.[showEditorAlways](/api-reference/_hidden/GridBaseColumn/showEditorAlways.md '{basewidgetpath}/Configuration/columns/#showEditorAlways')