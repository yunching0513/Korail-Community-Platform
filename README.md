# Machan 3D模型

Machan - Korail Community Platform（Paraa設計，孟加拉達卡Korail聚落，2024年12月啟用）的互動3D量體模型。這是臺大「當代建築」課程亞太篇（critical regionalism）分組作業的研究用模型。

線上版：https://korail-community-platform.vercel.app

打開 `index.html` 就能看，不需要安裝任何東西。頁面右側第一張卡片是建築基本資料（設計者、地點、年代、規模、構造、資助與獎項）。

## 可以做什麼

- **三種顯示方式：** 圖解（用顏色區分構件）、素模（單色白模）、擬真（材質、天空、霧霾，傍晚會點亮燈籠）。
- **視角：** 鳥瞰、從空地看、站上平台、巷道側、正上方。
- **分解：** 把地面層、二樓平台、上層磚牆、鋼構遮棚逐層拉開。
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
