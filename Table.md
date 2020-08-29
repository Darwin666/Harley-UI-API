## Table 表格

用于展示多条结构类似的数据，可对数据进行排序、筛选、对比或其他自定义操作，可展示分页组件。



### Attributes

| 参数                    | 说明                                                         | 类型                                                    | 可选值                                                       | 默认值                                                     |
| :---------------------- | :----------------------------------------------------------- | :------------------------------------------------------ | :----------------------------------------------------------- | :--------------------------------------------------------- |
| data                    | 显示的数据                                                   | Array                                                   | -                                                            | -                                                          |
| columns                 | 列的数组，具体参数见下方Columns表                            | Array                                                   | -                                                            | []                                                         |
| height                  | 表格高度                                                     | String / Number                                         | -                                                            | -                                                          |
| max-height              | Table 的最大高度                                             | String / Number                                         | -                                                            | -                                                          |
| multiple                | 表格是否展示多选列                                           | Boolean                                                 | -                                                            | false                                                      |
| selectable              | 仅对 type=selection 的列有效，类型为 Function，Function 的返回值用来决定这一行的 CheckBox 是否可以勾选 | Function(row, index)                                    | -                                                            | -                                                          |
| reserve-selection       | 仅对 type=selection 的列有效，类型为 Boolean，为 true 则会在数据更新之后保留之前选中的数据（需指定 `row-key`） | Boolean                                                 | -                                                            | false                                                      |
| all-selectable          | 是否展示全选框                                               | Boolean                                                 | -                                                            | true                                                       |
| showIndex               | 表格是否展示序号列                                           | Boolean                                                 | -                                                            | true                                                       |
| stripe                  | 是否为斑马纹 table                                           | Boolean                                                 | -                                                            | false                                                      |
| border                  | 是否带有纵向边框                                             | Boolean                                                 | -                                                            | true                                                       |
| size                    | Table 的尺寸                                                 | String                                                  | medium / small / mini                                        | -                                                          |
| fit                     | 列的宽度是否自撑开                                           | Boolean                                                 | -                                                            | true                                                       |
| show-header             | 是否显示表头                                                 | Boolean                                                 | -                                                            | true                                                       |
| show-body               | 是否显示表体                                                 | Boolean                                                 | -                                                            | true                                                       |
| highlight-current-row   | 是否要高亮当前行                                             | Boolean                                                 | -                                                            | true                                                       |
| current-row-key         | 当前行的 key，只写属性                                       | String / Number                                         | -                                                            | -                                                          |
| row-style               | 行的 style 的回调方法，也可以使用一个固定的 Object 为所有行设置一样的 Style。 | Function({row, rowIndex}) / Object                      | -                                                            | -                                                          |
| cell-class-name         | 单元格的 className 的回调方法，也可以使用字符串为所有单元格设置一个固定的 className。 | Function({row, column, rowIndex, columnIndex}) / String | -                                                            | -                                                          |
| cell-style              | 单元格的 style 的回调方法，也可以使用一个固定的 Object 为所有单元格设置一样的 Style。 | Function({row, column, rowIndex, columnIndex}) / Object | -                                                            | -                                                          |
| header-row-class-name   | 表头行的 className 的回调方法，也可以使用字符串为所有表头行设置一个固定的 className。 | Function({row, rowIndex}) / String                      | -                                                            | -                                                          |
| header-row-style        | 表头行的 style 的回调方法，也可以使用一个固定的 Object 为所有表头行设置一样的 Style。 | Function({row, rowIndex}) / Object                      | -                                                            | -                                                          |
| header-cell-class-name  | 表头单元格的 className 的回调方法，也可以使用字符串为所有表头单元格设置一个固定的 className。 | Function({row, column, rowIndex, columnIndex}) / String | -                                                            | -                                                          |
| header-cell-style       | 表头单元格的 style 的回调方法，也可以使用一个固定的 Object 为所有表头单元格设置一样的 Style。 | Function({row, column, rowIndex, columnIndex}) / Object | -                                                            | -                                                          |
| row-key                 | 行数据的 Key，用来优化 Table 的渲染；在使用 reserve-selection 功能与显示树形数据时，该属性是必填的。类型为 String 时，支持多层访问：`user.info.id`，但不支持 `user.info[0].id`，此种情况请使用 `Function`。 | Function(row) / String                                  | -                                                            | -                                                          |
| empty-text              | 空数据时显示的文本内容，也可以通过 `slot="empty"` 设置       | String                                                  | -                                                            | -                                                          |
| default-expand-all      | 是否默认展开所有行，当 Table 中存在 type="expand" 的 Column 的时候有效 | Boolean                                                 | -                                                            | false                                                      |
| expand-row-keys         | 可以通过该属性设置 Table 目前的展开行，需要设置 row-key 属性才能使用，该属性为展开行的 keys 数组。 | Array                                                   | -                                                            | -                                                          |
| default-sort            | 默认的排序列的 prop 和顺序。它的`prop`属性指定默认的排序的列，`order`指定默认排序的顺序 | Object                                                  | `order`: ascending, descending                               | 如果只指定了`prop`, 没有指定`order`, 则默认顺序是ascending |
| tooltip-effect          | tooltip `effect` 属性                                        | String                                                  | dark/light                                                   |                                                            |
| show-summary            | 是否在表尾显示合计行                                         | Boolean                                                 | -                                                            | false                                                      |
| sum-text                | 合计行第一列的文本                                           | String                                                  | -                                                            | 合计                                                       |
| summary-method          | 自定义的合计计算方法                                         | Function({ columns, data })                             | -                                                            | -                                                          |
| span-method             | 合并行或列的计算方法                                         | Function({ row, column, rowIndex, columnIndex })        | -                                                            | -                                                          |
| select-on-indeterminate | 在多选表格中，当仅有部分行被选中时，点击表头的多选框时的行为。若为 true，则选中所有行；若为 false，则取消选择所有行 | Boolean                                                 | -                                                            | true                                                       |
| show-pagination         | 是否展示分页组件                                             | Boolean                                                 | -                                                            | false                                                      |
| small                   | 是否使用小型分页样式                                         | Boolean                                                 | -                                                            | false                                                      |
| background              | 是否为分页按钮添加背景色                                     | Boolean                                                 | -                                                            | false                                                      |
| page-size               | 每页显示条目个数，支持 .sync 修饰符                          | Number                                                  | -                                                            | 10                                                         |
| total                   | 总条目数                                                     | Number                                                  | -                                                            | -                                                          |
| page-count              | 总页数，total 和 page-count 设置任意一个就可以达到显示页码的功能；如果要支持 page-sizes 的更改，则需要使用 total 属性 | Number                                                  | -                                                            | -                                                          |
| pager-count             | 页码按钮的数量，当总页数超过该值时会折叠                     | Number                                                  | 大于等于 5 且小于等于 21 的奇数                              | 7                                                          |
| current-page            | 当前页数，支持 .sync 修饰符                                  | Number                                                  | -                                                            | 1                                                          |
| layout                  | 组件布局，子组件名用逗号分隔                                 | String                                                  | `sizes`, `prev`, `pager`, `next`, `jumper`, `->`, `total`, `slot` | 'jumper, prev, pager, next, sizes, total'                  |
| page-sizes              | 每页显示个数选择器的选项设置                                 | Number[]                                                | -                                                            | [10, 20, 30, 40, 50, 100]                                  |
| popper-class            | 每页显示个数选择器的下拉框类名                               | String                                                  | -                                                            | -                                                          |
| prev-text               | 替代图标显示的上一页文字                                     | String                                                  | -                                                            | -                                                          |
| next-text               | 替代图标显示的下一页文字                                     | String                                                  | -                                                            | -                                                          |
| disabled                | 是否禁用                                                     | Boolean                                                 | -                                                            | false                                                      |



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

