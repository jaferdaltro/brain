---
apple-notes-id: 59BF4087-588D-491C-BDC4-894F4764FA93
---
| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">clg→</p> | console log console.log(object); |
| <p style="text-align:right;margin:0">clg2→</p> | console log console.log('tag', object); |


Get and Set

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">tgt→</p> | get object this.get(object) |
| <p style="text-align:right;margin:0">tst</p> | set objectthis.set(object) |
| <p style="text-align:right;margin:0">cgt→</p> | get object from controller (used in model hooks) controller.get(object) |
| <p style="text-align:right;margin:0">cst→</p> | set object on controller (used in model hooks) controller.set('tag', object) |
| <p style="text-align:right;margin:0">tcgt</p> | get object from controller this.controller.get(object) |
| <p style="text-align:right;margin:0">tcst→</p> | set object on controller this.controller.set('tag', object) |


Functions

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">func→</p> | function with no params functionName() {} |
| <p style="text-align:right;margin:0">func1→</p> | function with 1 param functionName(param) {} |
| <p style="text-align:right;margin:0">func2→</p> | function with 2 params functionName(param1, param2) {} |
| <p style="text-align:right;margin:0">func3→</p> | function with 3 params functionName(param1, param2, param3) {} |


Service

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">serv→</p> | destruncting a service serviceName: service('serviceSlug') |


Import

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">imp→</p> | import a module import moduleName from 'module'; |


Super

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">sup→</p> | super context this._super(...arguments); |


Computed Property

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">comp→</p> | computed property with one property computedProperty: computed('property', { get() {} }) |


Component Lifecycle Hooks

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">chook→</p> | component generic hook hookName() { this._super(...arguments); } |
| <p style="text-align:right;margin:0">cinit→</p> | component init hook init() { this._super(...arguments); } |
| <p style="text-align:right;margin:0">cdra→</p> | component didReceiveAttrs hook didReceiveAttrs() { this._super(...arguments); } |
| <p style="text-align:right;margin:0">cdr→</p> | component didRender hook didRender() { this._super(...arguments); } |
| <p style="text-align:right;margin:0">cdua→</p> | component didUpdateAttrs hook didUpdateAttrs() { this._super(...arguments); } |
| <p style="text-align:right;margin:0">cdie→</p> | component didInsertElement hook didInsertElement() { this._super(...arguments); } |
| <p style="text-align:right;margin:0">cwde→</p> | component willDestroyElement hook willDestroyElement() { this._super(...arguments); } |


Ember Store Commands

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">sinj→</p> | inject store store: inject.service() |
| <p style="text-align:right;margin:0">sfr→</p> | store find record this.get('store).findRecord(model, id) |
| <p style="text-align:right;margin:0">spr→</p> | store peek record this.get('store).peekRecord(model, id) |
| <p style="text-align:right;margin:0">sfa→</p> | store find all this.get('store).findAll(model) |
| <p style="text-align:right;margin:0">spa→</p> | store peek all this.get('store).peekAll(model) |
| <p style="text-align:right;margin:0">sqa→</p> | store query and then |


Handlebars Snippets for EmberJS
Below is a list of all available handlebars snippets and the triggers of each one. The **⇥** means the TAB key.

| **Trigger** | **Content** |
| -- | -- |
| <p style="text-align:right;margin:0">get→</p> | get helper {{get object "property"}} |
| <p style="text-align:right;margin:0">act→</p> | action helper {{action "action-name"}} |
| <p style="text-align:right;margin:0">act1→</p> | action helper with one param {{action "action-name" "param"}} |
| <p style="text-align:right;margin:0">log→</p> | log a message to console {{log object}}}} |
| <p style="text-align:right;margin:0">input→</p> | input component {{input value=value}} |
| <p style="text-align:right;margin:0">link→</p> | link-to helper |
| <p style="text-align:right;margin:0">if→</p> | block if helper |
| <p style="text-align:right;margin:0">inif→</p> | inline if helper |
| <p style="text-align:right;margin:0">un→</p> | block unless helper |
| <p style="text-align:right;margin:0">inun→</p> | inline unless helper |
| <p style="text-align:right;margin:0">ifel→</p> | if else block helper |
| <p style="text-align:right;margin:0">unel→</p> | unless else block helper |
| <p style="text-align:right;margin:0">ifelif→</p> | if else-if block helper |
| <p style="text-align:right;margin:0">each→</p> | each loop helper |
| <p style="text-align:right;margin:0">eachx→</p> | each loop with index helper |
| <p style="text-align:right;margin:0">eachin→</p> | each in loop helper to iterate through properties of a object |
| <p style="text-align:right;margin:0">eachinel→</p> | each in loop with else helper |


Contribute
More snippets or any modifications to the existing ones are welcome!