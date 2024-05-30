<img alt="2024-camp" src="https://firebasestorage.googleapis.com/v0/b/hexschool-courses.appspot.com/o/hex-website%2Fblog%2F1710986781813-engineer-camp.png?alt=media&token=536bc802-b2b7-4778-8887-2017e88853d7">

# hexschool - Hexo
此為套用了主題 `hexschool` 的完整 Hexo 専案，開箱即用

![Required Node version](https://img.shields.io/node/v/hexo)
[![Discord Chat](https://img.shields.io/badge/chat-on%20discord-7289da.svg)](https://discord.gg/822N5Ycttt)


## 快速開始

**專案設置（Project setup）**

將專案複製到本地端
```sh
$ git clone git@github.com:hexschool/2024-camp-hexo.git
```

基礎套件安裝
```sh
$ cd 2024-camp-hexo
$ npm install
```

**執行專案（Start the server）**
```sh
$ hexo server
```

**新增文章（Create a new post）**，建議以 Kebab case 進行命名。例如：your-post
```sh
$ hexo new post <your-post-name>
```

**生成靜態檔案（Generate static files）**
```sh
$ hexo generate
```

**清除靜態檔案（Clear static files）**
```sh
$ hexo clean
```

## [一鍵部屬](https://hexo.io/zh-tw/docs/github-pages#%E4%B8%80%E9%8D%B5%E9%83%A8%E5%B1%AC)
- 以下教學改編自 [一鍵部署 .](https://hexo.io/docs/one-command-deployment)

- 安裝 [hexo-deployer-git.](https://github.com/hexojs/hexo-deployer-git)
```sh
npm install hexo-deployer-git --save
```

- 清空 _config.yml 的現有資料，並新增以下組態:
```sh
deploy:
  type: git
  repo: https://github.com/<username>/<project>
  # example, https://github.com/hexojs/hexojs.github.io
  branch: gh-pages
```
- 執行 hexo clean && hexo deploy 。
- 瀏覽 <GitHub 用戶名>.github.io 檢查你的網站能否運作。



## 常見問題

### Q：如何在文章中加入圖片

**Step 1: 將圖片存放至 `/source/images`**

**Step 2: 在文章中以 `![](/images/your-image.png)` 方式載入**

### Q：如何新增 / 修改 CSS 樣式

在 `/themes/hexschool/source/scss/_custom.scss` 中新增

### Q：如何編譯 SCSS 檔案

**Step 1: 安裝 [Live Sass Compiler](https://marketplace.visualstudio.com/items?itemName=ritwickdey.live-sass)**（若已安裝可略過此步驟）

**Step 2: 點擊 VS Code 下方的 `Watch Sass` 按鈕**
![](https://i.imgur.com/4z3IMP6.png)

**Step 3: 點擊 `/themes/hexschool/source/scss/all.scss` 並按下儲存快捷鍵**

MacOS 使用 cmd + s，Windows 使用 ctrl + s


**Note: 編譯完成的檔案會出現在 `/themes/hexschool/source/css/all.min.css`**

### Q: Hexo d -g 指令錯誤 Deployer not found
- 當在使用 hexo 建置屬於自己的 Blog 時，發生 `Deploy not found : git` 的解決方式

- 解決方法: 由於缺少 hexo-deployer-git 套件，在當前目錄安裝套件即可

```sh
npm install hexo-deployer-git --save
```

- 接下來再使用 `hexo d -g` 就可以成功推送了！ 很簡單對巴~

[參考來源](https://blog.csdn.net/qq_21808961/article/details/84476504)



## 更多資訊
- [hexschool 主題相關設定與介紹](https://github.com/hexschool/2024-camp-hexo/blob/main/themes/hexschool/README.md)
- [Hexo 相關指令](https://hexo.io/zh-tw/docs/commands)





---

