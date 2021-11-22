**js是什么**
> js是网站三层结构中的行为层，负责处理网站的数据与事件交互。js是一门动态的，弱类型脚本语言。

**js变量有哪些**
> boolean、null、undefinde、number、string、symbol、bigint、object。其中基础数据类型有：boolea、undefined、number、string、symbol、bigint、。引用类型有：object

**如何判断数据是什么类型**

- typeof
> typeof可以基本区分引用类型和基础数据类型，当数据为Array、Regex等时，返回值均为object

- instanceof
> instanceof 可以判断数据是否某一个具体类型
```javascript
function instanceOf(left, right){
    let leftValue = left._proto_
    let rightValue = right.prototype
    while(true){
        if(leftValue == null) {
            return false
        } 
        if(leftValue == rightValue){
            return true
        }
        leftValue = leftValue._proto_
    }
}
```

- Object.prototype.toString().call(value)





