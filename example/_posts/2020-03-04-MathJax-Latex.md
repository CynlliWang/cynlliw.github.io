---
title: "MathJax(Latex)"
categories:
  - Jekyll
last_modified_at: 2020-03-04T15:33:37-04:00
---


使用Kramdown时可以选择使用由MathJax提供的LaTex格式至PNG格式的数学区块渲染器，详见[Kramdown-math blocks](https://kramdown.gettalong.org/syntax.html#math-blocks)

具体代码块：在 includes/head.html 中添加

```html
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
    jax: ["input/TeX", "output/HTML-CSS"],
    tex2jax: {
        inlineMath: [ ['$', '$'] ],
        displayMath: [ ['$$', '$$']],
        processEscapes: true,
        skipTags: ['script', 'noscript', 'style', 'textarea', 'pre', 'code']
    },
    messageStyle: "none",
    "HTML-CSS": { preferredFont: "TeX", availableFonts: ["STIX","TeX"] }
});
</script>
<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
```

***


以及更多[MathJax](https://www.mathjax.org/#gettingstarted)的使用指导。

***

### Test

$$h(x)=\theta_0+\theta_1$$

$$ax^2 + bx + c = 0$$

* 引擎警告说是网址弃用不更新,详见[MathJax CDN shutting down on April 30,2017.](http://link.zhihu.com/？target=https%3A//www.mathjax.org/cdn-shutting-down/)，更改如下：

```html
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

```

* 无法渲染，怀疑官方cdn访问过慢，更改为国内BootCDN:

```html
<script src="//cdn.bootcss.com/mathjax/2.7.0/MathJax.js?config=Tex-AMS-MML_HTMLorMML"></script>
```
* 这个js还是会调用MathJax官方的配置js文件，所以添加dns-prefetch用于网页加速

```html
<link rel="dns--prefetch" href="//cdn.boots.com"/>
```

* 还是他媽的渲染不出，改用了火狐
* SHITE
* 渲染成功，具体方式：骂它。

