---
title: AGENTS.md

---

# AGENTS.md

## 1. Project Overview

### Project Name
**Retro Study Notes**

### Project Purpose
Retro Study Notes 是一個用來整理研究所課程、論文閱讀與技術筆記的靜態網站。

網站的主要目標是建立一套固定且可重複使用的內容結構與視覺規則，讓之後新增筆記時，不需要重新說明網站應該長什麼樣子，也不需要每次重新決定檔案位置、命名方式與頁面格式。
AI 在修改或新增內容前，應先閱讀本文件，並依照本文件的規則維持整個專案的一致性。

---

## 2. Project Goals

本專案希望達成以下目標：

1. 將研究所課程與技術筆記整理成容易瀏覽的網頁。
2. 每篇筆記使用一致的頁面結構。
3. 所有頁面共用同一套視覺設計。
4. 新增內容時能快速建立新頁面。
5. 讓 AI 可以依照 `AGENTS.md` 自動延伸網站，而不需要重新定義專案規則。
6. 保持專案結構簡單，優先使用 HTML 與 CSS，不引入沒有必要的複雜框架。

---

## 3. Project Structure

專案基本結構如下：

```text
retro-study-notes/
│
├── index.html
├── styles.css
├── AGENTS.md
│
├── pages/
│   ├── anomaly-detection.html
│   ├── machine-learning.html
│   └── dsp.html
│
└── assets/
    ├── images/
    └── icons/
```

### File Responsibilities

#### `index.html`
網站首頁。

主要功能：

- 顯示網站標題與簡介
- 顯示所有筆記主題卡片
- 提供各筆記頁面的入口
- 新增筆記頁面後，需要同步更新首頁

#### `styles.css`
所有網站共用樣式。

所有頁面都應引用這個檔案。

除非有特殊需求，禁止在 HTML 中新增大量 inline CSS。

#### `pages/`
存放所有筆記頁面。

每一個主要主題使用一個獨立 HTML 檔案。

#### `assets/images/`
存放網站使用的圖片、圖表或截圖。

#### `assets/icons/`
存放介面裝飾或功能 icon。

---

## 4. File Naming Rules

所有檔案名稱使用：

**lowercase + kebab-case**

例如：

```text
anomaly-detection.html
machine-learning-basics.html
digital-signal-processing.html
foundation-models.html
```

不要使用：

```text
AnomalyDetection.html
Machine Learning.html
chapter_01.html
newpage.html
```

檔名應能直接反映頁面內容。

---

## 5. Website Design System

網站整體採用 **Retro Desktop / Y2K Study Notes** 風格。

視覺應保持低飽和、乾淨、易閱讀。

### Main Visual Style

主要元素：

- 淡藍色格紋背景
- 奶油白內容視窗
- 鼠尾草綠視窗標題列
- 深灰藍主要文字
- 低飽和粉色作為少量強調色
- 少量復古桌面 icon 作為背景裝飾
- 視窗具有簡單硬陰影
- 避免大量圓角
- 避免過度現代化的玻璃擬態或漸層效果

### Suggested Colors

```text
Desktop Background: #DCECF0
Grid Line:          #B9D2D8

Paper / Window:     #FFFAF2
Light Paper:        #FFFDF8

Main Text:          #34434A
Secondary Text:     #657B80

Sage Green:         #8B9A8F
Dark Sage:          #65776C

Pink Accent:        #F4C7CF
Blue Gray:          #8A9BA8
```

若需要新增顏色，應優先選擇低飽和色系，並維持整體一致性。

---

## 6. Typography

中文文字優先使用容易閱讀的字體，例如：

```css
"Noto Sans TC", "Microsoft JhengHei", sans-serif
```

視窗標題、系統文字或裝飾文字可以使用 monospace，例如：

```css
"Courier New", monospace
```

原則：

- 內文優先考慮閱讀性
- 不要將所有中文文字改成 pixel font
- 復古風格主要透過標題列、框線、icon 與版面呈現

---

## 7. Homepage Structure

首頁應包含以下內容：

### 7.1 Header

包含：

- 網站名稱
- 簡短網站介紹
- 可使用復古視窗標題列

### 7.2 Notes Section

使用卡片呈現不同筆記。

每張卡片至少包含：

- 主題名稱
- 簡短說明
- 分類
- 前往筆記頁面的連結

例如：

```text
Anomaly Detection

Visual anomaly detection、
MVTec AD、VisA 與基礎方法整理。

Category: Computer Vision
```

### 7.3 Optional Categories

