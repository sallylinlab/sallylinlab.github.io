# 網站更新教學(持續更新中)

## 更新 News 頁面
在 news.html 中，找到以下程式碼：
```
<thead>
  <tr><th>Date</th><th>News</th></tr>
</thead>
<tbody>
```
將內容新增至 tbody 中，最新的 news 更新在最上面。<br>
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
使用 <tr> 標籤新增一個 row ，並在此 row 中使用 <td> 標籤增加一個 column ，
範例程式碼如下：
```
<tr>
  <td>
    <div class="">
      <a type="button"data-bs-toggle="modal"
          data-bs-target="#文章互動式窗的ID">
        <h4 class="p-0 m-0">ARTICLE TITLE</h4>
        <p class="p-0 m-0">In JOURNAL NAME, 20XX</p>
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
點擊文章標題會出現一互動視窗，為該文章的內容，<br>
因此要更改參數 data-bs-target，文章互動視窗的 ID 命名規則為"文章名稱"。
```
<a type="button"data-bs-toggle="modal"
          data-bs-target="#article_title">
```
另外點擊 citation 圖示也會出現一互動視窗，可讓使用者快速複製 citation 內容，<br>
因此要更改參數 data-bs-target，citation 互動視窗的 ID 命名規則為"文章名稱_cite"。
```
&nbsp&nbsp<a class="link-dark" type="button" data-bs-toggle="modal" data-bs-target="article_title_cite"><i class="fa-2x fa-solid fa-quote-left"></i></a>
```

## 更新 Pics 頁面
## 更新 Members 頁面






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
