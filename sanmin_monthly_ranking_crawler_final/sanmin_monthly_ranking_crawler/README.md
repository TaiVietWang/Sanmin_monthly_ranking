# 三民書局｜最新月份排行榜爬蟲（Jupyter Notebook）

## 專案簡介 / Project Description

**中文（繁體）**  
> 📚 一支用 Python（Jupyter Notebook）撰寫的三民書局「最新月份排行榜」爬蟲，僅抓取單一月份的排行榜資料，避免對網站造成過大負載。可自動擷取書名、作者、出版社、出版日期、價格、折扣、分類等資訊並輸出 CSV，並提供簡易設定讓使用者自行修改月份參數 `base_url` 抓取不同月份的資料。僅供研究與技術交流，請遵守網站服務條款與 robots.txt。  

**English**  
> 📚 A Python (Jupyter Notebook) crawler for **Sanmin.com.tw**’s "Latest Monthly Ranking", fetching only a single month’s ranking list to minimize server load. It extracts key book details (title, author, publisher, publish date, price, discount, category, etc.) and exports them to CSV. Users can easily change the `base_url` parameter to scrape other months’ rankings. For research and educational purposes only – please respect the site’s Terms of Service and robots.txt.  


只抓取 **三民書局（sanmin.com.tw）最新月份排行榜** 的安全版爬蟲 Notebook。  
本專案僅提供 **單一入口、單一清單** 的資料擷取範例，避免對站方造成過大負載，適合公開分享與二次研究。

## ✅ 功能
- 擷取「最新月份排行榜」頁面之書籍清單
- 抽取常見欄位（如：書名、作者、出版社、出版日期、價格、折扣、分類路徑…）
- 以 `time.sleep()` 做基本頻率控制
- 輸出為 **CSV** 以利後續分析

> **不** 進行全站遍歷（不抓所有分類／所有分頁），僅示範單一排行榜清單，較安全。

## 📁 結構
```
.
├─ notebooks/
│  └─ sanmin_ranking_20250225.ipynb   # 單一 Notebook：最新月份排行榜
├─ requirements.txt
├─ .gitignore
├─ LICENSE
└─ README.md
```

## 🚀 使用方法
1) 下載或複製專案
```bash
git clone https://github.com/<your-username>/sanmin-monthly-ranking-crawler.git
cd sanmin-monthly-ranking-crawler
```
2) 建立虛擬環境（建議）並安裝依賴
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

pip install -r requirements.txt
```
3) 開啟並執行 Notebook  
使用 VS Code、Jupyter Lab 或 `jupyter notebook` 開啟 `notebooks/sanmin_ranking_20250225.ipynb`，依內文說明執行即可。


### 📅 修改抓取月份
在 `notebooks/sanmin_ranking_20250225.ipynb` 中，程式開頭會有：
```python
# 基本設置
base_url = "https://www.sanmin.com.tw/promote/top/?id=yy&item=11403"
```
其中 `item=11403` 表示要抓取的月份排行榜編號。

#### 如何找到正確編號：
1. 打開三民書局排行榜首頁：https://www.sanmin.com.tw/promote/top/
2. 選擇想抓取的月份排行榜。
3. 查看瀏覽器網址列中的 `item=XXXXX` 數字，複製該數字。
4. 將程式中的 `11403` 改成新數字並儲存。
5. 重新執行 Notebook，即可抓取該月份的排行榜資料。

> 註：排行榜的編號會隨月份變化，請每次抓取前先到網站確認最新編號。


## 🔒 法遵與風險提示
- 僅供 **研究與技術交流**，請遵守網站 **服務條款** 與 **robots.txt**。  
- 請維持合理的請求頻率，避免對站方造成壓力（已示範 `time.sleep()`）。  
- 若後續擴充功能，請務必保持「單一入口的清單擷取」範圍，不要做全站遍歷。  
- 嚴禁將本範例用於商業服務或大規模資料鏟取。

## 📝 授權
MIT License
