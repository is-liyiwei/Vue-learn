首先看到定义了两个方法isHTMLTag和isSVG

其中isSVG方法还传入了第二个参数true

makeMap方法最后根据第二个参数返回一个是否要做小写转换的函数

举个栗子

makeMap('zhang','san','feng')

然后创建map一个空对象，list数组['zhang','san','feng']，遍历数组得到

map: {
  zhang: true
  san: true
  feng: true
}

最后返回一个函数function (val) { return map[val]; }，map则作为闭包变量保存下来

那么这个时候isHTMLTag就是function (val) { return map[val]; }，即

isHTMLTag = function (val) {
  return map[val];
}

调用isHTMLTag('feng') return map['feng']，自然是返回true了

那么isSVG亦是同理