| 事件名                    | 说明                                                         | 参数                              |
| :------------------------ | :----------------------------------------------------------- | :-------------------------------- |
| select                    | 当用户手动勾选数据行的 Checkbox 时触发的事件                 | selection, row                    |
| select-all                | 当用户手动勾选全选 Checkbox 时触发的事件                     | selection                         |
| selection-change          | 当选择项发生变化时会触发该事件（如果没有指定rowKey，则参数selectedKeys的值为null） | selection, selectedKeys           |
| cell-mouse-enter          | 当单元格 hover 进入时会触发该事件                            | row, column, cell, event          |
| cell-mouse-leave          | 当单元格 hover 退出时会触发该事件                            | row, column, cell, event          |
| cell-click                | 当某个单元格被点击时会触发该事件                             | row, column, cell, event          |
| cell-dblclick             | 当某个单元格被双击击时会触发该事件                           | row, column, cell, event          |
| row-click                 | 当某一行被点击时会触发该事件                                 | row, column, event                |
| row-contextmenu           | 当某一行被鼠标右键点击时会触发该事件                         | row, column, event                |
| row-dblclick              | 当某一行被双击时会触发该事件                                 | row, column, event                |
| header-click              | 当某一列的表头被点击时会触发该事件                           | column, event                     |
| header-contextmenu        | 当某一列的表头被鼠标右键点击时触发该事件                     | column, event                     |
| sort-change               | 当表格的排序条件发生变化的时候会触发该事件                   | { column, prop, order }           |
| filter-change             | 当表格的筛选条件发生变化的时候会触发该事件，参数的值是一个对象，对象的 key 是 column 的 columnKey，对应的 value 为用户选择的筛选条件的数组。 | filters                           |
| table-current-change      | 当表格的当前行发生变化的时候会触发该事件，如果要高亮当前行，请打开表格的 highlight-current-row 属性 | currentRow, oldCurrentRow         |
| header-dragend            | 当拖动表头改变了列的宽度的时候会触发该事件                   | newWidth, oldWidth, column, event |
| expand-change             | 当用户对某一行展开或者关闭的时候会触发该事件                 | row, expandedRows                 |
| size-change               | pageSize 改变时会触发                                        | 每页条数                          |
| pagination-current-change | currentPage 改变时会触发                                     | 当前页                            |
| prev-click                | 用户点击上一页按钮改变当前页后触发                           | 当前页                            |
| next-click                | 用户点击下一页按钮改变当前页后触发                           | 当前页                            |



