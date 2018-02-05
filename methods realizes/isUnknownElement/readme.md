开头创建了两个元素，然后像Vue一样做判断，重点主要在这里

```

const HTMLElement_dev = document.createElement('nav')
console.log(HTMLElement_dev.constructor)

// => function HTMLElement() { [native code] }

const HTMLUnknownElement_dev = document.createElement('unKnownNav')
console.log(HTMLUnknownElement_dev.constructor)

// => function HTMLUnknownElement() { [native code] }

```

创建一个nav元素，它的构造函数是HTMLElement，因为它html<span style="font-weight: bold;margin-bottom: 10px;color: #FF0000">是</span>原有的标签元素

创建一个unKnownNav元素，它的构造函数是HTMLUnknownElement，因为它<span style="font-weight: bold;margin-bottom: 10px;color: #FF0000">不是</span>html原有的标签元素

这里尤大佬也给出了链接，可以看下国外大神的高见[http://stackoverflow.com/a/28210364/1070244](http://stackoverflow.com/a/28210364/1070244)


回到主题

这里的isUnknownElement函数，名字意思大概就是：“是否是未知元素”
全局变量unknownElementCache这个对象就是保存未知元素的object了
所以这个方法就是检测传入用来创建元素的字符串是否为未知的html标签检测的功能