# 知乎（仿制版）
> 由于后端未提供相应接口文档，本次展示只有前端部分，内容相对较少，请多多包涵！
## 目录结构
`-- workTogether
    |               `-- defaultAvator.jpeg
    `-- login
    |   |           `-- class.css
    |   |           `-- close.png
    |   |           `-- header.png
    |   |           `-- log.html
    |   |           `-- open.png
    |   |           `-- sign_bg.47eec442.png
    |               `-- v2-f6b1f64a098b891b4ea1e3104b5b71f6_720w.png
    `-- main
        |           `-- main-answer
        |   |       `-- class-answer.css
        |   |       `-- header.png
        |   |       `-- main-answer.html
        |   |       `-- recommend.png
        |   |       `-- search.png
        |           `-- writing center.png
        |-- main-collection
        |   |       `-- class-collection.css
        |   |       `-- collection.png
        |   |       `-- header.png
        |   |       `-- main-collection.html
        |   |       `-- recommend.png
        |   |       `-- search.png
        |           `-- writing center.png
        |-- main-homepage
        |   |       `-- class-homepage.css
        |   |       `-- header.png
        |   |       `-- main-homepage.html
        |   |       `-- recommend.png
        |   |       `-- search.png
        |           `-- writing center.png
        |-- main-individual
        |   |       `-- class-individual.css
        |   |       `-- header.png
        |   |       `-- main-individual.html
        |   |       `-- recommend.png
        |   |       `-- search.png
        |           `-- writing center.png
        |-- main-passage
        |   |       `-- class-passage.css
        |   |       `-- header.png
        |   |       `-- main-passage.html
        |   |       `-- preview.css
        |   |       `-- preview.html
        |   |       `-- recommend.png
        |   |       `-- search.png
        |           `-- writing center.png
        |-- main-password
        |   |       `-- class-password.css
        |   |       `-- header.png
        |   |       `-- main-password.html
        |   |       `-- recommend.png
        |   |       `-- search.png
        |           `-- writing center.png
        `-- video.webp
        
  ## 技术栈      
  本次用到的技术栈均为原生的html，js和css
  ## 功能实现
  本项目根据原本知乎页面一共做了五个页面，分别为主页，回答问题，发布文章，我的收藏，个人信息以及密码更改。<br>
  - 登录界面根据原知乎的样式设置为首次登录及注册的形式，同时考虑实现功能复杂度只做了密码登录一种，对于密码框采取了密码框显示与隐藏的功能。若密码提供正确则跳转到首页（未实现）
  - 主页计划设置为显示发布的文章并提供评论功能（未能实现）
    主要实现了下滑时导航栏切换效果，通过js判断下滑高度并通过`transition`设置导航栏的动画效果，实现下滑时   导航栏的切换，同时设置回到顶部按钮，同样通过`transition`实现从无到有的动画效果
  - 回答问题界面设置为显示发布的问题并提供评论功能（未实现）
  - 收藏功能设置为显示收藏的问题和文章（未实现）
  - 个人信息页面实现了对知乎原本页面的较为完整的还原，基本的页面信息修改都可以在前端展示出来，不过由于浏览器自身的安全协议，无法通过localstorage上传头像，导致前端无法自己实现更换头像

- 在发布问题和发布文章时都实现了一定程度的文本编辑器功能，其中一部分借助修改div的`contenteditable = true`后设置`document.execCommand()`来修改选区的文字样式，对于代码块，链接等采用向元素中添加子元素的方式模拟富文本编辑器的效果，对于插入图片使用了`<input type ="file">`并用`label`来定义插入图片的样式，并创建`img`元素，通过`URL.createObjectUrl（）`获取其src值并append到选区中实现图片的插入。
- 在文章发布界面同时实现预览功能，通过`localstorage`获取选区内容，并在预览界面呈现。
