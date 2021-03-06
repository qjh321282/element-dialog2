# element-dialog2
an extension of element-dialog that allow you to use it nested

[![aaa][npm-version]][npm-home]

[npm-version]: https://img.shields.io/npm/v/element-dialog2.svg 'npm-version'
[npm-home]: https://www.npmjs.com/package/element-dialog2 'element-dialog2'

- dependence      
    [element-ui][element]   
    
    [element]: https://github.com/ElemeFE/element "element-ui"

> versions 

- 0.0.5   
    `open` and `close` envents won't be `$emited` repeated.
- 0.0.4   
    currently vue@2.3.0+ with element-ui@1.3.0+ work correct.


> useage  

 - install
    ```shell
    npm install element-dialog2 --save
    ```
 - use
    ```javascript
    //common 
    var ElDialog2 = require('element-dialog2');
    Vue.component(ElDialog2.name,ElDialog2);
    //import form source
    import ElDialog2 from 'element-dialog2/src/index.js';
    Vue.component(ElDialog2.name,ElDialog2)
    ```
 - code
    ```html
    <el-dialog2 title="this is title"  v-if="showed" v-model="showed"
        v-on:close="handleClose">
        <span>code of $slots.default</span>
        <div slot="footer">
            code of $slots.footer
        </div>
    </el-dialog2>
    ```
    ```html
    <el-dialog2   v-if="showed" v-model="showed"
        v-on:close="handleClose">
        <div slot="title">
            this is title
        </div>
        <span>code of $slots.default</span>
        <div slot="footer">
            code of $slots.footer
        </div>
    </el-dialog2>
    ```

> ### Attributes

| Attribute     |Compare Element | Description          | Type      | Accepted Values       | Default  |
|---------- |------|-------------- |---------- |--------------------------------  |-------- |
| title     |same| title of Dialog. Can also be passed with a named slot (see the following table) | string    | — | — |
| size      |same| size of Dialog | string    | tiny/small/large/full | small |
| top      |same| value for `top` of Dialog CSS, works when `size` is not `full` | string    | — | 15% |
| modal    |same | whether a mask is displayed | boolean   | — | true |
| modal-append-to-body     |same| whether to append modal to body element. If false, the modal will be appended to Dialog's parent element | boolean   | — | true |
| lock-scroll     |same| whether scroll of body is disabled while Dialog is displayed | boolean   | — | true |
| custom-class      |same| custom class names for Dialog | string    | — | — |
| close-on-click-modal |default value diffrent| whether the Dialog can be closed by clicking the mask | boolean    | — | `false` |
| close-on-press-escape |same| whether the Dialog can be closed by pressing ESC | boolean    | — | true |
| show-close |same| whether to show a close button | boolean    | — | true |
| before-close |same| beforeclose(close) | Function    | — | null |

- beforeClose
    new in `element-ui@1.3.0+` 
    ```javascript
        beforeClose(close){
            if(...){
                // hook of close
                close();
            }
        }
    ```

> ### Slot

| Name | Description |
|------|--------|
| — | content of Dialog |
| title | content of the Dialog title |
| footer | content of the Dialog footer |