### TypeScript 声明文件

TypeScript 作为 JavaScript 的超集，在开发过程中不可避免要引用其他第三方的 JavaScript 的库。虽然通过直接引用可以调用库的类和方法，但是却无法使用TypeScript 诸如类型检查等特性功能。为了解决这个问题，需要将这些库里的函数和方法体去掉后只保留导出类型声明，而产生了一个描述 JavaScript 库和模块信息的声明文件。通过引用这个声明文件，就可以借用 TypeScript 的各种特性来使用库文件了。

```ts
jQuery('#foo');  // index.ts(1,1): error TS2304: Cannot find name 'jQuery'.
declare var jQuery: (selector: string) => any;
jQuery('#foo');
```

```ts
// 声明文件以.d.ts位后缀
runoob.d.ts
// 声明文件或模块的语法格式如下
declare module Module_Name {
	...
}
// 引入声明文件语法格式
/// <reference path = " runoob.d.ts" />
```

