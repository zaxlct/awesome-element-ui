# awesome-element-ui
收集了基于 element-ui 的插件，第三方库，脚手架等，大大加速你的开发速度~

## 表单
#### [element-china-area-data](https://github.com/Plortinus/element-china-area-data)
> Element UI Cascader级联选择器 中国省市区三级、二级联动option数据

不用多说，如果你的项目里需要「选择省市区」，直接 npm install 就能用！

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

