## HTML / CSS / JavaScript 筆記

### 目錄
* [HTML](#html)
	* [🔴 HTML 架構](#html架構)
	* [🔴 head](#head)
	* [🔴 body](#body)
* [CSS](#css)

## HTML
### 🔴HTML架構
```html
<!DOCTYPE html>
<html lang = "zh-TW"> <!-- lang指定網頁語系 -->
    <head>
		<!-- 瀏覽器的相關資訊 -->
    </head>
    <body>
		<!-- 顯示在網頁上的資訊 -->
    </body>
</html>
```

<br>

### 🔴head 
在head區塊中，會放置與網頁的相關資訊  `<起始標記 屬性名稱1=設定值1 屬性名稱2=設定值2 ...>`  
* **`<title> 網站名稱 </title>` 說明此網頁的標題，並顯示在瀏覽器的標題列**  
* **`<link rel="與目前網站的關係" href="連結">` 建立與其他檔案或外部資源的連結，以下介紹rel相關屬性**  
	1. 樣式與圖示
		* `stylesheet` : 連結外部 CSS 檔案來美化網頁
		* `icon` : 定義網頁的小圖示
		* `apple-touch-icon` : 把網頁加入到主畫面時iPhone/iPad 時顯示的圖示
	2. 效能優化
		* `preload` : 告訴瀏覽器先下載的資源
		* `preconnect` : 預先連線到外部伺服器
		* `dns-prefetch` : 預先進行DNS查詢
	3. SEO與連結的關係
		* `canonical` : 標準連結
		* `alternate` : 定義替代版本  

* **`<meta>` 描述網頁特性**
	1. `charset` 文件字元編碼
		* `UTF-8` : <推薦>目前網路標準編碼，支援全世界語言
		* `Big5` : 早期使用的繁體中文版本
		* `ISO-8859-1` : 早期的西歐語言編碼
		* `GB2312` : 簡體中文編碼
		* `UTF-16` : 使用較長的位元組來處理文字
	2. `name` 搭配content屬性使用，定義網頁的各項資訊
		* 搜尋引擎相關
			* `description` : 網頁摘要
			* `keywords` : 關鍵字
			* `robots` : 可不可以爬蟲
		* 視窗與顯示
			* `viewport` : 控制網頁在不同裝置的縮放比例
				* `width=device-width` : 寬度等於裝置寬度
				* `initial-scale=1.0` : 初始縮放等比例1:1
			* `theme-color` : 上方工具列顯示的顏色
		* 資訊紀錄與工具相關
			* `author` : 作者
			* `generator` : 網站是用什麼軟體產生的
			* `copyright` : 版權聲明
	3. `content` 屬性值  
		必須搭配name或property屬性
	4. `http-equiv` 模擬 HTTP 指令
		* `refresh` : 自動重新整理頁面或跳轉頁面
		* `X-UA-Compatible` : 指定IE瀏覽器的渲染模式
		* `content-security-policy` : 防止惡意腳本攻擊
	5. `property` 社群通訊協議
		* `og:title` : 分享時顯示的標題
		* `og:description` : 分享時顯示的副標題/摘要
		* `og:image` : 分享時顯示的縮圖
		* `og:url` : 分享時指向的標準網址

<br>

### 🔴body
在body區塊中，會顯示網頁的內容
1. **文本**  
	* `<h1>~<h6> </h1>~</h6>` : 標題 `<h1>`最大 `<h6>`最小
	* `<p> </p>` : 段落 
	* `<br>` : 換行 
	* `<hr>` : 水平線
	* `<blockquote>` : 縮排標籤
	* `<b><strong>` : 粗體
	* `<i><em>` : 斜體
	* `<u><ins>` : 底線
	* `<s><del>` : 刪除線
	* `<sup>` : 上標
	* `<sub>` : 下標
2. **清單**  
	* `<ul>` : 無序清單
	* `<ol>` : 有序清單
	* `<li>` : 清單中的每一列
3. **表格**  
	* `<table>` : 表格主體
	* `<tr>` : 一列
	* `<th>` : 表頭單位格(文字會粗體居中)
	* `<td>` : 一般資料單位格
4. **超連結**  
	`<a href="連結資源" target="連結方式">網站顯示的文字或圖片</a>`
	* `href` : 目標網址
		* 網址 : https://www.google.com/?hl=zh_TW
		* 站內網頁 : /admin/login.html  
			上一層資料夾要用 `../` 表示
		* 頁內 : #id名稱
		* 電子郵件 : mailto:電子郵件
	* `target`
		* `_self` : 顯示在目前視窗中
		* `_blank` : 顯示在新的視窗中
		* `_top` : 顯示整個視窗
		* `_parent` : 顯示在上一層框架中
		* `視窗名稱` : 顯示在指定名稱的視窗中
5. **圖片**  
	`<img src="圖檔路徑" alt="文字說明" ...>`
	* `src` : 設定圖檔路徑
	* `alt` : 圖片沒出現時的說明文字
6. **表單**  
	```html
	<form action="" method="" ...>
		<input type="欄位型別" name="欄位名稱">
	</form>
	```
	* form屬性
		* `action` : 用來處理表單資料程式的位置
		* `method` : 指定用戶端傳送到伺服器所採用的方式
		* `name` : 提供伺服器使用，根據name的欄位名稱存取資料
		* `id` : 識別名稱
		* `enctype` : 設定表單傳輸編碼類型
		* `accept` : 指定允許上傳的文件類型
		* `autocomplete` : 當使用者輸入時，會顯示先前資料
	* input屬性
		* `type` : 欄位樣式
			* `<input type="text">` : 建立單行文字欄位
			* `<input type="password">` : 建立密碼欄位
			* `<input type="radio">` : 建立單選按鈕
			* `<input type="checkbox">` : 建立核取方塊
			* `<input type="number">` : 建立數字欄位
			* `<input type="date">` : 建立日期選擇器
			* `<input type="email">` : 建立郵件欄位
			* `<input type="file">` : 建立檔案上傳按鈕
			* `<input type="submit">` : 建立送出按鈕
			* `<input type="reset">` : 建立重設按鈕
			* `<input type="hidden">` : 建立隱藏欄位
		* `name` : 欄位名稱
		* `value` : 欄位預設值
		* `placeholder` : 欄位提示文字
		* `required` : 設定為必填項目
		* `readonly` : 設定為唯讀
		* `disabled` : 禁用該欄位


* **語意化標記**  
	原本需要使用 `<div id="">` 來指定id屬性，現在可以透過以下標記去除div，與div功能相同
  
	```html
	<header>	<!-- 顯示網站名稱、主題、主題資訊 -->
	<nav>		<!-- 網站連結選單 -->
	<aside>	<!-- 使用側邊攔 -->
	<main>		<!-- 網頁主要內容，每個頁面只能有一個 -->
	<article>	<!-- 用於定義主內容區 -->
	<section>	<!-- 具有標題或章節的段落 -->
	<footer>	<!-- 置於頁尾，用來放置版權資訊、作者 -->
	<figure>	<!-- 指定獨立內容，圖片、圖表 -->
	<mark>		<!-- 要凸顯的文字 -->
	<audio>		<!-- 顯示音效控制列 -->
	```

## CSS

* `align` : 設定圖片與周圍的連結方式
	* `left` : 圖片靠左
	* `right` : 圖片靠右
	* `center` : 圖片置中
	* `bottom` : 文字對齊圖片下緣
	* `top` : 文字對齊圖片上緣
	* `middle` : 圖片垂直置中對齊文字
* `width` : 圖片寬度(px)
* `height` : 圖片高度(px)
* `border` : 設定圖片外框