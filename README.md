# awesome-element-ui
收集了基于 element-ui 的插件，第三方库，脚手架等，大大加速你的开发速度~

## 表单
#### [element-china-area-data](https://github.com/Plortinus/element-china-area-data)
> Element UI Cascader级联选择器 中国省市区三级、二级联动option数据

不用多说，如果你的项目里需要「选择省市区」，直接 npm install 就能用！

#### [element-ui-verify](https://github.com/aweiu/element-ui-verify)
> 如果你受够了饿了么ElementUI原生的校验方式，那就来试试它吧！一款更懂你的校验插件

十分推荐，用指令代替了校验函数，可少写大量代码，解放了生产力~

#### [el-form-dialog](https://github.com/njleonzhang/el-form-dialog)
**为什么要用 el-form-dialog？**
1. confirm和cancel按钮<br/>
[element-ui](http://element.eleme.io/) 的 [dialog](http://element.eleme.io/#/zh-CN/component/dialog) 本身是不带按钮的, 需要通过slot去添加。这个设计本身没有问题，组件分离的很开。但是实际使用了缺带来了不便，主要是这里的2个按钮一般一个项目都是一样的，但是却要不断的写这段`slot = footer`代码，感觉很是烦躁。
    ```
    <el-dialog
      title="提示"
      :visible.sync="dialogVisible"
      width="30%"
      :before-close="handleClose">
      <span>这是一段信息</span>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
    ```
2. validate操作<br/>
就是和 [el-form](http://element.eleme.io/#/zh-CN/component/form) 一起用的时候，每次点击确定键的时候都要去对表单做validate, 每次点取消都要对validate的提示做清除, 这些代码也是要不断重复的。
3. 两种状态的dialog<br/>
一个典型的场景是我们一个页面，经常会需要新增和编辑一个数据，这是就需要添加和修改2个dialog。而这2个dialog一般来说是比较相似的，如果分别写一个dialog来处理，逻辑上自然是简单的，但是缺凭空多出很多重复代码来，运行时也多1倍的组件实例。但是如果把添加和修改dialog做成一个往往又需要处理组件的重用的逻辑复杂性，而这些处理大体上是十分相似的。
4. loading
当`confirm`按钮被点击的时候，多数情况下，我们会发起一个http请求去处理一些业务逻辑，这就会涉及到loading加载器的处理。

这个库对`el-dialog`和`el-form`做了一些封装处理以上问题，让大家可以轻松上阵，专注自己的业务逻辑。

> 编者注：如果你有以上的痛点，请一定要用 `el-form-dialog` ，不仅仅可以少写重复的代码，更大的好处是代码结构更加清晰易懂

## 表格
#### [egrid-element-table](https://github.com/zaxlct/egrid-element-table)
**为什么要用 egrid-element-table？**
1. 你是否受够了重复一遍又一遍的 `el-table-column` 和 `template scope="scope"`
```html
  <el-table
    :data="tableData"
    border
    style="width: 100%">
    <el-table-column
      label="日期"
      width="180"
      prop="time">
    </el-table-column>
    <el-table-column
      label="姓名"
      width="180"
      props="name"
    >
    </el-table-column>
    <el-table-column label="操作">
      <template scope="scope">
        <el-button
          size="small"
          @click="handleEdit(scope.$index, scope.row)">编辑</el-button>
        <el-button
          size="small"
          type="danger"
          @click="handleDelete(scope.$index, scope.row)">删除</el-button>
      </template>
    </el-table-column>
  </el-table>
```
2. 如何优雅的复用自定义列模板（`template scope="scope"`）？
3. 如何实现表格的继承？比如有一个基础的展示数据表格组件，如何实现引用该组件后再添加「修改、删除、关闭」等自定义操作列？

#### [vue-data-tables](https://github.com/njleonzhang/vue-data-tables)
> 一个基于 Vue 和 element-ui 支持SSR的, 简单易用的, 可定制的分页表格
- 使用便捷, 轻量
- 支持前台分页和后台分页
- 可定制, 灵活, 强大
- 支持 SSR (目前还在beta阶段）

如果你项目中的表格均需要分页、筛选、过滤等操作，请用它！

（`egrid-element-table` 和 `vue-data-tables` 能一起用，参考此 [issue](https://github.com/njleonzhang/vue-data-tables/issues/223)）

## 脚手架
#### [vue-admin-template](https://github.com/PanJiaChen/vue-admin-template)
后台管理系统必备脚手架，太出名，就不多说了~

#### [vue-element-admin](https://github.com/PanJiaChen/vue-element-admin)
后台管理系统必备脚手架，太出名，就不多说了~

## 其他
- 以上所有的库和脚手架均在两三个项目中正常使用过，经过了考验
- 欢迎发起 Pull Request
