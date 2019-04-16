# learn-vue

## 基础复习

#### js数据类型

- 基本: number string boolean null udefined
- 复杂: Object function
- Symbol(es6)

#### 数组的变异方法

-操作数组的方法

- pop  从后面删除元素 只能是一个 返回值是删除的元素

  ```
  let arr = [1,2,3,4,5]
  console.log(arr.pop()) //5
  console.log(arr) //[1,2,3,4]
  ```

- push 从后面添加元素 返回值为添加完成后的数组长度

  ```
  let arr = [1,2,3,4,5]
  console.log(arr.push(5)) // 6
  console.log(arr) // [1,2,3,4,5,5]
  ```

- unshift  从前面添加元素 返回值是添加完成后的数组的长度

  ```
  let arr = [1,2,3,4,5]
  console.log(arr.unshift(2)) //6
  console.log(arr) // [2,1,2,3,4,5]
  ```

- shift  从前面删除元素  只能删除一个 返回值是删除的元素

  ```
  let arr = [1,2,3,4,5]
  console.log(arr.shift()) //1
  console.log(arr) // [2,3,4,5]
  ```

- slice(start,end) (不能改变原数据)  切去索引值start到索引值end的数组 不包含end索引的值 返回值是切出来的数组

  ```
  let arr = [1,2,3,4,5]
  console.log(arr.slice(1,3)) //[2,3]
  console.log(arr) // [1,2,3,4,5]
  ```


- splice(i,n)  删除从i（索引值）开始之后的n个元素 返回值是删除的元素

  ```
  let arr = [1,2,3,4,5]
  console.log(arr.aplice(2,2)) //[3,4]
  console.log(arr) // [1,2,5]
  ```

- reverse 将数组反转 返回值是反转后的数组

  ```
  let arr = [1,2,3,4,5]
  console.log(arr.reverse()) // [5,4,3,2,1]
  console.log(arr)
  ```

- str.split()  将字符串转换为数组

  ```
  let str = '12345'
  conosle.log(str.split('')) // ["1","2","3","4","5"]
  ```

- sort 将数组进行排序 返回值是排序好的数组 默认按照最左边的数字进行排序 不是按照数字大小排序的 

  ```
  let arr = [2,10,6,1,4,22,3]
  console.log(arr.sort()) // [1,10,2,22,3,4,6]
  let arr1 = arr.sort((a,b) => a-b)
  console.log(arr1) // [1,2,3,4,6,10,22]
  let arr2 = arr.sort((a,b) => b-a)
  console.log(arr2) [22,10,6,4,3,2,1]
  ```


- indexOf  查找某个元素的索引值 若有重复 则返回第一个查到的索引值 若不存在 则返回-1

  ```
  let arr = [1,2,3,4,5]
  let index = arr.indexOf(2)
  console.log(index)  // 1
  index2 = arr.indexOf(9)
  console.log(index2) // -1
  ```


- lastIndexof   和 indexOf一样只不过是从后边开始找


- concat 连接两个数组 返回值为连接后的新数组 合并数组

  ```
  let arr=[1,2,3,4,5]
  console.log(arr.concat([1,2])) // [1,2,3,4,5,1,2]
  console.log(arr) // [1,2,3,4,5]
  ```


- Array.from()  将为数组编程数组 就是只要有length的就可以转成数组 --es6

  ```
  let str = '12345'
  console.log(Array.from(str)) // ["1","2","3","4","5"]
  let obj = {0:"a"，1:"b",length:2}
  console.log(Array.from(obj)) // ["a","b"]
  ```


- includes  判断数组中包含给定的值  返回布尔值

  ```
  let arr = [1,2,3,4,5]
  let arr1 = arr.includes(2)
  console.log(arr1)
  ```

  **与indexOf的区别**

  1. indexOf 返回的是数值 而includes返回的是布尔值
  2. indexOf不能判断NaN 返回为-1 includes则可以判断


- find  找到第一个符合条件的数组成员

  ```
  let arr = [1,2,3,4,5,2,4]
  let arr1 = arr.find((value,index,array) => value > 2)
  console.log(arr1) // 3
  ```


- forEach

  1. forEach不支持return
  2. 两个参数 第一个是回调中有三个参数 item index  arr第二个是改变this指向

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

  ```javascript
  let arr = [1,2,3]
  let newArr = arr.map(function(item,index,array){
    return `
   		<li>${item}</li> 
    `
  })
  // ['<li>1</li>',<li>2</li>,<li>3</li>]
  ```

  #### filter与map什么时候用

   删除 用filter

  更新 用map

- some   判断数组中是否存在满足条件的项，只要有一项满足条件，就会返回true

  ```javascript
  var arr = [1, 2, 3, 4, 5];
  var arr2 = arr.some(function(x) {
  return x < 3;
  }); 
  console.log(arr2); // true
  var arr3 = arr.some(function(x) {
  return x < 1;
  }); 
  console.log(arr3); // false
  ```

- every  判断数组中每一项都是否满足条件，只有所有项都满足条件，才会返回true

  ```
  var arr = [1, 2, 3, 4, 5];
  var arr2 = arr.every(function(x) {
      	return x < 10;
      }); 
  console.log(arr2); // true
  var arr3 = arr.every(function(x) {
      	return x < 3;
      }); 
  console.log(arr3); // false
  ```

- reduce   reduceRight 

这两个方法都会实现迭代数组的所有项，然后构建一个最终返回的值。reduce()方法从数组的第一项开始，逐个遍历到最后。而 reduceRight()则从数组的最后一项开始，向前遍历到第一项。

这两个方法都接收两个参数：一个在每一项上调用的函数和（可选的）作为归并基础的初始值。

传给 reduce()和 reduceRight()的函数接收 4 个参数：前一个值、当前值、项的索引和数组对象。这个函数返回的任何值都会作为第一个参数自动传给下一项。第一次迭代发生在数组的第二项上，因此第一个参数是数组的第一项，第二个参数就是数组的第二项。

```
var values = [1,2,3,4,5];
var sum = values.reduceRight(function(prev, cur, index, array){
        return prev + cur;
    },10);
console.log(sum); //25
```

- arr.keys() 遍历数组的键名

```
let arr = [1,2,3,4]
let arr2 = arr.keys()
for (let key of arr2){
    console.log(key) // 0 1 2 3
}
```









 















