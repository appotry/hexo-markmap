[English](https://github.com/MaxChang3/hexo-markmap/blob/main/README_EN.md)
| 简体中文 |

依赖于 [markmap](https://github.com/gera2ld/markmap)，灵感来自 [hexo-simple-mindmap](https://github.com/HunterXuan/hexo-simple-mindmap)

> **⚠️更新 1.1.3+ 版本更好的适配开启 pjax 的站点**

[![NPM](https://nodei.co/npm/hexo-markmap.png)](https://nodei.co/npm/hexo-markmap/)

# hexo-markmap
在你的博客中使用markdown插入思维导图，使用markmap。

现已经支持 链接、代码块、markdown、Katex、多行代码语法的渲染！

> 多行代码仍有一定渲染问题，可能出现报错。

更多预览和说明见 [我的博客](https://zhangmaimai.com/2021/02/23/hexo-mindmap-plugin/).
# 安装
```
npm install hexo-markmap
```
或
```
yarn add hexo-markmap
```

# 使用
```
{% markmap height [depth] %}
```

## 参数
- `height`: 画布高度
- `depth`: 可选，自动折叠层数深于 `depth` 的节点

## 示例
````
{% markmap 400px %}
- links
- **inline** ~~text~~ *styles*
- multiline
  text
- `inline code`
- ```js
  console.log('code block');
  console.log('code block');
  ```
- Katex - $x = {-b \pm \sqrt{b^2-4ac} \over 2a}$
{% endmarkmap %}
````

## 配置文件

将相应内容追加到 config.yml 中。

约定大于配置，如果你不需要以下某个功能，那么无需添加该配置项。 

默认情况下，他可以很好的正常工作。每个选项都有缺省项。

### pjax 修复
默认值 `false`
```yaml
hexo_markmap:
  pjax: true
```
如果你的博客安装了 pjax 请开启此项配置。

### KaTeX
默认值 `false`
```yaml
hexo_markmap:
  katex: true
```

如果你需要使用 $K\kern-.25em\raise.45ex {\scriptstyle{A}}\kern-.15em\TeX$ 请开启此项配置以插入 css 文件。如果博客本身已经通过其他方式配置 $K\kern-.25em\raise.45ex {\scriptstyle{A}}\kern-.15em\TeX$ 则无需开启.

> 如果你同时装有 `mathjax`，也请打开此项。
### Prism
默认值 `false`
```yaml
hexo_markmap:
  prism: true
```

如果需要插入代码块，请开启此项配置以插入 css 文件。如果博客本身已经通过其他方式配置 prism 则无需开启.

### 自定义 CDN
```yaml
hexo_markmap:
  CDN:
    d3_js: https://fastly.jsdelivr.net/npm/d3@6
    markmap_view_js: https://fastly.jsdelivr.net/npm/markmap-view@0.2.7
    katex_css: https://fastly.jsdelivr.net/npm/katex@0.12.0/dist/katex.min.css
    prism_css: https://fastly.jsdelivr.net/npm/prismjs@1.25.0/themes/prism.css
```

### 缺省项
```yaml
hexo_markmap:
  pjax: false
  katex: false
  prism: false
  CDN:
    d3_js: https://fastly.jsdelivr.net/npm/d3@6
    markmap_view_js: https://fastly.jsdelivr.net/npm/markmap-view@0.2.7
    katex_css: https://fastly.jsdelivr.net/npm/katex@0.12.0/dist/katex.min.css
    prism_css: https://fastly.jsdelivr.net/npm/prismjs@1.25.0/themes/prism.css
```