- 每篇筆記都必須指定一個 category。
- Category 不限制固定清單，可依內容自行新增。
- Category 名稱應簡短、清楚，建議 1 到 3 個英文單字。
- 相同概念應盡量沿用既有 category，避免重複分類。

Examples:
Computer Vision
Machine Learning
Signal Processing
Algorithms
Paper Reading
Research Notes
Deep Learning
Medical Imaging

---

## 8. Note Page Structure

每一篇筆記頁面應盡量遵守相同結構。

基本模板：

```text
Title

Overview

Key Concepts

Important Terms

Detailed Notes

My Notes

References
```

---

### 8.1 Title

顯示主題名稱。

例如：

```text
Anomaly Detection
```

可附上簡短副標題。

---

### 8.2 Overview

簡短說明：

- 這個主題在講什麼
- 為什麼重要
- 這篇筆記會涵蓋哪些內容

避免寫得過長。

---

### 8.3 Key Concepts

整理核心概念。

適合使用：

- 小標題
- 條列
- 簡單表格

不要把整段教材直接貼進來。

---

### 8.4 Important Terms

整理重要名詞與簡短定義。

例如：

```text
Anomaly:
與正常資料分布明顯不同的樣本。

Normality Modeling:
利用正常資料建立正常模式，再判斷測試樣本是否偏離此模式。
```

---

### 8.5 Detailed Notes

放置較完整的課程、論文或技術內容。

如果內容很多，可以拆成多個小節。

---

### 8.6 My Notes

用來放：

- 個人理解
- 容易混淆的地方
- 上課補充
- 自己整理的比較
- 研究上的想法

此區塊應與一般教材內容有所區分。

---

### 8.7 References

列出內容來源。

例如：

- 課程講義
- 論文
- 官方文件
- 教材
- 網站

AI 不可以虛構不存在的 reference。

若沒有來源資訊，應標示：

```text
Source not provided.
```

---

## 9. Content Writing Rules

所有網站內容優先使用 **繁體中文與台灣常用語**。

技術名詞可以保留英文，例如：

- Anomaly Detection
- Feature Extraction
- Foundation Model
- Frequency Response

第一次出現時可以提供中文說明。

### Writing Style

內容應：

- 清楚
- 簡潔
- 有結構
- 避免過度口語
- 避免不必要的長篇敘述
- 技術內容需優先維持正確性

不要為了讓內容看起來完整而自行補充沒有來源支持的事實。

---

## 10. ## Rules for Adding a New Note from Course Materials

當使用者希望新增一篇課程筆記時，應優先以使用者提供的教材檔案作為主要內容來源。

支援的主要輸入包含：

- 課程教材 PDF
- 講義 PDF
- 課程投影片
- 使用者提供的課堂筆記
- 其他明確指定為本次筆記來源的檔案

AI 必須先閱讀 `AGENTS.md`，再讀取教材內容，最後依照本專案既有的頁面結構與設計規範建立新的筆記頁面。

完整流程如下：

`Read AGENTS.md → Read Course Material → Identify Topic & Category → Extract & Organize Content → Build Note Page → Update Homepage → Validate`

---

### Step 1：閱讀專案規則

開始新增內容以前，AI 必須先閱讀 `AGENTS.md`。

確認以下項目：

- 專案目的
- 網站 Design System
- 檔案結構
- 檔案命名規則
- Note Page Structure
- Content Writing Rules
- HTML / CSS Rules
- AI Development Rules
- Definition of Done

後續所有新增與修改都必須遵守這些規則。

---

### Step 2：讀取課程教材

AI 必須完整理解使用者提供的教材，再開始整理內容。

教材是本次筆記的主要知識來源。

整理時必須遵守：

1. 只使用教材實際提供的內容。
2. 不自行加入教材沒有出現的知識、定義、範例或推論。
3. 不自行修正教材中的理論、公式或敘述。
4. 若教材某部分資訊不足，應標示「教材未說明」或保留該部分空白。
5. 可以重新排序內容，以提升閱讀性。
6. 可以濃縮重複內容。
7. 可以將分散在不同頁面的相關概念整合在一起。
8. 可以將教材內容重新整理成條列、表格或小節。
9. 整理後不可改變教材原本的概念與語意。
10. 專有名詞、公式、符號與技術名稱應盡量保留教材原本的寫法。

若使用者另外要求補充、查證或延伸教材內容，必須將「教材內容」與「額外補充內容」明確區分。

---

### Step 3：確認筆記主題

根據使用者指定的主題與教材內容，決定新頁面的主要 Title。

例如：

```text
Sorting Algorithms
Frequency Response
Bayesian Decision Theory
Anomaly Detection
```

