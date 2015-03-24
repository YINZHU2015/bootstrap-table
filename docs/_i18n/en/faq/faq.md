# FAQ []({{ site.repo }}/blob/master/docs/_i18n/{{ site.lang }}/faq/faq.md)

### 你好，非常感谢您提供了一个如此强大而且好用的插件，但是我想请教一下您的插件里面，queryParamsType这个属性在整体控件中是一个什么样的作用呢？，因为我将它设置为空，代码也是可以正常执行，而且我看了您的源代码，一时也难以明白这个属性执行的那些代码的是用来做什么工作的呢？

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
