# YouTube Layout

使用 HTML、CSS 與 Bootstrap 5 製作的 YouTube 首頁版面練習。

本作業以 YouTube 首頁為參考，練習網頁結構規劃、Flexbox、Bootstrap Grid、Responsive Web Design（RWD），以及 Font Awesome 圖示的整合。

---

## Demo

- GitHub Pages：待部署

---

## Preview

### Desktop

YouTube 風格的深色首頁介面，包含：

- Header 導覽列
- YouTube Logo
- 搜尋列
- 通知與使用者頭像
- 左側 Sidebar
- 影片分類按鈕
- 響應式影片卡片

### Mobile

螢幕寬度小於 768px 時：

- 隱藏左側 Sidebar
- 搜尋列移至 Header 下一行
- 影片卡片改為單欄排列
- Header 自動換行

---

## Features

### 1. Header

建立 YouTube 風格的頂部導覽列：

- Hamburger Menu
- YouTube Logo
- Search Bar
- Notification
- User Avatar

### 2. Sidebar Navigation

建立左側導覽選單，包含：

- 首頁
- 訂閱內容
- 個人中心
- 觀看紀錄
- 播放清單
- 稍後觀看
- 喜歡的影片
- 你的影片
- 已下載的內容
- 探索
- 音樂
- 電影
- 直播
- 遊戲
- 檢舉記錄

### 3. Video Cards

建立 YouTube 影片列表，每張影片卡片包含：

- 影片縮圖
- 頻道頭像
- 影片標題
- 頻道名稱
- 觀看次數
- 發布時間

點擊影片卡片後，可開啟對應的 YouTube 影片。

### 4. Category Navigation

建立影片分類按鈕：

- 全部
- 新聞
- 直播中
- Podcast
- 音樂
- 合輯
- 最新上傳
- 已觀看
- 讓你耳目一新

### 5. Responsive Web Design

使用 Bootstrap Grid 搭配 CSS Media Query 建立響應式影片列表：

| 螢幕尺寸 | Bootstrap Grid | 影片排列 |
| -------- | -------------- | -------- |
| Desktop  | `col-lg-4`     | 3 欄     |
| Tablet   | `col-md-6`     | 2 欄     |
| Mobile   | `col-12`       | 1 欄     |

---

## Layout Structure

```text
<body>
│
├── Header
│   ├── Menu
│   ├── YouTube Logo
│   ├── Search
│   └── Notification / User
│
└── Page Layout
    │
    ├── Sidebar
    │   ├── Navigation
    │   ├── Subscriptions
    │   ├── Personal Center
    │   └── Explore
    │
    └── Main Content
        ├── Category Buttons
        └── Video Grid
            ├── Video Card
            ├── Video Card
            ├── Video Card
            └── ...
```

---

## Tech Stack

- HTML5
- CSS3
- Bootstrap 5.3.3
- Font Awesome 6.5.0
- Flexbox
- CSS Media Query
- Responsive Web Design

---

## Technical Highlights

### Flexbox

Header 使用 Flexbox 進行水平排列：

```css
.left,
.middle,
.right {
  display: flex;
  align-items: center;
}
```

主要應用於：

- Header Layout
- Logo 與 Menu 排列
- Search Bar 排列
- Notification 與 User Avatar 排列

### Bootstrap Grid

影片列表使用 Bootstrap Grid：

```html
<div class="col-12 col-md-6 col-lg-4"></div>
```

透過不同 breakpoint 實現：

```text
Mobile
  ↓
1 column

Tablet
  ↓
2 columns

Desktop
  ↓
3 columns
```

### Aspect Ratio

影片縮圖使用 `aspect-ratio` 維持 16:9：

```css
.big {
  aspect-ratio: 16 / 9;
  object-fit: cover;
}
```

### Media Query

手機版使用 CSS Media Query 調整 Layout：

```css
@media (max-width: 768px) {
  aside {
    display: none;
  }

  .middle {
    order: 3;
    width: 100%;
  }
}
```

讓 Sidebar 在 Mobile 隱藏，並將搜尋列移至 Header 下一行。

### Hover Effect

Sidebar 選單加入 Hover 效果：

```css
aside a:hover {
  background: #333;
}
```

增加使用者操作時的視覺回饋。

---

## Project Structure

```text
youtube-layout/
├── index.html
├── style.css
└── README.md
```

---

## Learning Objectives

本次練習主要學習：

1. HTML 頁面結構與區塊拆分
2. Flexbox Layout
3. Bootstrap Grid
4. Responsive Web Design
5. CSS Media Query
6. `aspect-ratio` 圖片比例控制
7. Font Awesome Icon 整合
8. Sidebar Navigation
9. Responsive Video Card Layout
10. Git Branch 與 Pull Request 開發流程

---

## Learning Notes

透過這次練習，進一步理解：

- 如何將複雜頁面拆分成 Header、Sidebar 與 Main Content
- Flexbox 在實際網頁 Layout 中的應用
- Bootstrap Grid 如何快速建立響應式多欄 Layout
- CSS Media Query 如何處理 Mobile Layout
- `aspect-ratio` 如何維持影片縮圖比例
- 外部 CSS Framework 與 Icon Library 的基本整合方式
- 如何透過 Feature Branch 管理不同前端練習

---

## Future Improvements

目前本作業以 HTML / CSS Layout 練習為主，後續可進一步加入：

- [ ] Hamburger Menu 開關 Sidebar
- [ ] 搜尋功能
- [ ] Category Button Filter
- [ ] Video Card 動態資料
- [ ] 使用 JavaScript 產生影片列表
- [ ] 串接 API 取得影片資料
- [ ] Vue 3 Component 化
- [ ] TypeScript 型別管理
- [ ] GitHub Pages 部署

---

## Git Workflow

本作業使用獨立 Feature Branch 開發：

```text
main
 │
 └── feature/youtube-layout
        │
        ├── Develop
        ├── Commit
        ├── Push
        └── Pull Request
                 │
                 ▼
                main
```

此方式延續前一個 `feature/flexbox-practice` 練習，讓每個練習項目都可以透過獨立 Branch 開發，再經由 Pull Request 合併至 `main`。

---

## Author

Frontend Engineer Learning Project

持續透過實作練習 HTML、CSS、JavaScript、Vue 3、TypeScript 與前端工程實務。
