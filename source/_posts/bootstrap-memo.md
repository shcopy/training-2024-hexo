---
title: Bootstrap 常用語法筆記
date: 2024-05-30 11:05:40
tags:
---


Bootstrap 常用語法筆記
===

## RWD 網頁寬度範圍

|    設計稿寬度    |  判斷範圍 | CSS 設定寬度 | 
| -------------- | -------- | ---------- | 
| <= 575px       | <  575px |  auto  |
| 575px ~  768px | >  575px |  540px |
| 768px ~  992px | >  768px |  720px |
| 992px ~ 1200px | >  992px |  960px |
|1200px ~ 1400px | > 1200px | 1140px |
|1400px ~ n      | > 1400px | 1320px |

---

## 網格選項
|    Breakpoint     | Class infix | Dimensions |
| ----------------- | ----------- | ---------- |
| X-Small           | None        |   <576px   |
| Small             | sm          |	  ≥576px   |
| Medium            | md          |	  ≥768px   |
| Large             | lg          |	  ≥992px   |
| Extra large       | xl          |	  ≥1200px  |
| Extra extra large | xxl         |	  ≥1400px  |
- Bootstrap 預設默認六個斷點（有時候會稱之為網格），主要用於建立響應式開發。如果您是使用我們的 Sass 原始碼，則可以自定義這些斷點。

---

1. 格線系統結構由外而內為 .container, .row, .col-xx。
2. class="row" 內層建議使用 class-"col-xx" 避免增加其它的結構，將導致結構不穩定。
3. 最外層，在幫它補一個 class="container"、class="container-fluid"。
```htmlembedded=
// 範例1：
// 對於網頁內容寬度的階段美感都很要求且需要最大寬度限制可用 container
<div class="container">
    <div class="row">
        <div class="col-xx"></div>
    </div>                            
</div>

// 範例2：
// 如果網頁內容不需要嚴謹的定義最大寬度可以使用 container-fluid
<div class="container-fluid">
    <div class="row">
        <div class="col-xx"></div>
    </div>                            
</div>                                                   
```
---
## 問與答：
1. **Q:格線系統構構，何者為建議寫法?**
   A: .container > .row > .col-*
```htmlembedded=
// 範例：
<div class="container">
    <div class="row">
        <div class="col"></div>
        <div class="col"></div>
        <div class="col"></div>
    </div>
</div>
```
---
2. **Q: 格式系統中預設一列為幾欄?** 
   A: 12欄
---
3. **Q:使用三大欄的方式進行排列，需要用欄寬?** 
   A: .col-4
```htmlembedded=
// 範例：
<div class="container">
    <div class="row">
        <div class="col-4"></div>
        <div class="col-4"></div>
        <div class="col-4"></div>
    </div>
</div>  
```
---
4. **Q: 請問如果要行動版為單欄，桌面版（lg）為三大欄，請問該使用哪一組樣式套用在欄上?**  
  A: .col-lg-4
```htmlembedded=
// 範例：
<div class="container">
    <div class="row">
        <div class="col-lg-4"></div>
        <div class="col-lg-4"></div>
        <div class="col-lg-4"></div>
    </div>
</div> 
```
---
5. **呈現為"左右兩大欄"的結構範例**
```htmlembedded=
<div class="row row-cols-2">
     <div class="col"></div>
	 <div class="col"></div>
	 <div class="col"></div>
   </div>
```  
---
6. **Q:如果要移除水平 gutter 的間距，.row 要套用哪一組樣式？**  
   A:"gx-0" 
```htmlembedded=
// 範例
<div class="row gx-0">
 <div class="col"></div>
 <div class="col"></div>
 <div class="col"></div>
</div>
```
---
7. **Q: 請問 d-sm-flex 可以得到什麼樣的效果？**
   A: 預設不改變, sm 以上的裝置套用 display: flex
---
8. **Q: 如果想要在 lg 尺寸以上顯示元素，lg 以下則是隱藏可以使用哪一個語法？**
   A: d-lg-block d-none
---
9. **Q: 文字要靠右對齊，該使用哪一個 class 呢？**
   A: text-end
---
10. **Q: 當連結要套用色彩，並使它在 hover 時也能套用色彩，會使用？**
   A: link-primary
```htmlembedded=
// 範例
// 連結顏色 (Colored links) Hover 狀態的彩色連結
<a href="#" class="link-primary">Primary link</a>
<a href="#" class="link-secondary">Secondary link</a>
<a href="#" class="link-success">Success link</a>
<a href="#" class="link-danger">Danger link</a>
<a href="#" class="link-warning">Warning link</a>
<a href="#" class="link-info">Info link</a>
<a href="#" class="link-light">Light link</a>
<a href="#" class="link-dark">Dark link</a
```
---
11. **Q: 外層為 display: flex 時，內層元素要做到交錯軸置中，會使用哪一個 class？**
   A: align-self-center 
```htmlembedded=
// 範例
// 在 bootstrap 環境可直接使用 align-self-center
<div class="align-self-center">Aligned flex item</div>
```
---
## Bootstrap 工具元件
### 按鈕元件
- 結構與樣式分離
```htmlembedded=
<button type="button" class="btn btn-primary">我是按鈕</button>
結構: .btn           => 這是按鈕(邊距, 圓角) 
樣式: .btn-primary   => 基本色彩, 
     .active        => hover, focus... 樣式
     :hover
      btn btn-primary =>
```
### 元件組合規則
#### 元件模組大致包含以下規則
- 模組 (button, modal, pagination)
- 主題 (theme colors-> primary, danger...)
- 樣式 (size, style) => 例: 按鈕有大有小, 邊線樣式
- 狀態 (active, disabled)
          按鈕
- 模組 { 模組 }
- 主題 { 模組 } - { 主題 }
- 樣式 { 模組 } - { 樣式 }, { 通用類別 }
- 狀態 { 狀態 }
- 
---

```htmlembedded
// 範例
<div class="btn btn-primary btn-sm disabled"></div>
            結構    主題       樣式    狀態
```
| 結構  |     主題      |  樣式   |   狀態    | 
| ---- |---------------| -------|----------| 
| -btn | -btn-primary  | btn-sm | -active  | 
|      | -             |        |          |

- Bootstrap 中會加入大量的 Class 來套用樣式，每一個 Class 都代表了部分的結構、樣式、狀態等等…

Components
Accordion
Alerts
Badge
Breadcrumb
Buttons
Button group
Card
Carousel
Close button
Collapse
Dropdowns
List group
Modal
Navbar
Navs & tabs
Offcanvas
Pagination
Placeholders
Popovers
Progress
Scrollspy
Spinners
Toasts
Tooltips