若使用者已經指定主題，直接使用該主題。

若使用者只提供教材而沒有指定主題，可以根據教材的主要內容建立清楚且簡潔的頁面標題。

不要使用過於模糊的名稱，例如：

```text
Week 3
Lecture Notes
New Notes
Chapter
```

除非教材本身就是依週次或章節作為主要識別方式。

---

### Step 4：確認或建立 Category

每篇筆記必須具有一個 Category。

若使用者已指定 Category，優先使用使用者提供的名稱。

若使用者沒有指定：

1. 查看目前網站已有的 Category。
2. 優先使用語意最接近的既有 Category。
3. 若現有分類都不適合，再建立新的 Category。

Category 可以依內容自由新增，不限制固定清單。

命名原則：

- 名稱簡短
- 能清楚代表技術領域
- 優先使用 Title Case
- 同一概念應沿用既有名稱
- 避免建立語意重複的分類

例如：

```text
Algorithms
Computer Vision
Machine Learning
Digital Signal Processing
Medical Imaging
Generative AI
Bayesian Methods
Paper Reading
```

應避免同時存在：

```text
Computer Vision
CV
Visual AI
Vision
```

若這些名稱實際代表相同領域，應統一使用既有 Category。

---

### Step 5：決定檔名

依照專案 File Naming Rules 建立檔名。

檔名必須：

- 全部使用小寫
- 使用 kebab-case
- 能反映內容主題
- 放入 `pages/` 目錄

例如：

```text
sorting-algorithms.html
frequency-response.html
bayesian-decision-theory.html
anomaly-detection.html
```

避免：

```text
SortingAlgorithms.html
week3.html
new-page.html
note1.html
```

---

### Step 6：分析與整理教材內容

開始建立 HTML 前，先將教材整理成適合閱讀的知識結構。

優先辨識：

- 章節主題
- 核心概念
- 定義
- 重要術語
- 公式
- 演算法
- 流程
- 範例
- 圖表
- 教材中特別強調的內容
- 各概念之間的關係

整理時可以將教材原本按照投影片順序呈現的內容，重新組織成較適合筆記閱讀的架構。

例如教材原本可能依序出現：

```text
Definition
Example
Another Definition
Comparison
Another Example
```

整理後可以調整成：

```text
Concept A
    Definition
    Example

Concept B
    Definition
    Example

Comparison
```

重新組織的目的是提升理解與閱讀效率，但不得改變教材原意。

---

### Step 7：依固定 Note Page Structure 建立內容

每篇新筆記原則上使用以下結構：

```text
Title
Overview
Learning Objectives
Key Concepts
Important Terms
Detailed Notes
Examples / Figures
My Notes
References
```

可以依教材內容省略沒有資料的區塊，但不應自行補內容填滿版面。

---

#### Title

顯示本篇筆記主要主題。

同時標示：

- Category
- 必要時顯示教材章節資訊

---

#### Overview

根據教材內容簡短說明：

- 這個主題主要在討論什麼
- 本篇筆記涵蓋哪些範圍

Overview 應以教材內容為依據。

---

#### Learning Objectives

若教材有明確學習目標，整理並放入此區。

若教材沒有提供 Learning Objectives，可以：

- 根據教材章節標題整理非常直接的學習範圍
- 或省略此區塊

不要自行推測老師的教學目標。

---

#### Key Concepts

整理教材中最重要的核心概念。

適合使用：

- 條列
- 小標題
- 比較表格
- 簡單流程

每個概念都必須能在教材中找到依據。

---

#### Important Terms

整理教材中的重要名詞與定義。

例如：

```text
Sampling Frequency
Nyquist Rate
Aliasing
```

定義應忠於教材的說明方式。

若教材只提到名詞但沒有定義，不要自行補充完整教科書定義。

---

#### Detailed Notes

這是筆記的主要內容區域。

應依教材內容重新整理成清楚的小節。

可以包含：

- 理論說明
- 推導
- 公式
- 演算法流程
- 方法比較
- 注意事項
- 教材中的重要補充

如果教材內容很多，可以增加多層標題。

---

#### Examples / Figures

若教材包含：

- Example
- Exercise
- Case Study
- Figure
- Flowchart
- Table

可以整理於此區。

若無法直接使用原始圖像，可以以文字描述圖表所表達的內容。

不得自行創造教材沒有提供的 Example。

---

#### My Notes

此區域保留給使用者的個人理解與補充。

AI 預設不得自行假裝使用者撰寫心得。

若使用者沒有提供個人筆記，可以顯示：

```text
目前尚未加入個人筆記。
```

