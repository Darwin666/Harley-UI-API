## CheckboxGroup 多选框组

在一组备选项中进行多选。



### Attributes

| 参数            | 说明                                                         | 类型    | 可选值                | 默认值  |
| :-------------- | :----------------------------------------------------------- | :------ | :-------------------- | :------ |
| value / v-model | 绑定值                                                       | Array   | -                     | []      |
| data-source     | 所有选项数据组成的数组，具体元素对象看下表                   | Array   | -                     | -       |
| props           | dataSource数据源键名配置                                     | Object  | -                     | {}      |
| type            | 显示类型                                                     | String  | normal / button       | normal  |
| disabled        | 是否禁用状态                                                 | Boolean | -                     | false   |
| size            | 多选框组尺寸，仅对按钮形式的 Checkbox 或带有边框的 Checkbox 有效 | String  | medium / small / mini | -       |
| border          | 是否显示边框                                                 | Boolean | -                     | false   |
| fill            | 按钮形式的 Checkbox 激活时的填充色和边框色                   | String  | -                     | #409EFF |
| text-color      | 按钮形式的 Checkbox 激活时的文本颜色                         | String  | -                     | #ffffff |
| vertical        | 是否垂直展示                                                 | Boolean | -                     | false   |
| max             | 可被勾选的 checkbox 的最大数量                               | Number  | -                     | -       |
| min             | 可被勾选的 checkbox 的最小数量                               | Number  | -                     | -       |
| twoStage        | 是否有两级（搜索条件组件中使用）                             | Boolean | -                     | false   |

#### dataSource

| 参数          | 说明                                                 | 类型                      | 可选值                | 默认值 |
| ------------- | ---------------------------------------------------- | ------------------------- | --------------------- | ------ |
| label         | 标签名                                               | String / Number           | -                     | -      |
| value         | 选项的值                                             | String / Number / Boolean | -                     | -      |
| disabled      | 是否禁用状态                                         | Boolean                   | -                     | false  |
| border        | 是否显示边框                                         | Boolean                   | -                     | false  |
| size          | Checkbox 的尺寸，仅在 border 为真时有效              | String                    | medium / small / mini | -      |
| name          | 原生 name 属性                                       | String                    | -                     | -      |
| trueLabel     | 选中时的标签名                                       | String / Number           | -                     | -      |
| falseLabel    | 没有选中时的标签名                                   | String / Number           | -                     | -      |
| checked       | 当前是否勾选                                         | Boolean                   | -                     | false  |
| indeterminate | 设置 indeterminate 状态，只负责样式控制              | Boolean                   | -                     | false  |
| children      | 当twoStage为true时，此属性为第二级多选框的dataSource | Array                     | -                     | []     |



### Events

| 事件名称 | 说明                     | 回调参数   |
| :------- | :----------------------- | :--------- |
| change   | 当绑定值变化时触发的事件 | 更新后的值 |