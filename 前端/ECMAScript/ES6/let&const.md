* var 命令声明变量的缺陷：
    
    * 没有块级作用域
    * 变量允许重复声明 
    * 存在变量提升，允许在变量未声明完成前使用变量

* let & const 命令规定声明的变量：

    * 拥有块级作用域
    * 不允许重复声明
    * 不存在变量提升，let 命令声明的变量存在暂时性死区

* let

    let 声明的变量只在块级作用域中有效，每个代码块中都存在自己独立的作用域，即使不同层级的代码块中声明了同一个变量名，也都是相互不影响的，也就是外层代码块的作用域不受内层代码块的作用域的影响。

* const 

    const 命令声明的变量值是不允许修改的，也就是当做声明了一个常量来使用。声明的变量在初始化的时候必须赋值。
    但是有一点要注意，cosnt 命令本质是声明的变量并不是不允许修改值，而是不能修改指针指向的内存地址。对于一般的数据类型，变量的值指向的就是内存地址，所以修改值就等价于修改值的指针指向内存地址。对于复杂的数据类型，如对象和数组而言，可以修改内部的数据结构而不影响数据本身的内存地址。
    ```javascript
    const obj = {};
    obj.name = '白展堂';
    obj.sex = '男';
    ```
    ES5 中，顶层对象等价于 window 对象，全局变量就是顶层对象的属性，也就是 window 对象的属性。在 ES6 中规定了，let 和 const 命令定义的全局变量不再是顶层对象的属性，为了兼容，仍然保留 var 和 function 声明的全局变量可以作为顶层对象的属性。

    ```javascript
    let name = '白展堂';
    window.name; //undefined
    ```

* 参考

[https://zhuanlan.zhihu.com/p/28140450](https://zhuanlan.zhihu.com/p/28140450)    
