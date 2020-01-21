# learnyouhtml

# HTML (HyperText Markup Language)

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

# Tags

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

# 屬性(Attributes)

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

## `<img>`

* `<img>` 可以在頁面上嵌入圖像，這個標籤有幾個重要的屬性
  - `src` ： 圖像的鏈結，`<img>`一定需要此屬性
  - `alt` ： 圖像的替代文字，當圖像無法顯示或者還在載入中，將會顯示此文字
  - `height`、`width` ：分別代表圖像畫素的固定高度與寬度

```html
<img src="path/to/file" alt="some text">
```

---

# Inline text

* 有時候我們需要強調文字，例如定義、人名、書名...等
接下來將會說明如何達成

## Font faces

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


## Upper and lower indexes

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

## Pitfalls

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

# Headings

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

---

# Lists

* 在HTML裡有三種列表
  - 有序列表 ( Ordered list )
  - 無序列表 ( Unorderd list )
  - 說明列表 ( Definitions list )

## Oreder list

* 如果你想要建立一個有編號的列表，你需要使用`<ol>` ( oreder list 的縮寫 )，且使用`<li>` ( list item 的縮寫 ) 來描述列表的物件
 
Example：
```html
<ol>  
  <li>first item</li>  
  <li>second item</li>  
  <li>third item</li>  
</ol> 
```

Preview：
> <ol>  
>   <li>first item</li>  
>   <li>second item</li>  
>   <li>third item</li>  
> </ol> 

* 有序列表使用升序編號，標號可以是任何形式，像是數字、字母、羅馬數字。
* `<ol>` 有幾個有用的屬性
  - `type` ： 指定編號種類
    - 1 ： 預設，數字
    - a ： 小寫英文字母編號
    - A ： 大寫英文字母編號
    - i ： 小寫羅馬字母編號
    - I ： 大寫羅馬字母編號
  - `start` ： 指定編號從第n個開始遞增，n參數總是一個整數
  - `reversed` ： 列表將使用降續編號

## Unorder list

* 無序列表同樣使用`<li>`描述列表物件。主要的不同處是，改為使用`<ul>` ( unorder list 的縮寫 ) 包裹全部的列表物件。

Example：
```html
<ul>  
  <li>first item</li>  
  <li>second item</li>  
  <li>third item</li>  
</ul>
```

Preview：
> <ul type = "disc">  
>   <li>first item</li>
>   <li>second item</li>
>   <li>third item</li>
> </ul>

* `<ul>` 同樣的可以使用`type`屬性，可替換圓點的樣式
  - disc ： 預設，實心園
  - circle ： 空心圓
  - square ： 方塊

## Definitions lists

* 有時你需要製作一個詞彙表或者 key-value pairs 的列表。`<dl>` ( definitions list 的縮寫 )即是你所需的標籤。
* `<dl>` 用來封閉所有列表物件
* `<dt>` (definition term) ： 用來表示說明的項目
* `<dd>` ： 用來包裹所有的說明

Example：
```html
<dl>  
  <dt>HTML</dt>  
  <dd>  
    The standard markup language for creating web pages and web applications.  
  </dd>  
<!-- Other terms and descriptions -->  
</dl>
```

Preview：
> <dl>  
>   <dt>HTML</dt>  
>   <dd>  
>     The standard markup language for creating web pages and web                applications.  
>   </dd>
> </dl>

# Tables

* `<table>`創建表格
* `<tr>` ( table row ) 創建列 ( row )
* `<td>` ( table data ) 創建欄( column )

Example：
```html
<table>  
   <tr>  
     <td>1.1</td>  
     <td>1.2</td>  
   </tr>  
   <tr>  
     <td>2.1</td>  
     <td>2.2</td>  
   </tr>  
 </table> 
```

Preview：
<table>  
  <tr>  
   <td>1.1</td>  
   <td>1.2</td>  
  </tr>  
  <tr>  
   <td>2.1</td>  
   <td>2.2</td>  
  </tr>  
</table> 

```html
<table>  
 ╔═════════════════════╗  
 ║ <tr>                ║  
 ║┏━━━━━━━━━┳━━━━━━━━━┓║  
 ║┃ <td>    ┃ <td>    ┃║  
 ║┃┌───────┐┃┌───────┐┃║  
 ║┃│  1.1  │┃│  1.2  │┃║  
 ║┃└───────┘┃└───────┘┃║  
 ║┃ </td>   ┃ </td>   ┃║  
 ║┗━━━━━━━━━┻━━━━━━━━━┛║  
 ║ </tr>               ║  
 ╠═════════════════════╣  
 ║ <tr>                ║  
 ║┏━━━━━━━━━┳━━━━━━━━━┓║  
 ║┃ <td>    ┃ <td>    ┃║  
 ║┃┌───────┐┃┌───────┐┃║  
 ║┃│  2.1  │┃│  2.2  │┃║  
 ║┃└───────┘┃└───────┘┃║  
 ║┃ </td>   ┃ </td>   ┃║  
 ║┗━━━━━━━━━┻━━━━━━━━━┛║  
 ║ </tr>               ║  
 ╚═════════════════════╝  
 </table>
 ```

* `<th>` ( table head ) 能替表格加入表頭，且標頭文字將會自動加上粗體

```html
<table>
   <tr>
     <th>First name</th>
     <th>Last name</th>
   </tr>
   <tr>
     <td>John</td>
     <td>Doe</td>
   </tr>
   <tr>
     <td>Jane</td>
     <td>Doe</td>
   </tr>
</table>
 ```

