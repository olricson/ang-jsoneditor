# Angular 4 Json Editor

Angular 4 Json Editor (wrapper for jsoneditor). View/Edit Json file with formatting.

## Installation

To install this library with npm, run below command:

$ npm install --save ng-json-editor

## Usage

### Configuration

First, Import Angular 4 JsonEditor module in root

```ts
import { NgJsonEditorModule } from 'angular-jsoneditor' 

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    ....,
    NgJsonEditorModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
Then setup your component models as below :

```ts
import { Component, ViewChild } from '@angular/core';
import { JsonEditorComponent, JsonEditorOptions } from 'ng-json-editor/jsoneditor/jsoneditor.component';

@Component({
  selector: 'app-root',
  template: '<json-editor [options]="editorOptions" [data]="data"></json-editor>',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  public editorOptions: JsonEditorOptions;
  public data: any;
  @ViewChild(JsonEditorComponent) editor: JsonEditorComponent;

  constructor() { 
    this.editorOptions = new JsonEditorOptions()
    this.editorOptions.modes = ['code', 'text', 'tree', 'view']; // set all allowed modes
    //this.options.mode = 'code'; //set only one mode
      
      this.data = {"products":[{"name":"car","product":[{"name":"honda","model":[{"id":"civic","name":"civic"},{"id":"accord","name":"accord"},{"id":"crv","name":"crv"},{"id":"pilot","name":"pilot"},{"id":"odyssey","name":"odyssey"}]}]}]}
  }

}
```
Note : For better styling, add below line to your main style.css file

```ts
@import "~jsoneditor/dist/jsoneditor.min.css";
```

# Demo
Demo component files are included in Git Project.

Demo Project:
[https://github.com/mariohmol/ng-json-editor/tree/master/src/app/demo)

# License
MIT(./LICENSE)