或保留該區塊等待後續新增。

---

#### References

必須記錄本頁內容來源。

若主要來源是使用者提供的 PDF，可以列出：

```text
Course Material:
[教材檔名]
```

若教材本身包含正式引用文獻，可以保留教材中的 reference。

AI 不得自行虛構論文、作者、年份或 DOI。

---

### Step 8：建立 HTML 頁面

完成內容整理後，在 `pages/` 中建立新的 HTML。

必須：

- 使用現有筆記頁面的 HTML 結構
- 使用既有 CSS class
- 引用共用 `styles.css`
- 維持 Retro Desktop / Y2K Study Notes Design System
- 保持與其他頁面一致的 navigation
- 提供返回首頁的連結

CSS 路徑通常為：

```html
<link rel="stylesheet" href="../styles.css">
```

若既有元件已經可以完成需求，不要建立功能重複的新 class。

---

### Step 9：更新首頁

建立新筆記頁面後，必須同步修改 `index.html`。

新增對應的 Note Card。

卡片至少包含：

- Title
- Category
- 簡短內容說明
- 新頁面的正確連結

例如：

```text
Category:
Algorithms

Title:
Sorting Algorithms

Description:
整理教材中的排序概念、演算法與比較。

Link:
pages/sorting-algorithms.html
```

首頁卡片內容同樣應以教材實際內容為依據。

首頁中的 Note Card 必須依照「是否已有實際筆記頁面」排序。

排序原則如下：

1. **Available Notes**
   - 已經建立對應 HTML 頁面的筆記必須排列在前面。
   - 這些卡片應提供可以正常開啟的連結。
   - 按鈕文字使用 `OPEN NOTE`。

2. **Coming Soon Notes**
   - 尚未建立實際頁面的預留主題統一排列在 Available Notes 之後。
   - 按鈕文字使用 `COMING SOON`。
   - 不應提供無效連結。

3. **新增完成筆記時**
   - 若首頁已經存在相同主題的 `COMING SOON` 卡片，應直接將該卡片更新為可開啟的 Note Card。
   - 不要另外新增重複卡片。
   - 更新完成後，將該卡片移動至 Available Notes 區域。

4. **新增全新主題時**
   - 如果首頁沒有相同主題的預留卡片，建立新的 Note Card。
   - 新卡片應放在最後一個 Available Note 之後、第一個 `COMING SOON` 卡片之前。

5. **排序優先順序**
   - 第一優先：頁面是否已完成。
   - 第二優先：保留既有 Available Notes 的順序。
   - 不需要為了新增一篇筆記重新排序所有既有筆記。

首頁結構應維持：

```text
Available Notes
[ OPEN NOTE ]
[ OPEN NOTE ]
[ OPEN NOTE ]

Coming Soon
[ COMING SOON ]
[ COMING SOON ]
```

新增或修改首頁後，AI 必須確認：

- [ ] 所有 `OPEN NOTE` 卡片都排在 `COMING SOON` 之前
- [ ] 沒有同一主題的重複卡片
- [ ] 所有可開啟卡片的連結正確
- [ ] `COMING SOON` 卡片沒有無效連結

---

### Step 10：檢查內容忠實度

完成頁面後，再次與教材比對。

確認：

- 沒有加入教材未提供的重要知識
- 沒有改變教材原本概念
- 沒有遺漏教材中明顯重要的主題
- 公式與符號沒有被錯誤修改
- 技術名詞使用與教材一致
- 整理後的分類仍符合教材內容

若發現整理過程中加入推測內容，應移除或明確標示。

---

### Step 11：檢查網站結構

確認：

- 新 HTML 位於正確資料夾
- 檔名符合 kebab-case
- CSS 路徑正確
- 首頁連結可以開啟新頁面
- 返回首頁連結正常
- 沒有破壞其他既有頁面
- 沒有建立重複 CSS
- 頁面風格符合 Design System

---

### Step 12：完成條件

新增筆記完成前，AI 必須確認：

- [ ] 已先閱讀 `AGENTS.md`
- [ ] 已讀取使用者提供的教材
- [ ] 筆記內容以教材為主要來源
- [ ] 沒有自行補入未提供的技術內容
- [ ] Topic 清楚
- [ ] Category 正確
- [ ] 檔名符合 kebab-case
- [ ] 頁面位於 `pages/`
- [ ] 使用既有 Note Page Structure
- [ ] 使用共用 `styles.css`
- [ ] 已更新 `index.html`
- [ ] 首頁卡片連結正確
- [ ] 頁面可以正常瀏覽
- [ ] References 有標示教材來源
- [ ] 沒有虛構 Reference
- [ ] 沒有破壞其他頁面
- [ ] 整體風格符合 Design System