<table>  
 <tr>  
   <th>First name</th>
   <th>Last name</th> 
 </tr>  
 <tr>  
   <td>John</td>  
   <td>Doe</td>  
 </tr>  
 <tr>  
   <td>Jane</td>  
   <td>Doe</td>  
 </tr>  
</table>

---

# Blocks

* 接下來將介紹如何使用 UI 元素

## HTML `<div>` element

* `<div>` 是一個流內容( flow content )的常用容器，使用它來集結元素，做樣式調整、製作章節...等的動作
 
Example：
```html
<div>  
  <p>Any kind of content here. Such as &lt;p&gt;, &lt;table&gt;. You name it!</p>  
</div>  
```

Preview：
<div>  
  <p>Any kind of content here. Such as &lt;p&gt;, &lt;table&gt;. You name it!</p>  
</div>  

## Semantic elements (章節型元素)

![Semantic elements](Semantic&#32;elements&#32;.png)

### HTML `<main>` element

* `<main>` 呈現`<body>`的主要內容

### HTML `<header>` element

* `<header>` 呈現介紹性或導覽性的幫助，通常包含一些標題和其他元素，例如logo、搜尋欄...等等

Example：
```html
<header>  
  <h1>Main Page Title</h1>
  <img src="site-log.png" alt="Site logo">
</header>
```

### HTML `<nav>` element

* `<nav>` 代表一個網頁中提供導航欄連結的區域，可以連結到其他頁面，或者頁面中的其中一部分

Example：
```html
 <nav>  
  <ul>  
    <li>Home</li>  
    <li>About</li>  
    <li>Contact</li>  
  </ul>  
</nav> 
```

### HTML `<footer>` element

* `<footer>` 呈現一個頁尾，通常包含作者資訊、版權、相關文檔的連結。

Example：
```html
 <footer>  
  Some copyright info or perhaps some author info for an &lt;article&gt;?  
 </footer>  
```

### HTML `<section>` element

* `<section>` 為文件裡的一個段落。`<section>`需要能夠被清楚辨識，通常都包含一個標題(`<h1>`-`<h6>`element)

Example：
```html
<section>  
  <h1>Heading</h1>
  <p>Bunch of awesome content</p>  
</section>
```

### HTML `<aside>` element

* `<aside>`表示一個和其餘頁面內容幾乎無關的部分。通常為一個側邊欄

```html
<aside>  
  <!-- aside content -->  
</aside>  
```

### HTML `<article>` element

* `<article>`表示文檔、頁面、應用、網站的一個獨立結構。主要目的為成為可獨立分配、重複使用的結構。例如在PO文、雜誌、新聞文章...等其他獨立內容的項目。

---

# Links and References

* 連結允許你前往另一個網頁，或者訪問HTML檔案和其他任何種類的檔案。這些檔案甚至能被放置在另一個網站。
* 為了建立一個連結，你必須告訴瀏覽器，連結是什麼、你想訪問地址的哪一個文件。這裡使用`<a>` ( ancher ) 標籤。

Example：
```html
<a href="https://google.com/" target="_blank">Google</a>
```

Preview：
<a href="https://google.com/" target="_blank">Google</a>

* `<a>`常用屬性
  - `href` ： 添加一個URL或 URL fragment
  - `downland` ： 命令瀏覽器下載URL，而不是訪問它
  - `target` ： 指定在哪裡打開被連結的URL
    - `_blank`值可使連結在新的瀏覽器分頁打開

* 當然，也可以使用圖像取代連結文字

Example：
```html
<a href="https://google.com" target="_blank">
  <img src="path/to/google-logo.png" alt="Google logo" />
</a>
```

* `<a>`也很常被用來開啟使用者的郵件程式，寄信給收件人

Example：
```html
<a href="mailto:email@someone.com">Send email to someone</a>
```

Preview：
<a href="mailto:email@someone.com">Send email to someone</a>

---

# Forms

* 你絕對記得有些網站會有Email或者username和password的輸入區域。接下將會說明如何創造它。
* `<form>`代表一個包含互動性的控制去提交資訊的文件段落。以下介紹幾個最重要的屬性。
  - `action` ： 提交表單時，向某處發送資料
  - `method` ： 規定使用的 HTML 方法
    - value 為 post 時使用 POST 方法
    - value 為 get 時使用 GET 方法
  - `name` ： 表單的名字。文件裡表單的名字不能重複。

* 知道`<form>`後，你需要知道的是`<input>`。
* `<input>`被用來創造一個互動性的控制，為了接受來自用戶端的資料。`<input>`如何運作，取決於`type`屬性的值。
* 以下為一些`type`使用的值
  - `text` ： 預設，單一行的文字。輸入值中的換行會自動地移除
  - `button` ： 一個可點擊的按鈕，沒有任何預設的行為，可使用JS添加行為。
  - `checkbox` ： 一個檢查鈕，必須使用`value`屬性來定義被提交的值。可使用`checked`屬性預設這個物件是已經被選擇的。
  - `file` ： 提供一個控制給使用者選擇一個檔案，包含文字和一個“瀏覽”按鈕。
  - `password` ： 單一行文字，輸入值會被隱藏。
  - `radio` ： 單選按鈕，必須使用`value`屬性來定義被提交的值。可使用`checked`屬性預設這個物件是已經被選擇的。
  - `submit` ： 一個可以提交此表單的按鈕。