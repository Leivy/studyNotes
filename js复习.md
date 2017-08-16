### 数值类型转换

+ 转字符串:String();toString();+"";

+ 转数值:Number();   str-/+str;  parseInt();-->保留整数;   parseFloat();-->保留第一个小数;

+ 转布尔类型: 所有值都可以转布尔类型,Boolean(str); 在判断语句中用的比较多,转换成false的几种情况:0/undefined/null/nan/""/false;

+ NaN是数据类型,表示值不是一个数值;isNaN();判断是否为数字,返回true说明不是数字,NaN跟谁都不等;NaN==NaN?返回false;

+ 核心复合类型:object和function;构造函数:object,Date,Number等

+ 变量声明之后未赋值是undefined;变量永远不可能自动为null,除非手动赋值,null是对象的空值,undefined是数值类型的空值;

+ typeof只是关键字,可用typeof str;或者typeof(str);小括号只是用来提升优先级;typeof复杂类型都是object,除了typeof function的结果是function;

+ instanceof:判断是否是某类型`arr instanceof Array`

+ 只要是对象,转成布尔值都是true;

+ 当一个引用类型数据和值类型的数据进行运算,遵循如下结果

  + 先调用引用类型的valueof方法,获取返回值,进行运算;
  + 如果valueof的返回值无法运算,继续用引用类型 的toString方法进行运算;

+ in关键字:

  + for-in:遍历对象的键
  + 属性名 in 对象--->返回true和false;判断能否通过对象访问这个指定的属性;

+ 逻辑中断短路运算

  + a || b:如果a为真,则返回a的值,否则返回b的值'
  + a && b:如果a为假,返回a的值,否则返回b的值;

+ delete关键字:

  + 删除变量,删除未使用var声明的变量;
  + 删除对象的属性;
  + 数组删除后是留坑,值是undefined,数组长度不变;所以一般用splice();
  + 删除对象用delete;

+ 对象的动态特性:对象在创建后,可以为对象新增或删除属性的特性就是对象的动态特性

  + 点语法和关联数组语法

+ 值类型存储的是数据本身;引用类型存储的是数据的地址,数据单独存储在内存中,地址赋值给变量;

+ 连等:实际开发中,不推荐连等;js的特殊处理方式:a.num=a={num:4};解释--->a先暂存一份,压栈,即变量已经被存储成地址了,然后a被赋值新的对象,再修改暂存a的num属性为{num:4};即

  + ```javascript
    a.num=a={num:4};
    //等式解释如下:
    var temp=a;
    a={num:4};
    temp.num=a;
    ```

+ **异常处理语句**:

  + 异常:报错,阻断代码运行;

  + UNcaught reference:引用错误;UNcaught sy:语法错误;

  + 异常处理的目的就是捕获异常,防止异常阻断代码的正常运行;

    + ```javascript
      try{
        //可能会出现的异常代码
      }catch(e){
        //只要发生异常,这里的代码就会执行
        //e代表发生异常的异常信息
      }finally{
        //无论是否发生异常都会执行的代码
        //一般会放一些释放资源的操作
      }
      ```

+ 手动制造异常:

  + throw

    + ```javascript
      functin(a,b){
        if(!a || !b){
         throw "手动报错,可写任何东西" 
        }
        return a+b;
      }
      ```

+ console:浏览器控制台是一个js运行环境,和页面中书写的js处于同一个环境.

  + console.time和console.timeEnd可以计算代码运行时间;console.table:打印出表格的形式;

+ 断点调试:

  + 条件断点 add 
  + 断点全部隐藏, deactive
  + 直接跳转到错误的代码行 parse on 

+ network:

  + preserve log:保存上个页面的请求信息
  + disable cache:浏览器缓存禁用,保证每次页面请求都是新的返回数据
  + offline:断网
  + no throttling:切换网速环境

### 运算符的优先级

+ 括号()--> 一元运算符**++  --  !**  --> 算数运算符 ***  /  %  +  -** --> 关系运算符 **>  >=  < <=** -->  相等运算符 **== != === !==**  --> 逻辑运算符 **&&  ||**

### 三元运算符

+ a==b?c:d;-->解释:a等于b吗?等于则返回c,否则返回d; 前面是判断语句,后面是输出结果;



### 数组

+ 把Math对象作为apply()的第一个参数,从而正确的设置this值,然后可以将任何数组作为第二个参数.

  + ```javascript
     var values=[1,2,3,4,5];
      var max=Math.max.apply(Math,values);
      console.log(max);
     ```
    ```

  + ​
    ```

### lable语句

+ ​

### DOM

+ 拿到文本域的内容,顺便清除前后空格

  + ```javascript
    var content=txt.value.trim();
    ```

  ##### 1. Event对象

  Event对象代表事件的状态,比如事件在其中发生的元素、键盘按键的状态、鼠标的位置、鼠标按钮的状态。事件通常与函数结合使用，函数不会在事件发生前被执行！

  鼠标键盘属性:

  | 属性                                       | 描述                         |
  | ---------------------------------------- | -------------------------- |
  | [altKey](http://www.w3school.com.cn/jsref/event_altkey.asp) | 返回当事件被触发时，"ALT" 是否被按下。     |
  | [button](http://www.w3school.com.cn/jsref/event_button.asp) | 返回当事件被触发时，哪个鼠标按钮被点击。       |
  | [clientX](http://www.w3school.com.cn/jsref/event_clientx.asp) | 返回当事件被触发时，鼠标指针的相对可视区水平坐标。  |
  | [clientY](http://www.w3school.com.cn/jsref/event_clienty.asp) | 返回当事件被触发时，鼠标指针的相对可视区垂直坐标。  |
  | [ctrlKey](http://www.w3school.com.cn/jsref/event_ctrlkey.asp) | 返回当事件被触发时，"CTRL" 键是否被按下。   |
  | [metaKey](http://www.w3school.com.cn/jsref/event_metakey.asp) | 返回当事件被触发时，"meta" 键是否被按下。   |
  | [relatedTarget](http://www.w3school.com.cn/jsref/event_relatedtarget.asp) | 返回与事件的目标节点相关的节点。           |
  | [screenX](http://www.w3school.com.cn/jsref/event_screenx.asp) | 返回当某个事件被触发时，鼠标指针的相对屏幕水平坐标。 |
  | [screenY](http://www.w3school.com.cn/jsref/event_screeny.asp) | 返回当某个事件被触发时，鼠标指针的相对屏幕垂直坐标。 |
  | [shiftKey](http://www.w3school.com.cn/jsref/event_shiftkey.asp) | 返回当事件被触发时，"SHIFT" 键是否被按下。  |