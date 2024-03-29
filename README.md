# Identify-Customer-Segments
使用Arvato的資料進行客戶分群
[jupyternotebook](https://nbviewer.jupyter.org/github/JHL01/Identify-Customer-Segments/blob/master/Identify_Customer_Segments.ipynb)


>### 運作環境：
- Python version == 3.6.4
  - sklearn == 0.20.2
  - numpy == 1.15.4
  - pandas == 0.22.0
  - seaborn == 0.9.0
  - scipy== 1.1.0
>### 專案介紹：
在這個專案中，AZ Direct和Arvato Financial Solutions提供了兩個資料集，其中一個包含有關德國人的人口統計資料，另一個為郵購銷售公司客戶的資料(兩者具有相同欄位)。其中，我們對德國人口統計資料應用非監督式學習技術。包含數據進行預處理、降維及聚類算法以對客戶進行細分，目標是優化郵件訂購公司的客戶拓展。

>### 資料介紹：
* Udacity_AZDIAS_Subset.csv：德國的人口統計數據; 891,211筆 x 85個特徵
* Udacity_CUSTOMERS_Subset.csv：郵購公司客戶的人口統計數據; 191,652筆 x 85個特徵
* Data_Dictionary.md：有關所提供數據集中的功能的詳細信息文件
* AZDIAS_Feature_Summary.csv：人口統計數據的要素屬性摘要

人口統計文件中包含個人以外的訊息，例如有關家庭、建築物和社區的訊息。由於保密條款，無法在此發布Arvato Financial Services提供的數據。
>### 方法概述：
首先處理遺失值的問題，再根據特徵類型重新編碼及標準化，然後利用 PCA 將特徵從 86 維降至 35 維。最後使用 k-means 將一般人群聚類成具有相似人口統計特徵的群組
，然後套用至客戶資料集中，經過比較後即可獲得核心用戶群的樣貌。

>### 主要發現：
- 利用聚類方法可以發現郵購公司的客群具有明顯的組成特性。
- 此結果能夠清楚識別出郵購公司的核心客群樣貌為較傳統、較年長的男性。
- 選擇 k-means 聚類數量時未能出現明顯的"elbow point"，推測是由於雜音過多所致，可嘗試使用能辨識雜音的算法，例如：DBSCAN。
