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

