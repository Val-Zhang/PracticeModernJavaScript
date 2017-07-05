# ECMAScript 和 JavaScript的未来

谁也想不到，1995年被当做营销策略推出的JavaScript语言，在2017年成为了最受欢迎平台（web）上的核心语言。现在的JavaScript不仅是可以在浏览器中运行的脚本语言，它还被用作开发桌面和手机应用，嵌入式设备甚至NASA拿它来设计太空组件。

JavaScript语言取得的成绩有目共睹，其变化日异月殊，我们不禁好奇，这些成绩是怎么来的，未来JavaScript又该向何处发展？


## JS标准制定简史

1995年，那时候的浏览器还只支持html和简单的css,当时的浏览器巨头--网景公司，设想在浏览器中实现超越HTML的动态网站，Brendan Eich 因此被招进网景来开发一种供浏览器使用的类似`Scheme`的函数式语言。他加入后发现，网景公司高层希望这门语言看起来像Java（存在暗中进行的交易）。

只花了10天时间 Brendan 就开发完成了初版 JavaScript 的原型，被称作`Mocha`，这个新语言类似 `Scheme` 把函数当做一等公民，并以原型链为其核心。那时候JS还没有数组和字面量的对象的概念，所有的报错都只能通过丑陋的`alert`展示，也缺乏异常处理机制，导致出错时很多运算的结果是`NaN`或`undefined`。不过 Brendan对DOM 0的描述及初版的JavaScript还是成为了最初的标准。

