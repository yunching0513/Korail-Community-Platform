# Machan 3D模型

Machan - Korail Community Platform（Paraa設計，孟加拉達卡Korail聚落，2024年12月啟用）的互動3D量體模型。這是臺大「當代建築」課程亞太篇（critical regionalism）分組作業的研究用模型。

線上版：https://korail-community-platform.vercel.app

打開 `index.html` 就能看，不需要安裝任何東西。頁面右側第一張卡片是建築基本資料（設計者、地點、年代、規模、構造、資助與獎項）。

## 可以做什麼

- **三種顯示方式：** 圖解（用顏色區分構件）、素模（單色白模）、擬真（材質、天空、霧霾，傍晚會點亮燈籠）。
- **視角：** 鳥瞰、從空地看、站上平台、巷道側、正上方。
- **分解：** 把地面層、二樓平台、上層磚牆、鋼構遮棚逐層拉開。
- **基地：** 空地輪廓與指北針依Google Maps衛星影像量測（南北約50m、東西約28m；Plus Code：QCP6+FXJ，約北緯23.7862度、東經90.4124度）。
- **衛星影像底圖：** 圖層中可開啟Google Maps衛星影像截圖（`assets/site-satellite.jpg`，影像 ©2026 CNES / Airbus、Maxar Technologies，地圖資料 ©2026 Google），僅供教學研究參考；以圖上的20m比例尺對位，可能有數公尺偏差。
- **剖切：** 從面向空地的一側往巷道切入。
- **日照時間：** 依達卡（北緯23.8度）冬季估算，06:30至18:30。
- **模型提案：** 15×15×7cm的作業模型盒在五個比例尺下各取什麼：1:1材料（一皮磚，一個洞）、1:10局部特色（孔洞磚牆）、1:100建築物（中段剖出來）、1:500與1:1000城市尺度（空地和它的邊；低矮的紋理與遠方的高樓）。選一個比例尺，3D畫面會標出盒子的範圍，可以只顯示盒內，旁邊列出概念、做法、備案與待確認事項。
- **空間編號：** 13個位置，對應右側的說明。

## 這個模型的限制

這是依圖面與照片推估的量體模型，不是測繪。

- 各張圖的比例尺互相矛盾，換算出來的建築長度在25至31m之間。模型採用與官方面積332㎡最吻合的31m，寬約5m，最高約9m，高度再用照片裡的人物比例校正。
- 孔洞磚牆用貼圖示意，樓梯、內部隔間和平台邊緣的鋸齒形都簡化過。
- 周邊房屋、樹和遠方高樓只是示意，不代表實際位置。
- 配置圖上有畫、但照片裡看不到的兒童遊戲區、涼亭、階梯地景和瞭望塔，預設隱藏，是否已興建沒有查到。
- 擬真模式是瀏覽器即時算圖，磚、混凝土、泥土地和鐵皮屋頂的材質都是程式生成的，不是照片。

## 資料來源

- [Machan - Korail Community Platform / Paraa（ArchDaily）](https://www.archdaily.com/1182488/machan-korail-community-platform-paraa)：平面、剖面、立面、軸測圖，圖面Courtesy of Paraa，攝影City Syntax。
- [Machan_Korail Community Platform（Ammodo Architecture）](https://www.ammodo-architecture.org/projects/machankorail-community-platform)
- [Machan（Paraa）](https://www.paraa.org/projects/machan)

本專案沒有收錄任何原始圖面或照片，模型幾何是依上述資料重新建立的。建築設計的著作權屬於Paraa。

## 技術

單一HTML檔，使用 [three.js](https://threejs.org/) r128（由cdnjs與jsDelivr載入）。擬真與素模用到three.js範例中的SSAO與FXAA後製。需要支援WebGL的瀏覽器。

## 放到網路上

到這個repository的 Settings → Pages，Source選「Deploy from a branch」，Branch選 `main` 與 `/ (root)`，存檔後幾分鐘就會有網址。


## 擬真模式更新（2026-11-12）

- 六款本地透明 WebP 人物：AI 合成、非真實居民紀錄；在 22 個既有位置放置直立剪影，隨鏡頭水平轉向，支援遮擋、陰影與分解。圖解／素模保留幾何比例人；圖片載入失敗時也保留比例人。
- 增加磚面孔隙、混凝土／木紋與波紋鐵皮凹凸；降低鋼構飽和度、放大泥地紋理尺度，調整日照與曝光、減弱暗角。
- 初次開啟預設擬真，仍記住使用者切換的顯示方式。
- 人物資產在 `assets/resident-1.webp` 至 `resident-6.webp`，部署時須與 `index.html` 一起上傳。

- 2026-11-12晚：擬真模式的遠方高樓改為淡色半透明剪影，不再被霧染成地平線的橘色。

### 驗證範圍

JavaScript 語法通過；以 three.js r128 搭配模擬 renderer 執行初始化、三種模式、五個視角、六個比例選項、分解／剖切／日照事件，並檢查六張貼圖與 22 個人物剪影。預覽環境無法建立 WebGL context，因此尚未完成 GPU 畫面品質驗收，需在支援 WebGL 的實際瀏覽器確認。這仍是示意性的即時 3D 模型，不是實景攝影或測繪。

## 亞太四案3D模型（2026-11-13）

`cases.html`是同一門課亞太篇另外四個案例的互動量體模型，線上版：https://korail-community-platform.vercel.app/cases.html

- **案例：** AFER Hangang（Hyunjoon Yoo + Partners，首爾）、Hideout Leaf Villa（Pablo Luna Studio，峇里島）、The Inner Court House（Plus Idea Studio，越南藩朗）、Cordmark Miyota（Aida Atelier，長野御代田）。
- **功能：** 圖解與素模、五個視角、分解、剖切、日照時間（春秋分，依各案緯度）、空間編號說明、15×15×7cm模型盒在各比例尺下的範圍；「同比例尺比較」把四個模型排成一列，桃紅色線框是Machan的量體。
- **限制：** 全部依ArchDaily等來源的圖面與照片推估，不是測繪。AFER的露臺位置是示意；Leaf Villa的平面與立面比例尺互相矛盾，採用立面（約16m），方位未知；Inner Court的屋頂坡度與內庭尺寸為估計；Miyota的屋頂與地形簡化。各案的說明與來源連結在頁面右側的資料卡。
- 單一HTML檔，沒有圖片資產，不收錄任何原始圖面或照片。部署時須與`index.html`一起上傳。

## 英文版 English version（2026-11-13）

兩個頁面右上角都有「中文／English」切換。English: both pages have a language switch at the top right; add `?lang=en` to the address to open directly in English.

- 英文版連結：https://korail-community-platform.vercel.app/?lang=en 與 https://korail-community-platform.vercel.app/cases.html?lang=en
- 語言的決定順序：網址的`?lang=en`或`?lang=zh`，其次是上次的選擇（存在瀏覽器），最後依瀏覽器語言（中文瀏覽器顯示中文，其他顯示英文）。
- 做法：頁面本身維持中文，`index.html`與`cases.html`結尾各有一段`<!-- i18n:start -->`到`<!-- i18n:end -->`的區塊，裡面是中英對照表（`EXACT`）與含數字字串的規則（`RULES`），在畫面上把中文換成英文。
- **新增或修改介面文字時，要在同一頁的對照表補上英文**；對照表的鍵要和畫面上的中文一字不差（包含空格與全形標點）。沒有對應的字串會維持中文，不會出錯。
