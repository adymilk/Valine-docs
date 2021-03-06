---
title: 文章阅读量统计
---

Valine 从 `v1.2.0-beta1` 开始支持文章阅读量统计。

``` js
new Valine({
    el:'#vcomments',
    ...
    visitor: true // 阅读量统计
})
```

> 如果开启了`阅读量统计`，Valine 会`自动检测` leancloud 应用中是否存在`Counter`类，如果不存在`会自动创建`，**无需手动创建**~


Valine会自动查找页面中`class`值为`leancloud_visitors`的元素，获取其`id`为查询条件。并将得到的值填充到其`class`的值为`leancloud-visitors-count`的子元素里：

``` html
<!-- id 将作为查询条件 -->
<span id="/visitor.html" class="leancloud_visitors" data-flag-title="文章阅读量统计">
    <span class="post-meta-item-text">阅读量 </span>
    <span class="leancloud-visitors-count">1000000</span>
</span>
```
<span id="/visitor.html" class="leancloud_visitors" data-flag-title="文章阅读量统计">
    <span class="post-meta-item-text"> 当前页访问次数 </span>
    <i class="leancloud-visitors-count">0</i>
</span>

> Next 主题`阅读量统计`请参考：[#hexo-theme-next/pull/345](https://github.com/theme-next/hexo-theme-next/pull/345)