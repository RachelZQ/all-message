### 实现两栏（三栏）布局的方法(4种)
- 表格布局
- float + margin 布局（兼容性好）
- inline-block 布局（需要处理间隙问题）
- flexbox布局（简单，但兼容性不是很好）
#### 表格布局
分3层，最外层display:table,第二层：display:table-row;第三层:display:table-cell
```javascript
<div class="table">
    <div class="table-row">
        <div class="left table-cell">left</div>
        <div class="right table-cell">right</div>
    </div>
</div>
```