### Slot

| name       | 说明                                                         |
| :--------- | :----------------------------------------------------------- |
| -          | 表格列组件                                                   |
| append     | 插入至表格最后一行之后的内容，如果需要对表格的内容进行无限滚动操作，可能需要用到这个 slot。若表格有合计行，该 slot 会位于合计行之上。 |
| pagination | 分页组件自定义内容，需要在 `layout` 中列出 `slot`            |



### Methods

| 方法名             | 说明                                                         | 参数                        |
| :----------------- | :----------------------------------------------------------- | :-------------------------- |
| clearSelection     | 用于多选表格，清空用户的选择                                 | -                           |
| toggleRowSelection | 用于多选表格，切换某一行的选中状态，如果使用了第二个参数，则是设置这一行选中与否（selected 为 true 则选中） | row, selected               |
| toggleAllSelection | 用于多选表格，切换所有行的选中状态                           | -                           |
| toggleRowExpansion | 用于可展开表格，切换某一行的展开状态，如果使用了第二个参数，则是设置这一行展开与否（expanded 为 true 则展开） | row, expanded               |
| setCurrentRow      | 用于单选表格，设定某一行为选中行，如果调用时不加参数，则会取消目前高亮行的选中状态。 | row                         |
| clearSort          | 用于清空排序条件，数据会恢复成未排序的状态                   | -                           |
| clearFilter        | 不传入参数时用于清空所有过滤条件，数据会恢复成未过滤的状态，也可传入由columnKey组成的数组以清除指定列的过滤条件 | columnKey                   |
| doLayout           | 对 Table 进行重新布局。当 Table 或其祖先元素由隐藏切换为显示时，可能需要调用此方法 | -                           |
| sort               | 手动对 Table 进行排序。参数`prop`属性指定排序列，`order`指定排序顺序。 | prop: string, order: string |


