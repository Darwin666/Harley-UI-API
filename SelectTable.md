## SelectTable 下拉表格

用表格展示选项的下拉框，可自定义表格搜索条件或分页。



### Attributes

| 参数            | 说明                                  | 类型            | 可选值        | 默认值 |
| :-------------- | :------------------------------------ | :-------------- | :------------ | :----- |
| value / v-model | 绑定值                                | String / Number | -             | -      |
| data            | 表格数据源                            | Array           | -             | []     |
| props           | data数据源键名配置，参数见下方Props表 | Object          | -             | {}     |
| columns         | 列的数组，具体参数见下方Columns表     | Array           | -             | []     |
| custom          | 是否展示自定义的el-popover的reference | Boolean         | -             | false  |
| disabled        | 是否禁用                              | Boolean         | -             | false  |
| type            | 展示类型                              | String          | normal / text | normal |
| placeholder     | 占位符                                | String          | -             | 请选择 |
| width           | 组件宽度                              | String / Number | -             | 200    |
| default-label   | 默认标题                              | String          | -             | -      |
| showPagination  | 是否展示分页组件                      | Boolean         | -             | false  |
| page-size       | 每页显示条目个数，支持 .sync 修饰符   | Number          | -             | 10     |
| total           | 总条目数                              | Number          | -             | -      |
| current-page    | 当前页数，支持 .sync 修饰符           | Number          | -             | 1      |



#### Props

| 参数  | 说明                                      | 类型   | 可选值 | 默认值 |
| ----- | ----------------------------------------- | ------ | ------ | ------ |
| label | 选项的标签，若不设置则默认与 `value` 相同 | String | -      | -      |
| value | 选项的值                                  | String | -      | -      |

 

#### Columns

| 参数                  | 说明                                       | 类型                                    | 可选值                | 默认值 |
| --------------------- | ------------------------------------------ | --------------------------------------- | --------------------- | ------ |
| label                 | 对应el-table-column的label                 | String                                  | -                     | -      |
| value                 | 对应el-table-column的prop                  | String                                  | -                     | -      |
| hide                  | 是否隐藏列                                 | Boolean                                 | -                     | false  |
| width                 | 对应el-table-column的width                 | String                                  | -                     | -      |
| min-width             | 对应el-table-column的min-width             | String                                  | -                     | -      |
| fixed                 | 对应el-table-column的fixed                 | String / Boolean                        | true, left, right     | -      |
| resizable             | 对应el-table-column的resizable             | Boolean                                 | false                 | -      |
| formatter             | 对应el-table-column的formatter             | Function(row, column, cellValue, index) | -                     | -      |
| show-overflow-tooltip | 对应el-table-column的show-overflow-tooltip | Boolean                                 | false                 | -      |
| align                 | 对应el-table-column的align                 | String                                  | left / center / right | left   |
| header-align          | 对应el-table-column的header-align          | String                                  | left / center / right | -      |
| class-name            | 对应el-table-column的class-name            | String                                  | -                     | -      |
| label-class-name      | 对应el-table-column的label-class-name      | String                                  | -                     | -      |
| header-slot-name      | 自定义表头列slot的名称                     | String                                  | -                     | -      |
| slot-name             | 自定义表体列slot的名称                     | String                                  | -                     | -      |

 

### Events

| 事件名称                  | 说明                                     | 回调参数                      |
| :------------------------ | :--------------------------------------- | :---------------------------- |
| change                    | 选中值发生变化时触发                     | value, row                    |
| visible-change            | 下拉框出现/隐藏时触发                    | 出现则为 true，隐藏则为 false |
| size-change               | pageSize 改变时会触发                    | 每页条数                      |
| pagination-current-change | currentPage 改变时会触发                 | 当前页                        |
| clear                     | 可清空的单选模式下用户点击清空按钮时触发 | -                             |
| blur                      | 当 input 失去焦点时触发                  | (event: Event)                |
| focus                     | 当 input 获得焦点时触发                  | (event: Event)                |



### Slots

| name   | 说明                          |
| :----- | :---------------------------- |
| -      | 表格中自定义内容              |
| head   | popover弹出部分的头部区域     |
| custom | 自定义的el-popover的reference |

