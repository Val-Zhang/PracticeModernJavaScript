# ECMAScript 和 JavaScript的未来

谁也想不到，1995年被当做营销策略推出的JavaScript在2017年成为最受欢迎平台上的核心语言。JavaScript不仅是在浏览器中运行了，它同时被用作开发桌面和手机应用，嵌入式设备甚至被NASA拿来设计太空组件。



我们不禁要问，JavaScript是怎么取得今天的成就的，JavaScript未来又将朝哪里发展？



## JS标准简史

1995年，网景公司设想了一种超越HTML能力的动态网站，Brendan Eich被招进网景来开发一种供浏览器使用的类似Scheme的函数式语言。他加入时发现，公司高层希望这门语言看起来像Java，关于这种效果的交易也在暗中进行。



Brendan只花了10天就开发完成了第一版JavaScript的原型，这个新语言类似Scheme把函数当做一等公民，并以原型为其主要成分。最初的原型被称作Mocha，那时候它还没有数组和字面量的对象，所有的报错都通过`alert`展示，由于缺乏异常处理机制，也导致那时很多运算的结果是`NaN`或`undefined`。Brendan对DOM 0的描述及初版的JavaScript成为了最初的标准。



1995年九月，随着网景公司发布了beta版的Netscape Navigator 2.0，JavaScript被调整包装为LiveScript一同面试。1995年12月随着Netscape Navigator 2.0 beta3的发布，LiveScript又被改名为JavaScript(这个商标当时为Sun公司所有，现在归属甲骨文公司)。在这之后不久，网景在其自己的服务器（ Netscape Enterprise Server）上推出了名为LiveWire的服务器端的JavaScript执行<sup>[1](#cite1)</sup>。

1996年，微软推出了其JavaScript的反向设计实现-- JScript，并同ie3捆绑发行。JScript在微软的IIS服务器上同样可用。



JS语言在1996年开始已ECMAScript的名字被标准化到ECMA-262规范，规范者为ECMA组织下的一个名为TC39的技术委员会。当时Sun公司不愿意转让JavaScript这一商标，微软倒是愿意转让JScript这一商标但却遭到其它成员公司的反对，最终就叫ECMAScript了。



尽管是竞争关系，网景的JavaScript和微软的JScript还是在当时的TC39标准委员会占主导地位，尽管如此，委员会还是取得了大量的成果，向后兼容被设定为黄金法则，带来了严格相等运算符而没有破坏现有的依靠松散的平等比较算法的程序。



ECMA-262的第一版在1997年六月发布，一年后的1998年六月，该规范根据ISO / IEC 16262国际标准进行了改进，经过国家ISO认证机构的大量审查，正式发布为第二版。



1999年12月第三版发布了，规范了正则表达式，`switch`，`do/while`,`try/catch`和`Object#hasOwnProperty`，包括其它的一些改变，大部分新的改变都在网景的新版浏览器SpiderMonkey中得以实现。



ES4标准的草案很快也被TC39提出，ES4的早期工作直接影响了2000年中期的JScript .NET，以及2006年Flash推出了ActionScript 3。



关于JavaScript如何推进，当时的意见非常矛盾，这使规范工作停滞不前。这是Web标准的一个非常奇妙的时刻，这是微软掌握着网络的主动权，但是对规范的改进却没太大的兴趣。



直到两年后Brendan（现在在Mozilla），凭借获取火狐浏览器不断增长的份额迫使微软回到标准的议程中。2005年中期开始，TC39委员会又开始的例会。至于ES4，人们有计划引入模块系统，类，迭代器，生成器，解构，类型注释，适当的尾部调用，新的数据类型和各种其他功能。由于这个工程的野心太大，ES4被一而再的延期。



2007的委员会被分为两部分，ES3的渐进加强版ES3.1，以及重新设计改动巨大的ES4。到2008年8月，ES3.1被认为是正确的选择，之后被更名为ES5.尽管ES4被放弃了，它提出的很多新功能被融入了ES6，不过其它的一些功能仍然在考虑之中，有一些已被放弃，拒绝或撤回。ES3.1成为了ES4标准可以被通过的前提。



2009年12月，ES3发布10周年，第五版ECMAScript得以发布。这个版本把浏览器中的普遍实践标准化了，添加了`get``set`存取，改进了Array原型的函数式特征，在语言层面中支持了JSON的解析，以及严格模式。



几年后的2011年 6月，标准得以再次修改和改进成为 ISO/IEC 16262:2011标准的第三版，并以ES5.1正式发布。



又过了四年，在2015年6月，TC39公布了JS语言有史以来最大的更新ES6，其中包含了很多ES4中提出的被和谐的草案，本书，我们将深入探索ES6.



与ES6的标准提出的同时，在012年，WHATWG（一个意在推动网络发展的标准机构）开始记录ES5.1和浏览器实现之间的差异性，在兼容性和互操作性方面。该工作组标准化了以前未标准化的`String＃substr`。统一了几种之前浏览器中不一致的在HTML标签中包装字符串的方法，并记录了`Object.prototype`属性，如`__proto__`和`__defineGetter__`结合其它一些方面的改进，它们的努力得以浓缩为一个单独的web ES标准，并最终展现为ES2015的附录B中，附录B是核心ECMAScript规范的资料不符，意思是浏览器的实现不需要遵循其建议。与此更新一起，附件B也被制定为网络浏览器的规范和要求。



第六版是JavaScript历史上的一个重要里程碑。除了数十种新功能，ES6的发布是ECMAScript成为滚动标准的关键转折点。



## 作为滚动标准的ECMAScript























- [1] A [booklet from 1998](https://mjavascript.com/out/livewire) explains the intricacies of server-side JavaScript with LiveWire.