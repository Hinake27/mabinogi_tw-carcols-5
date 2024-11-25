# 顏色匹配計算器

一個簡單且高效的網頁顏色匹配工具，可以幫助用戶在指定誤差範圍內（預設5）找到最接近的顏色組合。

## 功能特點

- 🎨 支持 RGB 和 HEX 顏色格式輸入
- 🔍 自動計算誤差範圍內的可能顏色組合
- 📊 即時顯示顏色差異值
- 💡 提供多個接近的顏色建議
- 📱 完全響應式設計
- ⚡ 極簡且高效的代碼結構

## 快速開始

1. 將專案克隆到本地：
```bash
git clone [repository-url]
```

2. 直接在瀏覽器中打開 `index.html` 文件即可使用

或者直接將以下代碼保存為 `.html` 文件：

```html
<!DOCTYPE html>
<html lang="zh-TW">
// ... [完整代碼]
</html>
```

## 使用說明

1. 輸入目標顏色：
   - 使用 RGB 值（0-255）
   - 或直接輸入 HEX 色碼（如：#FF0000）

2. 點擊「計算可能的顏色組合」按鈕

3. 查看建議列表：
   - 顯示最接近的5個顏色選項
   - 每個選項顯示 RGB 值、HEX 值和差異程度
   - 點擊任意建議可直接應用該顏色

## 技術細節

### 依賴項
- React 18.2.0
- ReactDOM 18.2.0
- Babel (用於JSX轉換)

### 核心邏輯

```javascript
// RGB 轉 HEX
const toHex = ({r,g,b}) => '#' + [r,g,b]
    .map(x => x.toString(16).padStart(2,'0'))
    .join('')
    .toUpperCase();

// 計算顏色差異
const calcDiff = (c1, c2) => ({
    r: Math.abs(c1.r - c2.r),
    g: Math.abs(c1.g - c2.g),
    b: Math.abs(c1.b - c2.b)
});
```

### CSS 變量

```css
:root {
    --primary: #1c4565;
    --border: #436279;
    --bg: #1a1a1a;
    --text: #fff;
    --shadow: #4a9eff;
    --p: clamp(8px, 2vw, 12px);
}
```

## 自定義設置

### 修改誤差範圍
在 `findMatches` 函數中修改 `range` 值：

```javascript
const range = 5; // 默認誤差範圍
```

### 修改建議數量
修改 `.slice(0,5)` 中的數字可改變顯示的建議數量：

```javascript
.slice(0,5) // 顯示前5個建議
```

## 瀏覽器支持

- ✅ Chrome / Edge (最新版本)
- ✅ Firefox (最新版本)
- ✅ Safari (最新版本)
- ✅ 移動端瀏覽器

## 性能優化

- 使用 CSS 變量實現主題統一
- 最小化重排重繪
- 優化事件處理
- 簡化 DOM 結構
- 使用 React 高效更新機制

## 待優化項目

- [ ] 添加顏色預設值
- [ ] 實現撤銷/重做功能
- [ ] 添加顏色歷史記錄
- [ ] 支持更多顏色格式（HSL等）
- [ ] 添加鍵盤快捷鍵

## 貢獻指南

1. Fork 本專案
2. 創建新的功能分支
3. 提交更改
4. 發起 Pull Request

## 授權協議

MIT License

## 作者Sorina

[Sorina]

## 更新日誌

### v1.0.0 (2024-01-01)
- 初始版本發布
- 基礎顏色匹配功能
- 響應式設計實現
