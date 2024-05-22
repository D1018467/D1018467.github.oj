# D1018467.github.oj
## 歡迎來到黃紹軒的網路世界

為了讓世界上的每個人都不會對平閏年感到困惑，而做了這個網頁

### 公式

公式如下

```公式
看懂但沒完全看懂的公式

# 能被4整除叫閏年
## 被100整除的叫平年
### 被400年整除的又叫閏年

- 但如果又能被4整除又能被被100整除的叫什麼
- 答案是平年

- 但如果能被4整除又能被被100整除還能被400整除的叫什麼
2. 答案是閏年

```

看不懂沒關係啦，幫你寫了一個平閏年的轉換公式，而且還能告訴你最近的平閏年是什麼

### 紹軒apps

因為是量身定做而且完全免費的apps，如果有需要請聯繫微信:1514576802

### Support or Contact

由紹軒團隊所創立的apps，並且由紹軒公司贊助



















我的第二篇
# first-website
<head><strong><em><div style="text-align:center;"><h1>萬年曆code</h1></div>
是不是大家一看到萬年曆就頭痛，code一定很難寫，在這裡我提供了我個人寫的code
<pre><div style="text-align:right;"><h1>BY 最帥的黃紹軒</h1></div>

<a href="https://zh.wikipedia.org/wiki/%E4%B8%9C%E8%8E%9E%E5%8F%B0%E5%95%86%E5%AD%90%E5%BC%9F%E5%AD%A6%E6%A0%A1"><button type="button"><img src="https://tse1.mm.bing.net/th?id=OIP.1nQw_THYsREpNFeMKb7DRgHaHa&pid=Api&P=0&w=154&h=154" border="0"></button></a>
<input type="button" value="點這裡"style="background-color:green;">

<input type="button" value="點這裡，這裡是世界上最棒的學校" style="background-color:green;" onclick="location.href='https://www.fcu.edu.tw/'">
C:\Users\15145\Desktop\IMG_20190804_145254.jpg" style="width:360px;height:400px;




<p>#include <stdio.h>
import os
import cv2
from ultralytics import YOLO

# 載入模型
model = YOLO('models/class1.pt')          #改成使用之模型

# 輸入和輸出資料夾路徑
input_folder = 'see/test'
output_folder = 'see/end'

# 確保輸出資料夾存在，如果不存在就創建它
if not os.path.exists(output_folder):
    os.makedirs(output_folder)

# 讀取test資料夾下的所有圖片
for filename in os.listdir(input_folder):
    if filename.endswith(('.jpg', '.jpeg', '.png')):
        # 讀取圖片
        image_path = os.path.join(input_folder, filename)
        image = cv2.imread(image_path)

        # 進行推論
        results = model(image)

        #print(results[0].boxes.cls)
        #print(results[0].boxes.xyxy)

        # 提取並印出物件的類別
        for cls in results[0].boxes.cls:  # 假設只有一個物件
            print(f"Class: {cls}")
        for box in results[0].boxes.xyxy:  # 假設只有一個物件
            x_min, y_min, x_max, y_max = box[0], box[1], box[2], box[3]
            print(f"Coordinates: ({x_min}, {y_min}, {x_max}, {y_max})")

        # 繪製檢測結果
        annotated_image = results[0].plot()

        # 將辨識結果圖片儲存到end資料夾中
        output_path = os.path.join(output_folder, filename)
        cv2.imwrite(output_path, annotated_image)

print("辨識結果已輸出到end資料夾中")
