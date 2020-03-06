---
title: "在GithubPages上支持MathJax(Latex)"
categories:
  - Post Formats
tags:
  - Post Formats
last_modified_at: 2020-03-04T15:33:37-04:00
---


使用Kramdown时可以选择使用由MathJax提供的LaTex格式至PNG格式的数学区块渲染器，详见[Kramdown-math blocks](https://kramdown.gettalong.org/syntax.html#math-blocks)

具体代码块：在 includes/head.html 中添加

```html
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$']]
    }
  });
</script>
```

***

引擎警告说是网址弃用不更新,详见[MathJax CDN shutting down on April 30,2017.](http://link.zhihu.com/?target=https%3A//www.mathjax.org/cdn-shutting-down/)


更改的代码：

```html
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

```

以及更多[MathJax](https://www.mathjax.org/#gettingstarted)的使用指导。

***

### Test

\( 2 + 2 = 5 \)
\( 2^2 + \sqrt{b^2+3} \)
