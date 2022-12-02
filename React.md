### JSX语法规则：


* 变量等号右侧，不能加引号，直接写HTML;
* 标签中插入JS``表达式``时，利用花括号 { };
* class 应该写成 **className**;
* 内联样式写的时候 ``<span style = {{ fontSize: '20px', color : 'red' }} > </span>``, 外面的一个花括号表示，要引入JS, 内部花括号，表示引入的对象；
* ``const VDome = (  <div>   </div>  );``
* 只能有一个根标签
* < input  3764 /> ：标签必须闭合；
* 标签的首字母，如果是大写，则要代表 - component
* 内部不能添加js语句，只能放置 js 表达式；什么是表达式呢？拿着变量接，要能接到

---

### 模块与组件

如何定义组件呢？
* 函数式组件
* 类似的组件

函数式组件：

`` function Mycomp () {
  return (
    
    <div>
    </div>
  
  )
}``





