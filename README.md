# learn-vue

## 基础复习

#### js数据类型

- 基本: number string boolean null udefined
- Object function
- Symbol(es6)

#### 数组的变异方法

-操作数组的方法

pop

push

unshift

shift

slice (不能改变原数据)

splice

reverse

sort

indexOf

lastIndexof

concat

forEach

filter

map

some 

every

reduce

*es6

includes

find

- forEach

  1. forEach不支持return
  2. 两个参数 第一个是回调中有两个参数 item index 第二个是改变this指向

  ```
  let arr = [1,2,3,4,5]
  arr.forEach(function(item,index){
  	console.log(item)
  })
  ```

  for in循环中的key会变成字符串 包括数组的私有属性也可以打印出来

  for of (es6) 支持return 并且是值of数组 不能遍历对象 Object.keys将对象的key作为新的数组

- filter 

  1. 不会改变原数组
  2. 返回过滤后的新数组
  3. 回调函数返回的结果 true 表示这一项放到新数组中

  ```
  let arr = [1,2,3,4,5]
  let newArr = arr.filter(function(item,index){
    return item<5&&item<2;
  })
  // [3,4]
  ```

- map 映射 将原有的数组映射成一个新数组

  1. 不改变原数组
  2. 返回新数组
  3. 回调函数中返回什么 这一项就是什么

  ```
  let arr = [1,2,3]
  let newArr = arr.map(function(item,index){
    return `
   		<li>${item}</li> 
    `
  })
  // ['<li>1</li>',<li>2</li>,<li>3</li>]
  ```

  #### filter与map什么时候用

   删除 用filter

  更新 用map

- some

  

















