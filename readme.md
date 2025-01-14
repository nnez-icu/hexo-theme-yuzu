# Hexo-Theme-Yuzu
本项目从 [hexo-theme-orange](https://github.com/Orange-way/hexo-theme-orange) fork 出来，鉴于无法找到原作者联系方式，本项目将由[Cerallin](https://github.com/Cerallin)继续维护。

**当前分支为 v3.x 版本**，使用pug代替ejs作为模板引擎。

**注意** 从v2.x迁移到v3.x，请参考[迁移指南](docs/migrate.md)。鼠标悬停在网页页脚`Theme Yuzu`上可以查看当前主题版本。

## 安装使用

```shell
# 在hexo网站源码目录下执行
$ npm i hexo-renderer-pug
$ mkdir -p themes && cd themes
$ git clone https://github.com/Cerallin/hexo-theme-yuzu
```

将 `config.yml` 中 `theme` 字段改为 `hexo-theme-yuzu`，在 `config.yml` 中添加如下内容：

```yml
since_year: 2020

# 此处的theme_config.root请设置与root相一致（一般在url下一行）
theme_config:
  root: /

post_copy:
  text: 署名-非商业性使用-相同方式共享
  text_en: CC BY-NC-SA 2.5 CN
  link: https://creativecommons.org/licenses/by-nc-sa/2.5/cn/

# 自定义侧边栏
menu:
  Archives:
    widget: Archives # 三种：Archives | Posts | Tags
  Posts1:
    name: Posts
    widget: Posts
  Posts2:
    name: Posts2
    widget: Posts
  Tags:
    widget: Tags

# 右上角
otherMenu2:
  关于: /about

# 备案
beian:
  enable: true
  icp: 京ICP备xxxxxxxx号

# toc
toc: true

visit_count:
  type: busuanzi
  # or
  # type: visitor-counter
  # url: //your.counter.site/count.php
```

**In case you didn't know** 你可以创建一个`_config.[theme name].yml`文件来覆盖主题的默认设置。对于上述安装方法来说，就是`_config.hexo-theme-yuzu.yml`。

## 示例网站

- 主题展示网站：[cerallin.github.io](https://cerallin.github.io)
- 学术写作指南：[一篇博客](https://cerallin.github.io/notes/2021/12/12/%E5%A6%82%E4%BD%95%E9%85%8D%E7%BD%AE%E4%B8%80%E4%B8%AA%E5%AD%A6%E6%9C%AF%E5%86%99%E4%BD%9C%E5%8D%9A%E5%AE%A2/)

什么？你问我小说站在哪？我才不会告诉你呢(/ω•＼*)。

## 特色
- 黑白色调，风格质朴简约。
- 针对文章创作优化，学术博客也是可以的 (?)。
- 支持深色模式，自适应电脑/手机深浅色模式。

## 功能
- 支持分页（hexo-generator-*）
- 支持显示 CC（Creative Commons）版权声明
- 文章文字两端对齐
- 适配学术写作（pandoc）

## 禁止用户复制粘贴网页内容

**注** 本选项仅为君子协定，通过插件可以轻易破解。
将主题配置文件中的`selectable`值改为`false`。

## 深色模式

将主题配置文件中的`dark_mode`值改为`true`。

## 学术写作指南

请先安装`hexo-renderer-pandoc`。

### 三线表格

```md
| key          | value                    |  type   |
| :----------- | :----------------------- | :-----: |
| num          | 65535                    | integer |
| post         | {id: 4, content: "text"} | object  |
| article_list | [{id: 1}, {id: 2}]       |  array  |
: 表格名 {#ref:tbl-name}
```

### 图

```md
![figure description](/path/to/figure.jpg){#ref:fig-name}
```

### 推荐插件

- hexo-filter-mathjax: 渲染生成mathjax公式；
- [hexo-filter-text-autospace](https://github.com/cerallin/hexo-filter-text-autospace): 为中文段落中的英文自动添加间距。
- hexo-clean-css：缩小生成的CSS文件的体积。由于Stylus自身的限制，本主题的CSS文件大小有很大的缩减空间。

## [辅助工具类](./docs/helpers.md)

本主题提供了一些类似tailwind css的辅助工具类。

例如，通过`text-{left|right|justify}`控制文字对齐，使用 `m{t|r|b|l}-{size}` 功能类控制元素一侧的外边距等等。

详细介绍请移步[这里](./docs/helpers.md)。

## TODOs

- [ ] 整理主题变量
- [ ] 重构模板布局，优化模板缓存
- [ ] 开发“关于”页的模板
- [ ] 更多动画
- [ ] 更多的helpers类

## License

This project is under MIT License.

    Copyright (c) 2021-2023 Cerallin   <cerallin@cerallin.top>

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.

### Bootstrap icons

Part of [Bootstrap opensource SVG icon library](https://github.com/twbs/icons) is used in this project, which is under MIT license.

### Clipboard.js

[Clipboard.js](https://github.com/zenorocha/clipboard.js) is used in this project, which is under MIT license.

### Smooth-corners.js

[Smooth-corners.js](https://github.com/wopian/smooth-corners) is used in this project, which is under MIT license.
