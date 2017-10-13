# 对本翻译的说明

本系列文章翻译自 Nicolas Bevacqua 的 《Practical Modern JavaScript》。

- 原书链接：[Practical Modern JavaScript](https://ponyfoo.com/books/practical-modern-javascript)
- Github链接：[practical-modern-javascript](https://github.com/mjavascript/practical-modern-javascript)

仔细的翻译是一个把学习放慢的过程，其实阅读原文只需要小半天时间，也可能可以 GET 到基础的知识点，想要翻译则不同，翻译会让人仔细的去想每一句话，这个过程常常就能有别的收获。

有时候我也会怀疑自己是否太注重工具的使用而忽略了语言的本质，虽然在项目中也在用ES6的语法，刚刚学会使用的时候也会有一些成就感，但是用多了也会开始怀疑为什么是这样，为什么要这样用。作为前端开发者，理因对这个语言有更深刻的理解，就像不断演化的JS语言一样，等翻译完本书，我的知识库肯定也能得到一个重大的更新。O(∩_∩)O哈哈~


## 对每章的翻译，我的收获

### [第一章 ECMAScript简史 和 JavaScript的未来](https://github.com/zhangwang1990/PracticeModernJavaScript/blob/master/docs/%E7%AC%AC1%E7%AB%A0.%20ECMAScript%20%E5%92%8C%20JavaScript%E7%9A%84%E6%9C%AA%E6%9D%A5.md)

- 温习了JS语言的发展简史；
- 了解了`stage0`,`stage1`,`stage2`,`stage3`,`stage4`各阶段的意义（以前使用babel时看见过类似的词，但是并不理解）；
- 知道了`ployfill`是局限性的新语法的实现，以前在开发微信应用时，也引入过，其实还真是一直不清楚，这到底是什么；
- 复习了`babel`，`eslint`的基本方法;
- 知道了ES6可以划分为：语法糖，新机制，更好的语义化，新api，现存局限方法的非破坏性解决方案几方面，这对构建系统的ES6知识大有裨益；


### [第二章 ES6 概要](https://github.com/zhangwang1990/PracticeModernJavaScript/blob/master/docs/%E7%AC%AC2%E7%AB%A0.%20ES6%20%E6%A6%82%E8%A6%81.md)
- 对象字面量的简写属性和计算的属性名不可同时使用，原因是简写属性是一种在编译阶段的就会生效的语法糖，而计算的属性名则在运行时才生效；
- 箭头函数本身已经很简洁，但是还可以进一步简写；
- 解构也许确实可以理解为变量声明的一种语法糖，当涉及到多层解构时，其使用非常灵活；
- 学会了模板字符串的高级用法--标记模板字符串；
- `let`,`const`声明的变量同样存在变量提升，理解了TDZ机制；

### [第三章 Classs,Symbols,Objects拓展 和 Decorators](https://github.com/zhangwang1990/PracticeModernJavaScript/blob/master/docs/%E7%AC%AC3%E7%AB%A0.%20Classes%2CSymbols%2CObjects%20%E5%92%8C%20Decorators.md)
- JS中，类实际上是一种基于原型链的语法糖；
- 重新理解了`getter`和`setter`;
- Symbol 分 `local Symbol`，`global Symbol`和语言内置Symbol；
- 装饰符目前处于Stage2，对类和类属性使用原理不同，不是很习惯原文对这一块的描述，译文中引用凹凸实验室的[Javascript 中的装饰器](https://aotu.io/notes/2016/10/24/decorator/index.html)；


## 备注
1. 本书的翻译并非严格逐句进行，或者说逐句翻译只是翻译的第一个阶段，而后会依据第一个阶段的翻译采用汉语的习惯意译。如果有任何意见，请不要犹豫，我们一起来修改；
2. 项目名称被误写成了Practice Modern JavaScript非Practical Modern JavaScript。。由于有之前的提交记录，在此就不先不改了；
3. 这本书在上半年就已经出来了，热心的中国开发者，可能也有进行翻译的，在此向你们致敬，你们肯定也大有收获；
4. 如果愿意，和我一起，我们一起来学习ES6吧，对书里面有疑问的任何地方，我们一起多讨论吧；

