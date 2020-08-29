## Select 选择器

当选项过多时，使用下拉菜单展示并选择内容。



### Attributes

| 参数                  | 说明                                                         | 类型                      | 可选值            | 默认值     |
| :-------------------- | :----------------------------------------------------------- | :------------------------ | :---------------- | :--------- |
| value / v-model       | 绑定值                                                       | Boolean / String / Number | -                 | -          |
| data-source           | 所有选项数据组成的数组                                       | Array                     | -                 | -          |
| props                 | dataSource数据源键名配置，具体元素对象看下表                 | Object                    | -                 | {}         |
| multiple              | 是否多选                                                     | Boolean                   | -                 | false      |
| disabled              | 是否禁用                                                     | Boolean                   | -                 | false      |
| value-key             | 作为 value 唯一标识的键名，绑定值为对象类型时必填            | String                    | -                 | value      |
| size                  | 输入框尺寸                                                   | String                    | medium/small/mini | -          |
| clearable             | 是否可以清空选项                                             | Boolean                   | -                 | false      |
| collapse-tags         | 多选时是否将选中值按文字的形式展示                           | Boolean                   | -                 | false      |
| multiple-limit        | 多选时用户最多可以选择的项目数，为 0 则不限制                | Number                    | -                 | 0          |
| name                  | select input 的 name 属性                                    | String                    | -                 | -          |
| autocomplete          | select input 的 autocomplete 属性                            | String                    | -                 | off        |
| placeholder           | 占位符                                                       | String                    | -                 | 请选择     |
| filterable            | 是否可搜索                                                   | Boolean                   | -                 | false      |
| allow-create          | 是否允许用户创建新条目，需配合 `filterable` 使用             | Boolean                   | -                 | false      |
| filter-method         | 自定义搜索方法                                               | Function                  | -                 | -          |
| remote                | 是否为远程搜索                                               | Boolean                   | -                 | false      |
| remote-method         | 远程搜索方法                                                 | Function                  | -                 | -          |
| loading               | 是否正在从远程获取数据                                       | Boolean                   | -                 | false      |
| loading-text          | 远程加载时显示的文字                                         | String                    | -                 | 加载中     |
| no-match-text         | 搜索条件无匹配时显示的文字，也可以使用`slot="empty"`设置     | String                    | -                 | 无匹配数据 |
| no-data-text          | 选项为空时显示的文字，也可以使用`slot="empty"`设置           | String                    | -                 | 无数据     |
| popper-class          | Select 下拉框的类名                                          | String                    | -                 | -          |
| reserve-keyword       | 多选且可搜索时，是否在选中一个选项后保留当前的搜索关键词     | Boolean                   | -                 | false      |
| default-first-option  | 在输入框按下回车，选择第一个匹配项。需配合 `filterable` 或 `remote` 使用 | Boolean                   | -                 | false      |
| popper-append-to-body | 是否将弹出框插入至 body 元素。在弹出框的定位出现问题时，可将该属性设置为 false | Boolean                   | -                 | true       |
| automatic-dropdown    | 对于不可搜索的 Select，是否在输入框获得焦点后自动弹出选项菜单 | Boolean                   | -                 | false      |

#### Props

>  如果没有options属性，则元素位普通的选项；否则元素为一个组，其子选项通过options设置。

| 参数     | 说明                                                         | 类型                      | 可选值 | 默认值 |
| -------- | ------------------------------------------------------------ | ------------------------- | ------ | ------ |
| label    | 有options：分组的组名；无options：选项的标签，若不设置则默认与 `value` 相同 | String / Number           | -      | -      |
| value    | 有options：无效；无options：选项的值                         | String / Number / Boolean | -      | -      |
| disabled | 有options：是否将该分组下所有选项置为禁用；无options：是否禁用该选项 | Boolean                   | -      | false  |
| options  | 分组子选项数组，具体元素对象看下表                           | Array                     | -      | -      |

#### Options

| 参数     | 说明                                      | 类型                      | 可选值 | 默认值 |
| :------- | :---------------------------------------- | :------------------------ | :----- | :----- |
| label    | 选项的标签，若不设置则默认与 `value` 相同 | String / Number           | -      | -      |
| value    | 选项的值                                  | String / Number / Boolean | -      | -      |
| disabled | 是否禁用该选项                            | Boolean                   | -      | false  |



### Events

| 事件名称       | 说明                                     | 回调参数                      |
| :------------- | :--------------------------------------- | :---------------------------- |
| change         | 选中值发生变化时触发                     | 目前的选中值                  |
| visible-change | 下拉框出现/隐藏时触发                    | 出现则为 true，隐藏则为 false |
| remove-tag     | 多选模式下移除tag时触发                  | 移除的tag值                   |
| clear          | 可清空的单选模式下用户点击清空按钮时触发 | -                             |
| blur           | 当 input 失去焦点时触发                  | (event: Event)                |
| focus          | 当 input 获得焦点时触发                  | (event: Event)                |



### Slots

| name   | 说明                |
| :----- | :------------------ |
| prefix | Select 组件头部内容 |



### Methods

| 方法名 | 说明                            | 参数 |
| :----- | :------------------------------ | :--- |
| focus  | 使 input 获取焦点               | -    |
| blur   | 使 input 失去焦点，并隐藏下拉框 | -    |