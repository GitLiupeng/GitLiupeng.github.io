<article class="markdown-body">
          <h1>
<a id="markdown语法" class="anchor" href="#markdown-%E7%BC%96%E8%BE%91%E5%99%A8%E8%AF%AD%E6%B3%95%E6%8C%87%E5%8D%97" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>Markdown 语法</h1>

<h2>
<a id="基本技巧" class="anchor" href="#%E5%9F%BA%E6%9C%AC%E6%8A%80%E5%B7%A7" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>基本技巧</h2>

<h3>
<a id="代码" class="anchor" href="#%E4%BB%A3%E7%A0%81" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>代码</h3>

<p>如果你只想高亮语句中的某个函数名或关键字，可以使用 <code>`function_name()`</code> 实现</p>

<p>通常编辑器根据代码片段适配合适的高亮方法，但你也可以用 <code>```</code> 包裹一段代码，并指定一种语言</p>

<pre>```javascript
(document).ready(function () {
    alert('hello world');
});
```</pre>
<p>支持的语言：<code>actionscript, apache, bash, clojure, cmake, coffeescript, cpp, cs, css, d, delphi, django, erlang, go, haskell, html, http, ini, java, javascript, json, lisp, lua, markdown, matlab, nginx, objectivec, perl, php, python, r, ruby, scala, smalltalk, sql, tex, vbscript, xml</code></p><p>也可以使用 4 空格缩进，再贴上代码，实现相同的的效果</p>
<pre>
    def g(x):
        yield from range(x, 0, -1)
    yield from range(x)</pre>

<h3>
<a id="标题" class="anchor" href="#%E6%A0%87%E9%A2%98" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>标题</h3>
<p>文章内容较多时，可以用标题分段：</p>
<pre>标题1
======

标题2
-----

## 大标题 ##
### 小标题 ###</pre>
<h3>
<a id="粗斜体" class="anchor" href="#%E7%B2%97%E6%96%9C%E4%BD%93" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>粗斜体</h3>
<pre>*<i>斜体文本</i>*    _<i>斜体文本</i>_
**<b>粗体文本</b>**    __<b>粗体文本</b>__
***<i><b>粗斜体文本</b></i>***    ___<i><b>粗斜体文本</b></i>___</pre>
<h3>
<a id="链接" class="anchor" href="#%E9%93%BE%E6%8E%A5" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>链接</h3>
<p>常用链接方法</p>
<pre>文字链接 [链接名称](http://链接网址)
网址链接 &lt;http://链接网址&gt;</pre>
<p>高级链接技巧</p>
<pre>
这个链接用 1 作为网址变量 [Google][1].
这个链接用 yahoo 作为网址变量 [Yahoo!][yahoo].
然后在文档的结尾为变量赋值（网址）
  [1]: http://www.google.com/
  [yahoo]: http://www.yahoo.com/
</pre>

<h3>
<a id="列表" class="anchor" href="#%E5%88%97%E8%A1%A8" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>列表</h3>

<p>普通无序列表</p>

<pre>- 列表文本前使用 [减号+空格]
+ 列表文本前使用 [加号+空格]
* 列表文本前使用 [星号+空格]</pre>
<p>普通有序列表</p>
<pre>1. 列表前使用 [数字+空格]
2. 我们会自动帮你添加数字
7. 不用担心数字不对，显示的时候我们会自动把这行的 7 纠正为 3</pre>
<p>列表嵌套</p>
<pre>1. 列出所有元素：
    - 无序列表元素 A
        1. 元素 A 的有序子列表
    - 前面加四个空格
2. 列表里的多段换行：
    前面必须加四个空格，
    这样换行，整体的格式不会乱
3. 列表里引用：

    &gt; 前面空一行
    &gt; 仍然需要在 &gt;  前面加四个空格

4. 列表里代码段：

    ```
    前面四个空格，之后按代码语法 ``` 书写
    ```

        或者直接空八个，引入代码块
</pre>

<h3>
<a id="引用" class="anchor" href="#%E5%BC%95%E7%94%A8" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>引用</h3>

<p>普通引用</p>

<pre>&gt; 引用文本前使用 [大于号+空格]
&gt; 折行可以不加，新起一行都要加上哦</pre>

<p>引用里嵌套引用</p>

<pre>&gt; 最外层引用
&gt; &gt; 多一个 &gt; 嵌套一层引用
&gt; &gt; &gt; 可以嵌套很多层</pre>

<p>引用里嵌套列表</p>

<pre>&gt; - 这是引用里嵌套的一个列表
&gt; - 还可以有子列表
&gt;     * 子列表需要从 - 之后延后四个空格开始</pre>

<p>引用里嵌套代码块</p>

