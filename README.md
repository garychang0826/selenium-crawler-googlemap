<!-- @format -->

# selenium-crawler-google map

此項目是透過 python selenium 自動化蒐集 google map 上的資料，並進行初步的資料整理後提供給 [ADL-HW3](https://github.com/jimpei8989/ADL-HW3) 進行 文章生成情緒分析訓練。

crawler 中包含兩個檔案 :

1. [mix.py](https://github.com/cyyW/selenium-crawler-googlemap/blob/master/crawler/mix.py) 透過 selenium 爬取 google map 中評論的時間、讚數、星數及留言資訊，過程使用 pandas 去除空白留言資料並存入 Excel 之中。

2. [資料處存.py](https://github.com/cyyW/selenium-crawler-googlemap/blob/master/crawler/%E8%B3%87%E6%96%99%E8%99%95%E5%AD%98.py) 則是將 [tptptk.xlsx](https://github.com/cyyW/selenium-crawler-googlemap/blob/master/crawler/tptptk.xlsx) 的資料清洗及整理成如 [tptptkclean2.xlsx](https://github.com/cyyW/selenium-crawler-googlemap/blob/master/crawler/tptptkclean2.xlsx) 中的狀態。
    - 過濾留言中中文以外的字詞，將星數進行正負面分類
    - 去除空白留言資料
    - 隨機取正向資料 5000、負向資料 3000 存入 [tptptkclean2.xlsx](https://github.com/cyyW/selenium-crawler-googlemap/blob/master/crawler/tptptkclean2.xlsx)

## 環境

-   python `3.9.15`
-   虛擬環境使用 `conda`
-   chrome driver : https://chromedriver.chromium.org/downloads

## 使用

-   [mix.py](https://github.com/cyyW/selenium-crawler-googlemap/blob/master/crawler/mix.py) 抓取評論星數的功能因 google map 改版暫時無法使用

-   [mix.py](https://github.com/cyyW/selenium-crawler-googlemap/blob/master/crawler/mix.py) 如若無法順利運行請自行檢查 driver.find_element By.XPATH 中的 FULL XPATH 於 google map 中是否有更動並請自行替換

-   Transformer 檔案 ADL-HW3, 來自 Wu-Jun Pei, https://github.com/jimpei8989/ADL-HW3

-   谷歌人工智能 mt5-small, 來自https://huggingface.co/google/mt5-small
