# reveal.js的pandoc模板

reveal.js的说明请看[这里](https://github.com/hakimel/reveal.js/blob/master/README.md)

## 文件说明

除了原版的reveal.js库里的文件以外，增加的文件有：

- `template-revealjs.html`  pandoc模板文件
- `slides.md`  示例文件
- `/css/custom.css` 用户自定义的样式文件

`index.html`是原版的演示文件，`slides.md`是我的示例文件，编译之后为`slides.html`，点[这里](https://github.com/yanping/reveal.js-with-pandoc.git)查看效果

## 使用方法

如果源文件是Rmd文件，先用[knitr](https://github.com/yihui/knitr)处理

```r
library(knitr)
knit("slides.Rmd")
```

得到md文件后运行命令：

```
pandoc -t html5 --template=template-revealjs.html --standalone --section-divs   --variable theme="default"   --variable transition="cube" slides.md -o slides.html
```

可直接运行`build.bat`批处理文件

注意，不管是直接在命令行下输命令，还是执行批处理文件，可以设置两个参数

- `theme` 可选的reveal.js主题有："sky", "beige", "simple","serif", "night", "default"
- `transition` 可选的slides切换方式有："default", "cube","page", "concave", "zoom", "linear", "fade", "none"

## 其他

可以在<http://rvl.io>上在线编辑reveal.js的slides