<pre>&gt;     同样的，在前面加四个空格形成代码块
&gt;
&gt; ```
&gt; 或者使用 ``` 形成代码块
&gt; ```</pre>
                <h3>
<a id="图片" class="anchor" href="#%E5%9B%BE%E7%89%87" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>图片</h3>

                <p>跟链接的方法区别在于前面加了个感叹号 <code>!</code>，这样是不是觉得好记多了呢？</p>
                <pre>![图片名称](http://图片网址)</pre><p>当然，你也可以像网址那样对图片网址使用变量</p><pre>这个链接用 1 作为网址变量 [Google][1].
然后在文档的结尾位变量赋值（网址）

 [1]: http://www.google.com/logo.png</pre>
                  <p>也可以使用 HTML 的图片语法来自定义图片的宽高大小</p>
<pre>&lt;img src="htt://example.com/sample.png" width="400" height="100"&gt;</pre>

                <h3>
<a id="换行" class="anchor" href="#%E6%8D%A2%E8%A1%8C" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>换行</h3>
               <p>如果另起一行，只需在当前行结尾加 2 个空格</p><pre>在当前行的结尾加 2 个空格
这行就会新起一行</pre><p>如果是要起一个新段落，只需要空出一行即可。</p>

                <h3>
<a id="分隔符" class="anchor" href="#%E5%88%86%E9%9A%94%E7%AC%A6" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>分隔符</h3>
                <p>如果你有写分割线的习惯，可以新起一行输入三个减号<code>-</code>。当前后都有段落时，请空出一行：</p>
<pre>前面的段落

---

后面的段落</pre>
<br>
                <h2>
<a id="高级技巧" class="anchor" href="#%E9%AB%98%E7%BA%A7%E6%8A%80%E5%B7%A7" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>高级技巧</h2>
                <h3>
<a id="行内-html-元素" class="anchor" href="#%E8%A1%8C%E5%86%85-html-%E5%85%83%E7%B4%A0" aria-hidden="true"><span aria-hidden="true" class="octicon octicon-link"></span></a>行内 HTML 元素</h3>
<p>目前只支持部分段内 HTML 元素效果，包括 <code>&lt;kdb&gt; &lt;b&gt; &lt;i&gt; &lt;em&gt; &lt;sup&gt; &lt;sub&gt; &lt;br&gt;</code> ，如</p>

<p>键位显示</p>

<pre>使用 &lt;kbd&gt;Ctrl&lt;kbd&gt;+&lt;kbd&gt;Alt&lt;kbd&gt;+&lt;kbd&gt;Del&lt;kbd&gt; 重启电脑
</pre>

<p>代码块</p>

<pre>使用 &lt;pre&gt;&lt;/pre&gt; 元素同样可以形成代码块</pre>

<p>粗斜体</p>

<pre>&lt;b&gt; Markdown 在此处同样适用，如 *加粗* &lt;/b&gt;</pre>

<pre><code>            &lt;h3&gt;符号转义&lt;/h3&gt;
            &lt;p&gt;如果你的描述中需要用到 markdown 的符号，比如 &lt;code&gt;_&lt;/code&gt; &lt;code&gt;#&lt;/code&gt; &lt;code&gt;*&lt;/code&gt; 等，但又不想它被转义，这时候可以在这些符号前加反斜杠，如 &lt;code&gt;\_&lt;/code&gt;  &lt;code&gt;\#&lt;/code&gt;  &lt;code&gt;\*&lt;/code&gt; 进行避免。&lt;/p&gt;
</code></pre>

<pre>
\_不想这里的文本变斜体\_
\*\*不想这里的文本被加粗\*\*
</pre>

<pre><code>            &lt;h3&gt;扩展&lt;/h3&gt;
            &lt;p&gt;支持&lt;b&gt; jsfiddle、gist、runjs、优酷视频&lt;/b&gt;，直接填写 url，在其之后会自动添加预览点击会展开相关内容。&lt;/p&gt;
</code></pre>

<pre>http://{url_of_the_fiddle}/embedded/[{tabs}/[{style}]]/
https://gist.github.com/{gist_id}
http://runjs.cn/detail/{id}
http://v.youku.com/v_show/id_{video_id}.html
</pre>

<pre><code>            &lt;h3&gt;公式&lt;/h3&gt;
            &lt;p&gt;当你需要在编辑器中插入数学公式时，可以使用两个美元符  包裹 TeX 或 LaTeX 格式的数学公式来实现。提交后，问答和文章页会根据需要加载 Mathjax 对数学公式进行渲染。如：&lt;/p&gt;
</code></pre>

<pre> x = {-b \pm \sqrt{b^2-4ac} \over 2a}.


x \href{why-equal.html}{=} y^2 + 1

</pre>

<p>同时也支持 HTML 属性，如：</p>

<pre> (x+1)^2 = \class{hidden}{(x+1)(x+1)}


(x+1)^2 = \cssId{step1}{\style{visibility:hidden}{(x+1)(x+1)}}
</pre>
        </article>