# 網站更新教學(持續更新中)

## 更新 News 頁面
在 news.html 中，找到以下程式碼：
```
<thead>
  <tr><th>Date</th><th>News</th></tr>
</thead>
<tbody>
```
將內容新增至 \<tbody> 中，最新的 news 更新在最上面。<br>
使用 \<tr> 標籤新增一個 row ，並在此 row 中使用 \<td> 標籤增加兩個 column 。<br>
第一個 col 為年份及時間(20XX/XX)，第二個 col 為內容。<br>
將重點內容以 \<span> 標籤標註藍字及粗體，
以下為範例：
```
<tr>
  <td class="col-1">2025/03</td>
  <td>新增<span style="color: blue;  font-weight: bold;">網站內容更新說明文件</span></td>
</tr>
```

## 更新 Publications 頁面
publications 頁面分為 Journal 及 Conference 兩個 section，<br>
更新方式相同，以下使用 Journal 作為範例。

在 publications.html 中找到以下程式碼：
```
<thead>
  <tr><th><h1 class="text-center">Journal</h1></th></tr>
</thead>
<tbody>
```
將內容新增至 \<tbody> 中，最新的 publication 更新在最上面。<br>
使用 \<tr> 標籤新增一個 row ，並在此 row 中使用 \<td> 標籤增加一個 column，<br>
範例程式碼如下：
```
<tr>
  <td>
    <div class="">
      <a type="button"data-bs-toggle="modal"
          data-bs-target="#文章互動式窗的ID">
        <h4 class="p-0 m-0">文章名稱</h4>
        <p class="p-0 m-0">In 期刊名稱, 20XX</p>
      </a>
      <p class="text-muted p-0 m-0">AUTHORS</p>
          &nbsp<a class="link-dark" href="PDF位置" download><i class="fa-2x fa-solid fa-file-pdf"></i></a>
          &nbsp<a class="link-dark" href="介紹影片連結"><i class="fa-2x fa-brands fa-youtube"></i></a>
          &nbsp&nbsp<a class="link-dark" type="button" data-bs-toggle="modal" data-bs-target="citation互動式窗的ID"><i class="fa-2x fa-solid fa-quote-left"></i></a>
          &nbsp&nbsp<a href="DOI連結" class="link-dark">DOI</a>
    </div>
  </td>
</tr>
```
點擊文章標題會出現一互動視窗為該文章的內容，<br>
因此要將參數 data-bs-target 更改為文章互動視窗的 ID，命名規則為"文章名稱"。
```
<a type="button"data-bs-toggle="modal"
          data-bs-target="#文章名稱">
```
另外點擊 citation 圖示也會出現一互動視窗，可讓使用者快速複製 citation 內容，<br>
因此將參數 data-bs-target 更改為 citation 互動視窗的 ID，命名規則為"文章名稱_cite"。
```
&nbsp&nbsp<a class="link-dark" type="button" data-bs-toggle="modal" data-bs-target="文章名稱_cite"><i class="fa-2x fa-solid fa-quote-left"></i></a>
```
更新完以上內容後，文章會出現在表格的最上方，接下來我們要新增該文章的兩個浮動頁面：文章內容、Citation。<br>
在 Publication.html 中找到以下程式碼：
```
<!-- Journal modal popup-->
```
若是更新 Conference Paper 就找到以下程式碼：
```
<!-- Conference modal popup -->
```
新增文章內容及 Citation 的區塊，
範例程式碼如下：
```
<!-- 文章名稱 -->
<div class="modal fade" id="文章名稱" tabindex="-1"  aria-hidden="true">
  <div class="modal-dialog modal-dialog-scrollable modal-xl">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title">文章名稱</h3>
      </div>
      <div class="modal-body">
        <h4>Author</h4>
        <p>作者</p>
        <h4>Abstract</h4>
        <p>摘要</p>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
<div class="modal fade" id="文章名稱_cite" tabindex="-1"  aria-hidden="true">
  <div class="modal-dialog modal-dialog-scrollable modal-xl">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title">文章名稱</h3>
      </div>
      <div class="modal-body">
        <textarea id="文章名稱_cite_text" rows='10'class="form-control" disabled readonly>
引用(BibTex 格式)
        </textarea>
      </div>
      <div class="modal-footer">
        <button class="btn btn-outline-secondary" type="button" onclick="copyModalContent('文章名稱_cite_text')">Copy</button>
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
```
主要分為兩個 \<div>，一個文章內容、一個 Citation 內容，<br>
前者 id 命名格式分別為"文章名稱"，後者為"文章名稱_cite"。<br>
在 Citation 中有幾個參數需要特別設定，<br>
首先先將 \<textarea> 的 id 設置為"文章名稱_cite_text"，<br>
接著將第一個 \<button> 中的 onclick 參數設置為"copyModalContent('文章名稱_cite_text')"<br>

