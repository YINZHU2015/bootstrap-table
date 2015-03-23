# FAQ []({{ site.repo }}/blob/master/docs/_i18n/{{ site.lang }}/faq/faq.md)
首先非常感谢你的bootstrap的table 插件，这个非常好用。但是里面有部分属性我有一点疑惑，比如queryParamsType。它设置成limit是干什么用的呢，虽然我看了文档和源代码，但是我并没有看出它是起到了一个什么作用，如果设置了"limit的话"，不知道有没有大哥知道这个属性是什么意思啊？
---

### When resize the window, the table header does not adjust automatically, how to solve it?

When you set the `height` of bootstrap table, the `fixed header` feature is automatically enabled, that is what cause the problem, you need to listen the `resize` event of window and use the `resetView` method to solve this problem, code example:

```js
$(function () {
    $('#tableId').bootstrapTable(); // init via javascript

    $(window).resize(function () {
        $('#tableId').bootstrapTable('resetView');
    });
});
```

---

### How to better merge cells?

For merged cells, when you do refresh, next page or switch columns to show, the merge cells will be unmerged. We can listen the events(on load success, on column switch, on page change and on search) to solve this problem, code example:

```js
$table.on('load-success.bs.table column-switch.bs.table page-change.bs.table search.bs.table', function () {
    $table.bootstrapTable('mergeCells', {...});
});
```
