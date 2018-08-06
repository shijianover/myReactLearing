Title         : 阮一峰React 学习笔记
Author        : shijian


[TITLE]

# 原教程连接 

[阮一峰React教程]

# React的HTML模板

```html
  <!DOCTYPE html>
  <html>
    <head>
      <script src="../build/react.js"></script>
      <script src="../build/react-dom.js"></script>
      <script src="../build/browser.min.js"></script>
    </head>
    <body>
      <div id="example"></div>
      <script type="text/babel">
        // ** Our code goes here! **
      </script>
    </body>
  </html>
```
可以看到Script标签的type属性为*text/babel*，这是因为React所使用的JSX语法和标准的javaScript是不兼容的。
凡是使用JSX的地方都系要*type="text/babel"*</br>

加载的库：</br>
1. react.js (React的核心库)</br>
2. react-dom.js(React提供与dom相关的功能)</br>
3. Browser.js(将jsx语法转换为标准javaScript语法，教程中指出了这一步是非常消耗时间的，
用在生产环境的时候必须放在服务器完成。具体解决方案有待学习)</br>
4. 将jsx语法转换成标准javaScript的方案：</br>
```html
 $ babel src --out-dir build 
```
该命令可将src目录中的js文件进行转换，将原本的jsx语法转换成标准javaScript语法。</br>
# React的基本方法
```html
  <!DOCTYPE html>
  <html>
    <head>
      <script src="../build/react.js"></script>
      <script src="../build/react-dom.js"></script>
      <script src="../build/browser.min.js"></script>
    </head>
    <body>
      <div id="example"></div>
      <script type="text/babel">
        ReactDOM.render(
          <h1>Hello, world!</h1>,
          document.getElementById('example')
        );
      </script>
    </body>
  </html>
```
# jsx语法
```html
  <!DOCTYPE html>
  <html>
    <head>
      <script src="../build/react.js"></script>
      <script src="../build/react-dom.js"></script>
      <script src="../build/browser.min.js"></script>
    </head>
    <body>
      <div id="example"></div>
      <script type="text/babel">
        var names = ['Alice', 'Emily', 'Kate'];
  
        ReactDOM.render(
          <div>
          {
            names.map(function (name, index) {
              return <div key={index}>Hello, {name}!</div>
            })
          }
          </div>,
          document.getElementById('example')
        );
      </script>
    </body>
  </html>
 ```
上面体现了JSX的基本语法规则：
"<"开头就用html规则解析，"{"开头就用JavaScript解析
  
jsx可以再模板中直接插入变量，如果变量是一个数组，会展开所有的成员并展示
代码如下：
```html
<!DOCTYPE html>
<html>
  <head>
    <script src="../build/react.js"></script>
    <script src="../build/react-dom.js"></script>
    <script src="../build/browser.min.js"></script>
  </head>
  <body>
    <div id="example"></div>
    <script type="text/babel">
      var arr = [
        <h1 key="1">Hello world!</h1>,
        <h2 key="2">React is awesome</h2>,
      ];
      ReactDOM.render(
        <div>{arr}</div>,
        document.getElementById('example')
      );
    </script>
  </body>
</html>

```







[阮一峰React教程]: http://www.ruanyifeng.com/blog/2015/03/react.html  "Madoko reference manual"