---

## Course Material Grounding Principle

當使用者提供教材時：

> **教材內容是筆記的主要事實來源。AI 的工作是提取、濃縮、重新組織與呈現教材內容，並維持原始概念與技術資訊的忠實度。**

AI 可以改善：

- 結構
- 排版
- 可讀性
- 重複內容
- 概念之間的組織方式

AI 不應自行增加教材沒有提供的：

- 理論
- 定義
- 公式
- 範例
- 結論
- Reference

若使用者明確要求額外補充或延伸，再另外加入，並清楚標示哪些內容來自教材、哪些屬於額外補充。
---

## 11. Rules for Editing Existing Content

修改既有頁面時：

1. 優先保留既有內容與結構。
2. 只修改使用者要求的部分。
3. 不要自行刪除其他筆記。
4. 不要自行修改網站主色系。
5. 不要任意更改所有頁面的 layout。
6. 若修改共用 CSS，需要確認其他頁面是否受到影響。
7. 若改變檔名，需要同步修改所有連結。
8. 不要建立功能重複的新 CSS class。

---

## 12. HTML Rules

HTML 應保持語意清楚。

優先使用：

```html
<header>
<main>
<section>
<article>
<nav>
<footer>
```

避免大量無意義的巢狀 `<div>`。

每個頁面應包含：

```html
<!DOCTYPE html>
<html lang="zh-Hant">
```

並設定：

```html
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## 13. CSS Rules

所有共用樣式應集中於：

```text
styles.css
```

CSS 建議依照以下順序整理：

```text
1. Variables
2. Global
3. Desktop Background
4. Window System
5. Header
6. Navigation
7. Cards
8. Note Content
9. Buttons
10. Decorations
11. Responsive
```

如果多個元件使用相同顏色，優先建立 CSS variable。

例如：

```css
:root {
    --desktop: #DCECF0;
    --paper: #FFFAF2;
    --text: #34434A;
    --sage: #8B9A8F;
}
```

避免同一顏色在不同地方重複寫大量 hex code。

---

## 14. JavaScript Rules

目前專案以靜態網站為主。

若 HTML 與 CSS 已能完成需求，不需要加入 JavaScript。

可以使用 JavaScript 的情況包括：

- 搜尋
- 分類 filter
- 展開 / 收合
- 簡單互動

不要為簡單視覺效果引入大型 JavaScript framework。

---

## 15. Dependency Rules

目前專案不需要：

- React
- Vue
- Next.js
- Database
- Backend
- npm package

除非未來專案需求明確增加，否則維持純靜態網站。

---

## 16. AI Development Rules

AI 修改此專案時必須遵守：

1. 修改前先閱讀 `AGENTS.md`。
2. 優先使用既有 HTML 結構與 CSS class。
3. 不要為每個新頁面重新設計風格。
4. 不要加入使用者沒有要求的新功能。
5. 不要刪除既有內容。
6. 不要自行更改專案目錄結構。
7. 新增頁面後一定要更新首頁。
8. 修改共用 CSS 時要考慮其他頁面。
9. 優先維持簡單、可讀、可維護的程式碼。
10. 完成修改後檢查所有相對路徑是否正確。

---

## 17. Extension Strategy

當筆記數量增加時，可以依需求逐步增加：

- Category filter
- Keyword search
- Tags
- Related Notes
- Previous / Next navigation

新增功能時仍應保持：

- 靜態網站優先
- 共用元件優先
- 簡單實作優先
- 不破壞既有頁面

只有當目前結構確實不足以支援需求時，才考慮較大型的技術改動。

---

## 18. Definition of Done

新增或修改內容完成前，AI 應確認：

- [ ] 頁面可以正常開啟
- [ ] CSS 路徑正確
- [ ] 首頁連結正確
- [ ] 檔名符合 kebab-case
- [ ] 頁面風格符合 Design System
- [ ] 內容使用繁體中文
- [ ] 沒有不必要的 inline CSS
- [ ] 沒有破壞其他頁面
- [ ] 沒有虛構來源
- [ ] 已更新必要的導覽或首頁內容

---

## 19. Core Principle

本專案最重要的原則是：

> **新增內容時延伸既有系統，而不是重新設計整個網站。**

AI 應將 `AGENTS.md` 視為專案的長期開發規範。

當未來新增新的課程、論文或技術筆記時，只需要提供新的內容主題，AI 就應能依照這份文件建立符合既有風格與結構的新頁面。