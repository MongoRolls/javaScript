手写版本（面试）

```javascript
let url = 'http://www.nowcoder.com?key=1&key=2&key=3&test=4#hehe';
  
  function parseParam(s,key)
  {
    let str = s.slice(s.indexOf('?') + 1);
    let arr = str.split('&');

    let obj = {};
    for(let x of arr)
    {
        let [key,value] = x.split('=');

        if(obj.hasOwnProperty(key))
        {
          obj[key]= [].concat(obj[key],value);
        }
        else
        {
          obj[key] = value;
        }
    }

    return obj;
  }

  let ans = parseParam(url);

  ans;
```

### 获取URL参数的方法：

1. **使用 JavaScript：**

   ```
   javascript// 获取当前页面的URL
   var currentURL = window.location.href;
   
   // 获取查询字符串
   var queryString = window.location.search;
   
   // 使用 URLSearchParams 获取参数
   var urlParams = new URLSearchParams(queryString);
   
   // 获取特定参数的值
   var parameterValue = urlParams.get('parameterName');
   ```