1995年9月，网景公司发布了Netscape Navigator 2.0 beta版，JavaScript也被包装为`LiveScript`一同面世。1995年12月，Netscape Navigator 2.0 beta3发布，`LiveScript`在这时被改名为`JavaScript`(当时这个商标为Sun公司所有，现在属甲骨文公司)。之后不久,网景推出了`LiveWire`，一种在其服务器（`Netscape Enterprise Server`）上的`JavaScript`实现<sup>[1](#cite1)</sup>。

1996年，微软推出了`JScript`，同ie3捆绑发行,`JScript`在微软的IIS服务器上同样可用。

1996年开始,JS语言开始走上规范之路，它已`ECMAScript`的名字被标准化到**ECMA-262**规范，规范指定者是**ECMA**组织下的一个名为**TC39**的技术委员会。由于当时Sun公司不愿意转让`JavaScript`这一商标，微软虽然愿意转让`JScript`这一商标,但却遭到其它成员公司的反对，因此这一语言的名字就成了我们熟悉的`ECMAScript`。

尽管`JavaScript`和`JScript`是竞争关系，网易和微软在当时的**TC39**标准委员会占主导地位，委员会还是取得了大量的成果，**向后兼容**被设定为黄金法则，比如说虽然有了新的严格相等运算符`===`，但是同时兼容了非严格相等运算符`==`。

1997年6月**ECMA-262**的第一版发布，之后一年中，规范依据**ISO / IEC 16262国际标准**进行了改进，并由ISO认证机构大量审查，1997年6月`ECMAScript`规范正式发布第二版。

1999年12月，第三版也发布了，这一版的规范带来了**正则表达式**，`switch`，`do/while`,`try/catch`，`Object#hasOwnProperty`以及其它的一些改变，这些新的改变大部分也都在网景的新版浏览器**SpiderMonkey**中得以实现。

ES4标准的草案很快就被`TC39`提出，其早期工作直接影响了2000年中期的`JScript`,`.NET`，以及2006年Flash推出了`ActionScript 3`。

但是关于`JavaScript`语言该如何发展，当时的意见非常矛盾，这使规范工作停滞不前。这是Web标准指定史上的一个非常尴尬奇妙的时刻，当时微软掌握着网络的主动权，但是它对规范的改进却没太大的兴趣。

两年后，随着火狐浏览器市场占有率不断增高，就职于Mozilla的Brendan的迫使微软回到标准指定的议程中。2005年中期开始，TC39委员会又开始了例会。开始讨论起**ES4**，委员会有成员计划在`ES4`中引入**模块系统**，**类**，**迭代器**，**生成器**，**解构**，**类型注释**，**适当的尾调用**，**新的数据类型**和各种其他功能,由于这个工程的野心太大，**ES4**制定因而被一而再的延期。

2007年，**TC39**委员会被迫分为两部分，一部分负责**ES3**的渐进加强版`ES3.1`标准的制定，以及另一部分负责重新设计改动巨大的**ES4**标准。2008年8月，**ES3.1**被认为是正确的选择，随后其更名为**ES5**，**ES4**也随之被废弃，不过ES4提出的很多新功能被融入了**ES6**，另外的一些功能则仍然在考虑之中，有一些则已被放弃，拒绝或撤回。兼容**ES3.1**成为**ES4**标准提出的功能可以被通过的前提。

2009年12月，ES3发布10周年，第五版`ECMAScript`才得以发布。这个版本把十年来各浏览器中的普遍实践标准化了，添加了`get``set`，改进了数组原型的函数式特征，原生支持了JSON的解析，提出了严格模式。

2011年6月，ES5标准再次修改并改进为 **ISO/IEC 16262:2011标准**的第三版，并以**ES5.1**的名义正式发布。

四年后的2015年6月，TC39公布了JS语言有史以来最大的更新ES6，其中包含了很多ES4中提出草案。本书，我们将深入探索ES6。

在ES6的标准提出的同时，2012年，**WHATWG**（一个意在推动网络发展的标准机构）开始记录ES5.1和浏览器实现之间的差异性。该工作组标准化了`String＃substr`，并统一了之前在不同浏览器中HTML标签中使用字符串的不一致方法，记录了`Object.prototype`属性（如`__proto__`和`__defineGetter__`），并结合其它一些方面，这些改进也被列入web ES标准，并记录在ES2015的附录B中，不过附录B中的规范，浏览器的实现不需严格遵循其建议。

第六版是JavaScript历史上的一个重要里程碑。除了数十种新功能，ES6的发布也标志着ECMAScript将定期更新。

## 不断演化的ECMAScript标准

ES3发布了十年都没有重大变化，而后的ES6花了四年才得以标准化，TC39的效率确实需要改进了。效率低的原因是因为，之前标准的修订过程是由期限驱动的，但是只要未达成共识就会导致修订时间的延长，这期间可能有些功能又有了新的变化，这导致更多的延迟。

不过随着ES6标准的指定，TC39的工作流程也流线化了。他们优化了规则的制定过程使得其能满足现代更新持续且频繁的需求，规范的的制定也更加民主化了，为此，TC39从一个古老的基于Word的流程转移到了使用`Ecmarkup`（用于格式化ECMAScript规范的HTML超集）和`Github request`,这大大增加了提案数量以及非会员参与度，新的流程是连续且更透明的，以往你需要从网上下载某个规范的word或pdf说明文稿，现在你随时可以通过[这个网站](https://mjavascript.com/out/spec-draft)看见最新的草案。

现在Firefox，Chrome，Edge，Safari和Node.js都实现了ES6规范中超过95％的标准了，但是我们并不需要等到规范百分百的被支持再使用新语法。

任何尚未提交为正式提案的讨论，想法，改变或补充的建议都被认为是一个草案（所谓的stage0），但只有TC39成员可以提出草案。本文成文时，已有十几个积极的草案了。

标准的stage1，草案升级为正式化的提案，并将逐步解决多部门关切的问题，即与其他提案的相互影响以及该如何实施的问题。在这个阶段的提案会被提出一些问题，并需要为这些问题提供具体的解决方案，stage1的提案通常包括高级API描述，说明性使用示例，内部语义和算法的讨论，通常第一阶段的提案在这个过程中可能会发生重大变化。

stage2的提案就有了初始的草案规范。这个阶段的规范，也将开始在实际环境中运行，通过`polyfill`，用户可以提提案的形式使用了，一些浏览器引擎也会逐步对这一阶段的规范的提供本地支持，通过使用构建工具来转换源代码，编译成现有引擎可以执行的代码也可以使这一阶段的语法得以运行。

state3的规范就属于候选推荐代码了，要达到这一规范，规范编辑和指定审阅者必须在最终规范上签字，用户也应该对该提议感兴趣，而且该提案还必须至少被一个浏览器实现，拥有有高效的`ployfill`，或者被Babel支持，stage3的提议可能变化就不会那么大了。

想要达到stage4阶段，就必须有两个独立的通过验收测试的该草案的实现，进入第4阶段的提案就将包含在ECMAScript的下一个修订版中了。

ES6开始，每年都会发布新的规范，也因此新的规范将包含年号，如ES6又称ES2015，今年通过的规范将叫ES2017而非ES7，以此类推。不过ES6，称之为ES2015的还是比较少，大家还是习惯喊ES6，ES2016在命名规则变更之前已经公布，因此有时仍被称为ES7，不过按照这一命名规则，我们之后会说ES6，ES2016，ES2017，ES2018等等。

精简提案流程和每年发布的新版本使得新版的发布得以持续化，不过这也意味着版本号不再那么重要了，这也使得现在大家都把精力放在提案上，对参考ECMAScript标准的期待反而变少了。

## 浏览器支持情况和兼容工具

只要JavaScript引擎中提供了两个独立的实现，第3阶段的候选推荐方案就非常有可能在下一步中就被纳入规范了。实际上，第三阶段的提案一般被认为通过可以通过实验阶段的浏览器解析，`ployfill`或者编译器解析后，在生产环节中安全的使用。Stage2的提案以及更早的提案也被有些开发者运用到生产中，这使得社区对规范能有更多的反馈。

类似Babel这样，以代码作为输入，以浏览器可识别的HTML，CSS，JS的作为输出的工具被称为编译器，或者转义器（编译器的子集），当我们想在我们的代码中写还不是正式标准的语法时，Babel这类编译器就会把这些尚不被支持的语法转换为目前被浏览器广泛支持的语法。

转换一般发生在开发阶段。这使得浏览器更早的‘支持了’新的规范，让JS开发者更早享受到了新规范带来的好处。这对规范的作者和实践者也是大有裨益的，他们因此收集到了更多关于可行性、可取性，可能的错误或边缘案例的反馈。

通过转义器会把我们写的ES6代码转换为浏览器可识别的ES5代码，这是现今在生产环境使用ES6语法的最值得信赖的方案，只需要一个`build`步骤,我们的新代码就可以被老的浏览器（更不用说新浏览器）成功解析了。

这种方法同样被运用到ES7以及更新的标准中，随着新的标准每年的推出，我们可以预见编译器会马上支持ES2017，ES2018等等。与此同时，随着浏览器对新标准的支持度越来越高，编译器也会逐步减少对ES6代码的转译，ES7的转译等等。从这个角度看来，转译器起到了连接新旧的作用。

下面我们谈谈在你的工作流中该如何使用`Babel`。


## Babel转译器简介
Babel可以转义ES6代码为ES5代码，经转义的代码是易读的，这在我们对新特性还未牢牢掌握时非常有用。

在线的[Babel REPL (Read-Evaluate-Print Loop）](https://babeljs.io/repl/)为我们学习ES6提供了很好的途径，它不需要我们安装Node.js,也不需要使用`Babel` CLI就可以手动的转译源代码。

Babel REPL可以让我们输入源代码并在运行时自动编译，在右侧就可以看到编译后的代码。

我们一起来试试REPL，我们以下述代码开始：

```js
var double = value => value * 2
console.log(double(3))
// <- 6
```

在右侧我们可以看到编译为ES5的结果，如下图所示，当你更新左侧代码时，右侧也会实时更新
![图1 online Babel REPL](https://ponyfoo.com/books/practical-modern-javascript/img/pmjs_0101.png)

在练习本书提到的ES6特性时，Babel REPL是个很好的实践处，不过需要注意的是，Babel不能转译新增的类似`Symbol`,`Proxy`,`WeakMap`等内置指令，这些新特性并非被忽略了，其是否转译取决了运行时是否提供了Babel相关插件，如果我们想在运行时使用这些还未被执行的内置方法，我们需要在我们的代码中引入`babel-ployfill`.

在老版本的JS中，想要正确执行这些新语句是很难的或者几乎是不可完成的。polyfills可以减缓这种问题，但是通常它们并不能百分百覆盖所有情况，实际上它只是一种折中处理。因此如果要在生成环境中使用这些新内置语法，就算通过ployfill转译了，我们也应该在正式上线前仔细测试。

因此，对于这些无法解析的内置语法，我们最好还是等浏览器完全支持以后再使用。不过我们还是应该学习这些新特性，使得自己对JS语言有更深刻的理解。

诸如Chrome，Firefox，Edge等现代浏览器现在已经支持ES2015甚至更新的语法的大部分功能了，这使得我们在使用某个新语法时，浏览器的开发者工具非常有用。但是当涉及到基于新特性的生产阶段的应用时，我们还是推荐给你的代码添加转译，这能让代码的适用性更广。

除了REPL，我们还可以在命令行中实现转译，这需要用到Babel提供的一个node.js包，你可以通过`npm`的形式安装这个包。

我们新建一个node.js项目用做练习，新建目录，打开目录所在位置的终端，并通过`npm`CLI就可以实现这个目录的初始化；

```js
mkdir babel-setup
cd babel-setup
npm init --yes # yes参数使得初始化时采用默认设置
```

接下来我们创建一个名为`example.js`的文件，在babel-setup目录下新建子目录 src,并把这个文件保存其中，添加下述内容

```js
var double = value => value * 2
console.log(double(3))
// <- 6
```

在你喜欢的终端工具中输入以下内容就可以完成Babel的安装：

```js
npm install babel-cli​@6 --save-dev
npm install babel-preset-env@6 --save-dev
```

> 注：通过`npm`指令初始化的node项目，会自动在根目录新建一个名为node_modules的文件夹，之后我们通过`npm scripts`或通过`require`语句就可以在项目中引用这些包

> 使用`--save-dev`参数将会新安装的包添加到我们的package.json配置文件中作为开发依赖项，当我们把我们的项目复制到新的环境中时，我们只需要通过`npm install`指令完成依赖环境的安装。
> 
> `@`标记用以指定安装某特定版本的包，使用`@6`，`npm`将安装`babel-cli`,`6.x`版中的最新版。这种偏好设置可以非常有效的在未来保护我们的应用，永远不会安装`7.0.0`或者更新的版本，这些新版本可能包含我们在此时开发时无法预料的重大改变。
> 


接下来，我们要按照下面的方法替换`package.json`文件中的`scripts`，由`babel-cli`提供的`babel`命令会检测整个`src`目录，把他们转换为我们想要的输出格式，并存储在目录`dist`中，这将防止原来根目录下的源文件目录受到影响。

```js
{
  "scripts": {
    "build": "babel src --out-dir dist"
  }
}
```

通过上面的操作，现在我们的`package.json`应该是下面这个样子了

```js
{
  "scripts": {
    "build": "babel src --out-dir dist"
  },
  "devDependencies": {
    "babel-cli": "^6.24.0",
    "babel-preset-env": "^1.2.1"
  }
}
```

> 任何写作`scripts`对象中的命令都可以通过`npm run <name>`来执行，它会暂时修改`$PATH`的值，这使得我们在未全局安装`babel-cli`的前提下也可以成功运行`babel-cli`
> 


现在如果你在命令行中执行`npm run build`，你会发现系统自动新建了`dist/example.js`文件，输出文件目前会和我们的源代码一致，这是因为`babel`并不会自动给我们添加配置文件，我们需要在根目录创建文件`.babelrc`输入下述代码进行配置

```js
{
  "presets": ["env"]
}
```

我们现在安装的`env`preset,会在构建时添加一系列的Babel插件，这些插件可以转换不同的ES6代码为ES5代码，此时我们会看到我们在`example.js`中使用的箭头函数被转换为了ES5代码，`env` 预设依照协议，使得Babel依据最新的浏览器支持情况转换JS代码，这个预设是可以配置的，这意味着我们可以决定支持多新的浏览器。我们想要支持的浏览器越多，我们需要做的转换工作就越大，所做的转换工作越少，意味着可正常使用的用户也越少。我们需要通过调研来确定`env`预设的正确配置，默认情况下所有的转换都会被启用，以提供尽可能广泛的支持。

我们执行转义后，转译后的ES5代码如下：

```js
» npm run build
» cat dist/example.js
"use strict"

var double = function double(value) {
  return value * 2
}
console.log(double(3))
// <- 6

```


下面我们来说明如果使用另外一个非常有用的工具，`eslint`，它可以依据某个基线帮助我们改善代码质量。


## 使用ESLint改善我们的代码质量并保证一致性

随着我们的代码量越来越多，我们会面临很多问题，一些代码是多余的并不再那么有用，写新的代码，删除一些不再相关或必须的特性，运用新架构而相应的调整代码位置。随着代码量增多，团队人员也会相应变化，期初可能只有少数人甚至一个人，但是随着项目的扩大，开发人员也随值增多。

lint工具可以用于识别语法错误，现代的lint工具常常是可自定义的，这能帮助构建一种对团队里每个人都适用的编码风格。通过标准化样式规则和质量基线，我们能让团队在编码风格保持一致。团队中的每个人可能对编码风格都有自己的看法，但是当我们以合适的配置适用linter工具，它们的意见可以被抽象为编码样式规则。

除了确保程序可被解析外，我们可能还希望防止`throw`语句抛出异常语句，或者在生产代码中不允许出现`console.log`和`debugger`语句。但是，要求每个函数执行时都至少含有一个参数的规则也许过于苛刻。

尽管linter在定义和实行编码风格方面是有效的，但是我们也应该小心定义风格，如果规则过于严格，开发人员可能会沮丧到影响开发效率，如果过于宽松，可能又难以维持代码的一致性。

ESlink是一个具有很多插件的现代linter工具，它支持众多规则，并允许我们挑选需要的规则去遵守。我们可以决定在没有准守这些规则时会在输出中打印出警告语句或者错误。我们可以使用`npm` 用类似安装`babel`的方法安装`eslint`，使用`npm`

```js
npm install eslint@3 --save-dev
```

接下来，我们需要配置ESlint,由于我们把eslint安装为了本地依赖，我们可以在`node_modules/.bin`文件夹下找到对应的命令行工具。执行下面的命令行命令将引导我们完成对项目的首次配置。我们选用`standard`已采用流行风格，选择配置文件为`JSON`格式:

```bash
./node_modules/.bin/eslint --init
? How would you like to configure ESLint?
  Use a popular style guide
? Which style guide do you want to follow? Standard
? What format do you want your config file to be in? JSON
```

除了个人风格，`eslint`允许我们拓展预定义的风格，这些拓展都以node.js的包呈现。当你在多项目甚至社区中分享配置时这非常有用。在选择`standard`风格之后，我们还注意到`ESlint`添加了一些依赖到`package.json`中，即预定义标准风格的包，同时创建了一个名为`.eslintrc.json`的配置文件，如下所示：

```js
{
  "extends": "standard",
  "plugins": [
    "standard",
    "promise"
  ]
}
```

从`node_modules/bin`目录中引入npm命令，这样用起来感觉很不好，当我们初始化我们的`ESlint`配置文件时就是这样用的，我们总不能之后每次都带上`node_modules/bin`吧，这样太麻烦了。为了解决这个问题，我们把`lint`命令也添加到`package.json`中：

```js
{
  "scripts": {
    "lint": "eslint ."
  }
}
```

也许你还记得，`npm run`会临时把`node_modules`名录添加到`$PATH`中。现在当我想lint我们的代码时，我们只需要输入`npm run lint`，npm就会自动执行深藏在`node_modules`中的ESLint CLI命令了

还是以`example.js`文件为例，这个文件目前可能存在一些样式问题，我们来看看`ESLint`会为我们做什么：

```js
// expamle.js
var goodbye='Goodbye!'

function hello(){
  return goodbye}

if(false){}
```

当我们执行`lint`脚本，ESlint会列出这个文件中的所有问题，如下：

![ESLint 错误示例](https://ponyfoo.com/books/practical-modern-javascript/img/pmjs_0102.png)

如果我们在执行上述命令的时候 添加参数 `--fix`，eslint会为我们修复大部分的问题，我们修改`package.json`如下

```js
{
  "scripts": {
    "lint-fix": "eslint . --fix"
  }
}
```

当我们执行 `lint --fix`的时候，我们会发现现在的错误只是说 `hello` 从未使用过，`false`是一个不变的状态，其它的问题都被修复了，修复后的代码如下，由于ESLint不对我们的代码做假设，出问题的代码没有被修复，ESlint 也不想造成语义变化，基于此，`--fix`的参数是我们解决代码风格问题时的有效帮手，并且它不会搅乱我买额程序。

```js
// 修改后的example.js
var goodbye = 'Goodbye!'

function hello() {
  return goodbye
}

if (false) {}
```

> `prettier`是另一个类似的工具，它会自动规范化我们的代码，当给定一些固定的规则，比如所讲的空格数，单引号还是双引号，尾逗号，以及一行最大长度时，`prettier`会实现我们的代码的自动重写。
> 

现在你已经知道了如何转译现代的JS为浏览器普遍支持的JS了，也知道如何合适的使用lint来规范代码，下面我们来学习ES6特性以及JS的未来。


## ES6中的新特性

ES6改动非常大，要知道ES5.1的规范一共才258页，ES6的规范达到了566页，规范的改变属于都属于一些不同的类别：

- 语法糖
- 新机制
- 更好的语义化
- 更多内置的方法
- 现存局限的非破坏性解决方案


语法糖是ES6所有改变中最重要的一块，通过`class`语法可简洁的构建对象实例，支持使用箭头函数，属性方法支持简写了，我们还将探讨一些别的特性，如果解构，剩余值，和拓展，ES6还提供语义良好的编写程序的方法。第二章 ES6 Essentials and Classes, Symbols, Objects, and Decorators将讨论ES6 的这些新特性。

ES6为我们提供了几种控制异步代码流的机制：`promises`,代表一种运算的最终结果，`iterators`，表示一系列值，`generators`是一种特殊的`iterators`,能够产生一系列值。在ES2017基于这些新概念还提出了`async/await`，让我们以同步的方式来书写异步代码。在[Iteration and Flow Control]()一节中，我们将详细叙述各种机制。

JavaScript中有一种常见的做法，即开发人员使用普通对象创建任意字符串键的哈希映射。但是如果我们不小心使用,让用户输入结束了这些键，就会导致错误，ES6提供了一些新的内置类型来管理set和map,这些新类型不具有仅使用字符串键的限制，关于这些方面的探讨，我们会在[Practical Considerations]()这一节中进行。

Proxy对象重新定义了我们通过JavaScript reflection可以做什么，Proxy对象类似于其它上下文中的代理（比如网络流量路由）。它们可以修改与JavaScript对象的任何交互，如定义、删除或访问属性。考虑到代理对象的工作机制，他们不能通过`ployfill`实现，事实上相关的`ployfill`也是存在的，但是由于它们的局限性使得他们在某些方面与规范有所不一致。我们将在[ Managing Property Access with Proxies]()这一节彻底理解代理对象。

除了这些新的内建语法，ES6对`Number`,`Math`,`Array`和`string`都有所更新。在[Build-in Improvement in ES6]()这一节，我们将通过大量的示例来解释这些新概念。

ES6还在语言层面上为我们提供了模块系统，在讲述`CommonJS`模块系统在node.js中的使用后，[JavaScript Modules]()一节里，我们将讲述JS的模块系统。

考虑到ES6的改动之大，我们很难用我们现有的JS知识理解所有的新特性，在[ Practical Considerations ]()一节我们会分析各ES6特性的优点和重要性，以便你可以对如何动手使用ES6有一个基础的概念。

## JS语言的未来

从1995年的卑微出生到今天的强大功能，JS变化巨大，ES6就是这变化过程中的一大步，当然这肯定不是终点，考虑到标准每年都会更新，学会如何和最新标准保持一致非常重要。

前面我们已经说明了，ES是一个滚动的标准，最好的学习新标准的方法是周期性的浏览TC39的建议库，尤其有注意处于候选阶段的stage3阶段的提议，这些很可能就是之后的标准。

在书中描述一个不断变化的语言是一个大的挑战，尤其是考虑到标准也是在不断演化的。与新的JavaScript更新保持一个有效的方法是看TC39建议库，订阅每周电子邮件，和阅读JavaScript的博客。

在写本书的时候，等待已久的`Async Functions `提议已经定于在ES2017中发布。同时还有一些处于候选阶段的提议，比如动态`import()`，这允许异步的加载本地JS模块，还有一个建议用ES6中的`rest`和 `spread`语法 对对象属性进行枚举。

尽管本书主体集中讨论ES6，我们也会学习一些重要的候选方案，如之前已经提及的`async functions`,`dynamic import()`，`calls`以及对象的 `rest/spread`和一些其它的属性。



1. A booklet from 1998 explains the intricacies of server-side JavaScript with LiveWire.

2. You can read the original announcement at the Microsoft website (July, 2000).

3. Listen to Brendan Eich in the JavaScript Jabber podcast, talking about the origin of JavaScript.

4. You can read a news report from The Mac Observer, July 2003.

5. Brendan Eich sent an email to the es-discuss mailing list in 2008 where he summarized the situation, almost 10 years after ES3 had been released.

6. For the full set of changes made when merging the Web ECMAScript specification upstream, see the WHATWG blog.

7. Check out the presentation “Post-ES6 Spec Process” from September 2013 that led to the streamlined proposal revisioning process here.

8. Check out all of the proposals being considered by TC39.

9. Check out this detailed table reporting ES6 compatibility across browsers.

10. Take a look at the TC39 proposal process documentation.

11. You can track strawman proposals.

12. Note that Standard is just a self-proclamation, and not actually standardized in any official capacity. It doesn’t really matter which style guide you follow as long as you follow it consistently. Consistency helps reduce confusion while reading a project’s codebase. The Airbnb style guide is also fairly popular and it doesn’t omit semicolons by default, unlike Standard.

13. Check out all of the proposals being considered by TC39.

14. There are many newsletters, including Pony Foo Weekly and JavaScript Weekly.

15. Many of the articles on Pony Foo and by Axel Rauschmayer focus on ECMAScript development.