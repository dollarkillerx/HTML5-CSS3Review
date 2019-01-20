# HTML5-CSS3 Review
HTML5-CSS3 Review

## 新的网页结构
- `header`  头
- `nav` 导航
- `article` 与上下文无关的独立类容
- `section` 完整的文章
- `aside` 内容相关的辅助信息
- `footer` footer
  
## 新增的主体结构元素
- `article`  独立的内容
- `section`  用于分块 相对独立 不推荐没有标题的内容使用section
- `aside`    内容相关的辅助信息 应用OR小广告
- `nav`      导航
- `time`     `<time datetime="2019-1-19">2019-1-19</time>`
- `pubdate`  文件发布时间`<time datetime="2019-1-19" pubdate='pubdate'>2019-1-19</time>`
- `header`   具有引导和导航的区域 比如网站标题OR文章标题
- `dl`       用于表示数语
``` 
    <dl>
        <dt>定义术语</dt>
        <dd>解释术语</dd>
    </dl>
```
当容器要设置样式时,推荐使用`div`

## CANVAS
- 创建画布
``` 
<canvas id='canvas' width='500' height='500'></canvas>
```
- 引入绘画JS
- 使用draw语句绘画
>步骤
- 获取canvas元素
- 得到上下文
    - getContent()
- 填充与绘画边框
    - 填充 fill
    - 绘制边框 stroke
- 设置绘制样式
    - fillStyle填充样式
    - strokeStyle图形边框样式
- 指定画笔宽度
- 设置颜色值
- 绘画

>绘制矩形
``` 
<body onload="draw('canvas')">
    <canvas id="canvas" width="500" height="500">

    </canvas>

    <script>
        function draw(id) {
          let canvas = document.getElementById('canvas')
          let context = canvas.getContext('2d')
          context.fillStyle = "#000"   
          context.strokeStyle = "#f60"
          context.lineWidth = 5
          context.fillRect(0,0,400,300)   //x,y,w,h
          context.strokeRect(50,50,180,120) //x,y,w,h
          context.strokeStyle = "#fff"
          context.strokeRect(110,110,180,120)
        }
    </script>
</body>
```

#### canvas绘制动画 通过不断更改坐标 擦除 重绘
- 设置动画间隔 setInterval(code,millisec) 单位毫秒
- 用来绘图的函数 
   - 通过不断更待X和Y的坐标
   - 在该函数中先用clearRect方法将画布整体或者局部擦除
   
注释:这边我就不看了 继续HTML5吧  有空深入了解下CANVAS

## 本地储存
- sessionStorage 临时储存
- localStorage  永久储存
- loadStorage.length   获取数据条数
- loadStorage.clear()  清除
- loadStorage.key(index) 传入index 获取数据
``` 
  设置
    sessionStorage.setItem('key','value')
    or
    sessionStorage.key = 'value'
  获得
    let value = session.getItem('key')  
    or
    let value = session.key(index)
```

[小demo 简单的网页浏览版]('./Storage/Storage.html')
- new Date().getTime() 获取当前时间搓

# CSS3 部分

### 选择器部分

- `[att*=val]` 如果元素用att表示的属性值中包含val指定字符,就选择
- `[att^=val]` 如果用att表示的属性值的开头符号用val指定的字符的话
- `[att$=val]` 如果以这个结尾

#### 结构性伪类选择器
- a:link 未被访问连接
- a:visited 已被访问
- a:hover 鼠标放上去
- a:active 鼠标点击上去
- :first-line 用于某个元素第一行
- :first-letter 用于某个元素中的文字的首字母
- :before 在元素之前插入内容
- :after 在元素之后插入内容
- :root 绑定到页面的根元素中
- :not 排除子结构元素 body :not(h1){color:red}
- :empty 内容为空白选择
- :target 用户点餐超链接,并且跳转到target元素后起作用
- :first-child 第一个子元素
- :last-child 最后一个子元素
- :nth-last-child(n)匹配倒数第n个子元素
- :nth-child(n)匹配正数第n个元素
- :nth-child(odd)匹配奇数(even)匹配偶数
- :nth-of-type 匹配同一类型元素正数 :nth-last-of-type  倒数 (odd) 奇数 (even) 偶数

### 元素状态选择器
- :hover
- :active
- :focus 元素获得光标焦点时
- :enabled 元素处于可用状态
- :disabled 元素处于不可用状态
``` 
        input[type='text']:hover{
            background-color: #008a00;
        }
        input[type='text']:focus{
            background-color: #9933ff;
        }
        input[type='text']:active{
             background-color: #0066cc;
        }
```

#### 使用选择器插入内容
- after
- before
``` 
        h2:before{
            content: 'Tile';
            color: #fff;
            background-color: green;
            padding: 1px 15px;
            margin-right: 10px;
        }
        图片:
        content: url()
        计数器:
        content:counter(计算器名称)
        
```

### 文字阴影与自动换行
- text-shadow 增加阴影  :x y 模糊半径 color
- word-break 页面文字自动换行 
- word-wrap 让浏览器在长单词或很长的url地址中间进行换行
- font-face
``` 
    @font-face{
    font-family:webFont;
    src:url('font/字体名称.otf')fontmat('opentype')
    }
```

