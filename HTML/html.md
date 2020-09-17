### HTML就是一种标记语言(用各种标签将 相关信息或者关键字 包裹起来，方便搜索引擎的抓取)
1:行内元素有哪些？块级元素有哪些？空（void）元素有哪些？
行内元素（不可以设置宽高，不独占一行）
```javascript
<a>、<abbr>、<acronym>、<b>、<bdo>、<big>、<br>、<cite>、<code>、<dfn>、<em>、<i>、<img>、<input>、<kbd>、<label>、<q>、<samp>、<select>、<small>、<span>、<strong>、<sub>、<sup>、<textarea>、<tt>、<var>
```
块元素（可以设置宽高，独占一行）
```javascript
<address>、<caption>、<dd>、<div>、<dl>、<dt>、<fieldset>、<form>、<h1>、<h2>、<h3>、<h4>、<h5>、<h6>、<hr>、<legend>、<li>、<noframes>、<noscript>、<ol>、<ul>、<p>、<pre>、<table>、<tbody>、<td>、<tfoot>、<th>、<thead>、<tr>
```
空
```javascript
<br> <hr> <img> <input> <link> <meta>
```
鲜为人知的：
```javascript
<area> <base> <col> <command> <embed> <link> <meta><keygen> <param> <source> <track> <wbr>
```
2:请描述一下 cookies，sessionStorage 和 localStorage 的区别？
- cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）
- cookie数据始终在同源的http请求中携带（即使不需要），即会在浏览器和服务器间来回传递
- sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存
- 存储大小：
cookie数据大小不能超过4k sessionStorage和localStorage虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大
- 有期时间：
localStorage 存储持久数据，浏览器关闭后数据不丢失除非主动删除数据 sessionStorage 数据在当前浏览器窗口关闭后自动删除 cookie 设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭
3:
