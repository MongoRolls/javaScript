## 数组的sort()方法



- sort是**原位排序** （原位是指在此数组内，而非生成一个新数组。)原位是指在此数组内，而非生成一个新数组。)
- sort是**非递减**排序，快排等解决

- 默认不加参数的sort是**将数组元素进行字符串排序**

  ```js
  let array = [1,6,15];
  
  array.sort();
  
  array;//[1, 15, 6]
  ```

  

## 编写自己想法的sort

可以定义一个cmp函数来进行执行

```js
let array = [1,15,6];

function cmp(a,b)
{
    if(a > b)return 1;
    else if(a == b)return 0;
    else if(a < b)return -1;//
}
array.sort(cmp);

array;//[1, 6, 15]
```

也可以用箭头函数

```js
array.sort((a,b)=>
           {
    console.log(a + '?' + b);//也可以看看内部比较了哪些数
   return a - b; 
});
```