完成以上動作後就更新完 Publication 了！


## 更新 Pics 頁面
Pics 頁面分為 頂部照片輪轉、論文發表、CONTESTS、ACTIVITIES 四個 section，<br>

### 更新頂部照片輪轉section
在 pics.html 中找到以下程式碼：
```
<section id="TopCarousel" class="page-section bg-primary pb-5">
```
裡面包為頂部照片輪轉的內容，<br>
若要新增照片，則找到 class="carousel-indicators" 的區塊，<br>
新增一個 button，範例程式如下：
```
<button type="button" data-bs-target="#picscarousel" data-bs-slide-to="7" aria-label="Slide 8"></button>
```
其中要改的參數為 data-bs-slide-to 以及 aria-label，<br>
接著在\<div class="carousel-inner" style="border-radius: 5%;"> 中新增以下程式碼：
```
<div class="carousel-item" >
  <img src="照片位置" class="img-fluid w-100 h-100" alt="...">
  <div class="carousel-caption d-none d-md-block">
    <h5>標題</h5>  
  </div>
</div>
```
請注意：第一張照片有一個預設的 class: active!

### 更新論文發表、CONTESTS、ACTIVITIES section
論文發表、CONTESTS、ACTIVITIES 這三個 section 的更新方式大同小異，<br>
以下使用論文發表作為範例。

在 pics.html 中找到以下程式碼：
```
<section id="PublicationsPresent" class="page-section bg-primary pt-0 pb-5">
  <div class=" container text-center">
      <h1>論文發表</h1>
      <div class="owl-carousel owl-theme" id="paperpics">
```
接下來分為兩個不同的做法，<br>
#### 1. 需要彈出式視窗說明活動內容：
新增以下程式碼：
```
<div class="item card slider ">
  <div class="hovereffect">
    <img class="img-responsive" src="圖片位置" />
    <div class="overlay">
      <h2>標題</h2>
      <a class="info" type="button" data-bs-toggle="modal" data-bs-target="自定義modal名稱">Click!</a>
    </div>
  </div>
  <h4>標題</h4>
  <p class="text-muted mb-2">地點</p>
</div>
```
並且在 code 中尋找 \<!-- modal --> 這個註解，<br>
在以下新增彈出式視窗的內容，以下為範例：
```
<!-- 自定義modal名稱 modal -->
<div class="modal fade" id="自定義modal名稱" tabindex="-1"  aria-hidden="true">
  <div class="modal-dialog modal-dialog-scrollable modal-xl">
    <div class="modal-content">
      <div class="modal-header">
        <h3 class="modal-title">活動標題</h3>
      </div>
      <div class="modal-body">
        <div class="text-center container">
          <h4>內容</h4>
          <img src="圖片位置">
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
      </div>
    </div>
  </div>
</div>
```
根據不同需求可在彈出式視窗中自訂不同的樣式，<br>
其他的範例請參考 pics.html 中其他 modal。<br>

#### 2. 不需要彈出式視窗
與前者最大差距為不需要新增 modal，<br>
並且在鼠標移過去後不需要顯示 Click! 按鈕，範例程式如下：
```
<div class="item card slider">
  <div class="hovereffect">
    <img class="img-responsive" src="照片位置" />
    <div class="overlay">
      <h2>標題</h2>
    </div>
  </div>
  <h4>標題</h4>
  <p class="text-muted mb-2">地點</p>
</div>
```

## 更新 Members 頁面
僅一section，分為 Ph.D.、MASTER STUDENTS、ALUMNI、UNGRADUATED STUDENTS 四個區塊，<br>
分別找到對應區塊後，在 \<div class="row"> 中新增以下程式碼：
```
<div class="col-xl-3 col-lg-4 col-md-6 col-sm-6  text-center mt-5">
  <img class="img-fluid rounded-circle" src="照片位置" style="width: 80%;"/>
  <h3 class="mt-2 mb-0">名稱</h3>
  <p class="mb-0">在學日期</p>
  <p class="text-muted mb-2">電子郵件</p>
  <a class="btn btn-dark btn-social rounded-circle" href="GITHUB連結"><i class="fab fa-github"></i></a>
  <a class="btn btn-light btn-social rounded-circle" href="LINKEDIN連結"><i class="fab fa-linkedin-in"></i></a>
</div>
```
注意！Ph.D.、MASTER STUDENTS、ALUMNI、UNGRADUATED STUDENTS各自有不同的縮放方式，<br>
因此 div 的 class 會有所不同，請選擇相同的學位的區塊複製並修改！





## Push 至 github
1. 提交你的更改：
    ```bash
    git add .
    git commit -m "更新網站內容"
    ```

2. 將更改推送到 GitHub：
    ```bash
    git push origin main
    ```
