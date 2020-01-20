# learnyouhtml

## HTML (HyperText Markup Language)

* HTML is a markup language for creating webpages.  

* HTML is used to mark and describe each of thes kind of content so the web browser can show them correctly.

```html
一個基本的html檔案

<!DOCTYPE html>  
<html>  
  <head>  
    <meta charset="utf-8">  
    <title>Hello, world!</title>  
  </head>  
  <body>  
    here is a body  
  </body>  
</html>
```

---

## Tags

* HTML 使用 “標記語言”
* tags 通常是一對的，各自代表著開頭與結束
* Opening tags 有一個 keyword 且被 "<" 和 ">"包裹。例如：`<p>`。
* Ending tags 也是一樣的，只不過在 keyword 前多一個 slash(/)。例如`</p>`
* 比較特別的標籤，不用 Ending tag。
  - `<br>` - 文字換行
  - `<img>` - 代表一個圖像文件，實際用法稍後敘述
  - `<hr>` - 畫出一條水平線，通常用於分隔段落

```html
<!DOCTYPE html>  
<html>  
  <head>  
    <meta charset="utf-8">  
    <title>Hello, world!</title>  
  </head>  
  <body>  
    here is a body  
  </body>  
</html>
```

* `<!DOCTYPE>` 這個宣告代表著此文件的種類，幫助瀏覽器顯示正確的網頁
* `<html>` 包裹整個文件，代表 HTML 文件 從哪裡開始、到哪裡結束
* 在 `<head>` 裡放進所有關於文件的資訊，例如 meta-tags 和 `<title>`
    - meta-tags 表示我們要使用哪種文字編碼(charset)
    - `<title` 會被顯示在瀏覽器的標題欄
* 在 `<body>` 放進所有我們要呈現的資訊，例如標題、文字、圖像...等
* 可以利用註解(comments)留下開發者的訊息

```html
<!-- this is a single-line comment -->
    
<!--
  this
  is
  a
  multi-line
  comment
-->
```

---

## 屬性(Attributes)

* 標籤屬性可以增加或控制標籤的行為，例如顏色、大小...等等

```html
<tag attribute1="value1" attribute2="value2">some text</tag> 
```

* 屬性值使用雙引號( " )或者單引號( ' )包裹起來，否則屬性只會承認等號後面的值

```html
<!-- with double quotes -->  
<tag attribute="value with spaces"></tag>  
<!-- with single quotes -->  
<tag attribute='value with spaces'></tag>

<!-- without quotes -->  
<tag attribute=value with spaces></tag>
<!-- with 和 spaces 將會被視為無效的屬性 -->
```

### `<img>`

* `<img>` 可以在頁面上嵌入圖像，這個標籤有幾個重要的屬性
  - `src` ： 圖像的鏈結，`<img>`一定需要此屬性
  - `alt` ： 圖像的替代文字，當圖像無法顯示或者還在載入中，將會顯示此文字
  - `height`、`width` ：分別代表圖像畫素的固定高度與寬度

```html
<img src="path/to/file" alt="some text">
```

---

## Inline text

* 有時候我們需要強調文字，例如定義、人名、書名...等
接下來將會說明如何達成

### Font faces

* `<strong>`、`<b>` ： 文字粗體

```html
<p>Here are few <strong>important</strong> words</p>
```
> <p>Here are few <strong>important</strong> words</p>

* `<em>`、`<i>`：文字斜體

```html
<p>Here are few <em>important</em> words</p>
```

> <p>Here are few <em>important</em> words</p>


### Upper and lower indexes

* 有時數學、物理、化學需要表示上指數與下指數
* HTML 也有相對應的標籤可以使用

* `<sup>` ： 上指數
* `<sub>` ： 下指數

```html
<p><b>The formula of sulfuric acid:</b> <i>H<sub>2</sub>SO<sub>4</sub></i></p>

<p><b>Pythagoras's theorem:</b> a<sup>2</sup> + b<sup>2</sup> = c<sup>2</sup></p>
```

> <p><b>The formula of sulfuric acid:</b> <i>H<sub>2</sub>SO<sub>4</sub></i></p>

> <p><b>Pythagoras's theorem:</b> a<sup>2</sup> + b<sup>2</sup> = c<sup>2</sup></p>

### Grouping inline elements

* 有時需要包裹其他文字或者元素，不為了表示什麼，只是為了調整樣式。
* `<span>` 就是為此目的

```html
<p>My mother has <span style="color:blue">blue</span> eyes.</p>
```

> <p>My mother has <span style="color:blue">blue</span> eyes.</p>

### Pitfalls

* 在瀏覽器裡，多個空白只會被視為一個空白。下面三個例子的顯示效果是相同的。

```html

<p>one. two. three<p>  
<p>one.    two.    three<p>  
<p>one.        two.        three<p>

```

> <p>one. two. three<p>

* HTML 不支援 hyphenation ，編輯器也相同。也就是說，不能將字分開。

* 文字佔用了瀏覽器視窗的所有寬度。
  - 假如你只寫了一長條的HTML code，瀏覽器將會自動排版它。
  - 假如文字比視窗寬度還要寬，瀏覽器會出現下方的捲軸。

* Character entity reference (字元實體參照)是一種HTML中一種對字元跳脫序列的表示
  - 跳脫是當於無法在代碼中寫出所要的字元的時候所採用的，以多個字元的有序組合來表示原本需要的字元的手段
  - `& quot;` ： double quotation mark ( " )
  - `& apos;` ： apostrophe (apostrophe-quote) ( ' )
  - `& amp;` ： ampersand ( & )
  - `& lt;` ： less-than sign ( < )
  - `& gt;` ： greater-than sign ( > )
  - [others symbol](https://dev.w3.org/html5/html-author/charref)

```html
<h1>Don't be afraid to be <then a 100% success & >more:</h1>

<h1>Don't be afraid to be &lt;then a 100% success &amp; &gt;more:</h1>
```

> <p>Don't be afraid to be <then a 100% success & >more:</p>
> <p>Don't be afraid to be &lt;then a 100% success &amp; &gt;more:</p>

---

## Headings

* 大部分的文章需要有規則的分割內文，HTML 提供了六種等級的標題元素

```html
<h1>Heading level 1</h1>  
<h2>Heading level 2</h2>  
<h3>Heading level 3</h3>  
<h4>Heading level 4</h4>  
<h5>Heading level 5</h5>  
<h6>Heading level 6</h6> 
```
> <h1>Heading level 1</h1>  
> <h2>Heading level 2</h2>  
> <h3>Heading level 3</h3>  
> <h4>Heading level 4</h4>  
> <h5>Heading level 5</h5>  
> <h6>Heading level 6</h6> 

* 標題可以吸引讀者的注意力，告訴他這裡有東西必須要讀
* 儘管標題可以增加字體大小，但請不要用此方法來達成，可以使用CSS屬性。
* 使用標題時避免跳級，總是從`<h1>`開始，下一個使用`<h2>`，以此類推。
* 通常網頁只用`<h1>`～`<h3>`即可，很少使用更低級的標題。