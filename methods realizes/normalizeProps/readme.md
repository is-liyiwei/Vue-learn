这里举了两个常用的props形式的例子

props: ['myPropData', 'myPropData-one', '_my-propsData-two'],

首先第一个是字符串数组，所以会走if (Array.isArray(props))，然后camelize(val)转驼峰写法，最后变成一个object返回，最后变成这样

props: {
  _myPropsDataTwo: object,
  myPropData: object,
  myPropDataOne: object
}


第二个是obj，所以会走 else if (isPlainObject(props))，然后for in操作，然后camelize(val)转驼峰写法，最后变成一个object返回

详情可以看控制台打印的数据，原理两者都是一样，变成object返回，只是后者功能更加丰富了，这个
使用过Vue的应该都能看明白