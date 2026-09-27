# Simon Game

一款使用 HTML、CSS、JavaScript 與 jQuery 製作的 Simon 記憶遊戲。玩家需要依照畫面提示，按照正確順序點擊四色按鈕；每通過一關，系統就會在原本的序列後新增一個顏色，逐步考驗玩家的記憶力。

遊戲連結: https://xdewdayx.github.io/SIMON-GAME/

## 遊戲特色

- 隨機產生紅、藍、綠、黃四色序列
- 隨關卡增加逐步延長記憶序列
- 按鈕動畫與對應音效回饋
- 即時檢查玩家輸入
- 答錯時顯示 Game Over 效果，並可重新開始

## 遊戲方式

1. 開啟遊戲後，按下鍵盤上的任意按鍵開始。
2. 觀察閃爍的顏色並記住順序。
3. 使用滑鼠依照相同順序點擊按鈕。
4. 輸入正確後會進入下一關，系統會在既有序列後新增一個顏色。
5. 任一顏色點錯即結束遊戲；再次按下任意鍵即可重新挑戰。

## 快速開始

本專案是純前端靜態網站，不需要安裝相依套件或執行建置。

### 直接開啟

下載或複製專案後，直接使用瀏覽器開啟 `index.html`。

```bash
git clone https://github.com/xDEWDAYx/SIMON-GAME.git
cd SIMON-GAME
```

### 使用本機伺服器

若電腦已安裝 Python，也可以在專案目錄執行：

```bash
python -m http.server 8000
```

接著前往 [http://localhost:8000](http://localhost:8000)。

> 頁面會從 CDN 載入 jQuery 與 Google Fonts，首次載入時需要網路連線。

## 使用技術

- HTML5：頁面與遊戲按鈕結構
- CSS3：版面、配色、按壓與失敗動畫
- JavaScript：遊戲狀態、隨機序列與答案判定
- jQuery 3.7.1：事件監聽、DOM 操作與動畫效果
- HTML Audio：播放按鈕及答錯音效

## 專案結構

```text
SIMON-GAME/
├── index.html       # 遊戲頁面
├── styles.css       # 視覺樣式與互動狀態
├── game.js          # 遊戲邏輯
└── sounds/          # 四色按鈕與答錯音效
    ├── blue.mp3
    ├── green.mp3
    ├── red.mp3
    ├── yellow.mp3
    └── wrong.mp3
```

## 核心流程

1. `nextSequence()` 隨機選擇顏色，加入系統序列並播放提示。
2. 玩家點擊按鈕後，選擇會被記錄至玩家序列。
3. `checkAnswer()` 逐次比對玩家輸入與系統序列。
4. 整組輸入正確時進入下一關；輸入錯誤時播放失敗效果並重設遊戲。
