# 圖片使用說明

## 如何加入圖片

### 步驟 1：建立圖片資料夾

在 `user_manual` 目錄下建立 `images` 資料夾：

```
user_manual/
├── index.html
├── style.css
└── images/          ← 建立這個資料夾
    ├── product-overview.png
    ├── usage-scenario.png
    └── product-details.png
```

### 步驟 2：準備圖片

根據極簡黑白設計系統的要求，圖片應符合以下規範：

✅ **建議格式**：
- PNG 格式（支援透明背景）
- 黑白或灰階圖片
- 高解析度（建議至少 1200px 寬度）

✅ **圖片要求**：
- 透明背景（如適用）
- 黑白或灰階色調
- 不加陰影
- 不加圓角
- 不加裝飾框
- 簡潔、清晰的構圖

❌ **避免**：
- 彩色圖片（除非必要，但需轉為灰階）
- 圓角邊框
- 陰影效果
- 裝飾性邊框
- 過於複雜的構圖

### 步驟 3：將圖片放入資料夾

將準備好的圖片檔案放入 `user_manual/images/` 資料夾中。

### 步驟 4：更新 HTML

在 `index.html` 中找到圖片占位符，將註解替換為實際的 `<img>` 標籤：

#### 封面頁圖片（第 18-20 行）

**原本：**
```html
<div class="cover-image-placeholder">
    <div class="image-placeholder-text">產品示意圖</div>
</div>
```

**替換為：**
```html
<div class="cover-image-placeholder">
    <img src="images/product-overview.png" alt="自動安全警示車產品示意圖" class="cover-image">
</div>
```

#### 使用情境圖（第 35-37 行）

**原本：**
```html
<div class="image-block">
    <div class="image-placeholder-text">使用情境圖</div>
</div>
```

**替換為：**
```html
<div class="image-block">
    <img src="images/usage-scenario.png" alt="使用情境圖" class="content-image">
</div>
```

#### 產品細節圖（第 69-71 行）

**原本：**
```html
<div class="image-block">
    <div class="image-placeholder-text">產品細節圖</div>
</div>
```

**替換為：**
```html
<div class="image-block">
    <img src="images/product-details.png" alt="產品細節圖" class="content-image">
</div>
```

### 步驟 5：測試

在瀏覽器中開啟 `index.html`，確認圖片正確顯示。

## 圖片處理建議

### 使用 Photoshop / GIMP 轉換為黑白

1. 開啟圖片
2. 轉換為灰階：`影像 > 模式 > 灰階`
3. 調整對比度以符合極簡風格
4. 儲存為 PNG 格式

### 使用線上工具

- [Remove.bg](https://www.remove.bg/) - 移除背景
- [Photopea](https://www.photopea.com/) - 免費線上圖片編輯器
- [ImageMagick](https://imagemagick.org/) - 命令列工具

### 使用 ImageMagick 命令列轉換

```bash
# 轉換為灰階
convert input.jpg -colorspace Gray output.png

# 調整對比度
convert input.jpg -colorspace Gray -contrast-stretch 0%x100% output.png

# 移除背景（需要先處理）
convert input.png -fuzz 10% -transparent white output.png
```

## 圖片尺寸建議

- **封面圖片**：1200 x 675px（16:9 比例）
- **內容圖片**：1200 x 675px（16:9 比例）
- **手機版**：會自動調整為 4:3 比例

## 注意事項

1. 圖片檔案名稱使用小寫字母和連字號（kebab-case）
2. 確保 alt 文字描述清楚
3. 圖片檔案大小建議控制在 500KB 以內
4. 使用適當的圖片格式（PNG 用於透明背景，JPG 用於照片）

## 範例圖片結構

```
user_manual/
├── index.html
├── style.css
├── README_IMAGES.md
└── images/
    ├── product-overview.png      # 封面產品示意圖
    ├── usage-scenario.png         # 使用情境圖
    ├── product-details.png       # 產品細節圖
    └── texture-pattern.png       # 紋理圖（可選）
```
