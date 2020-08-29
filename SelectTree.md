## SelectTree 下拉树

用清晰的层级结构展示选项的下拉框，可展开或折叠。



### Attributes

| 参数            | 说明                                       | 类型                      | 可选值        | 默认值 |
| :-------------- | :----------------------------------------- | :------------------------ | :------------ | :----- |
| value / v-model | 绑定值                                     | Boolean / String / Number | -             | -      |
| data-source     | 所有选项数据组成的数组，具体元素对象看下表 | Array                     | -             | -      |
| props           | dataSource数据源键名配置                   | Object                    | -             | {}     |
| multiple        | 是否多选                                   | Boolean                   | -             | false  |
| disabled        | 是否禁用                                   | Boolean                   | -             | false  |
| type            | 展示类型                                   | String                    | normal / text | normal |
| placeholder     | 占位符                                     | String                    | -             | 请选择 |
| width           | 组件宽度                                   | String                    | -             | -      |

#### Data Source

> 如果没有options属性，则元素位普通的选项；否则元素为一个组，其子选项通过options设置。

| 参数     | 说明                                      | 类型                          | 可选值 | 默认值 |
| -------- | ----------------------------------------- | ----------------------------- | ------ | ------ |
| label    | 选项的标签，若不设置则默认与 `value` 相同 | String / Function(data, node) | -      | -      |
| value    | 选项的值                                  | String / Number / Boolean     | -      | -      |
| disabled | 是否禁用该选项                            | Boolean/ Function(data, node) | -      | false  |
| children | 子节点对象列表                            | Array                         | -      | -      |
| isLeaf   | 是否是叶子节点                            | Boolean/ Function(data, node) | -      | -      |

#### 

### Events

| 事件名称       | 说明                                     | 回调参数                      |
| :------------- | :--------------------------------------- | :---------------------------- |
| change         | 选中值发生变化时触发                     | 目前的选中值                  |
| visible-change | 下拉框出现/隐藏时触发                    | 出现则为 true，隐藏则为 false |
| clear          | 可清空的单选模式下用户点击清空按钮时触发 | -                             |
| blur           | 当 input 失去焦点时触发                  | (event: Event)                |
| focus          | 当 input 获得焦点时触发                  | (event: Event)                |



### Slots

| name   | 说明                |
| :----- | :------------------ |
| prefix | Select 组件头部内容 |

