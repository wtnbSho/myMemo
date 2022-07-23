# This is sample code of markdown.

# 見出し1
## 見出し2
### 見出し3
#### 見出し4
##### 見出し5
###### 見出し6

<br>

- リスト1
	- ネスト リスト1_1
		- ネスト リスト1_1_1
		- ネスト リスト1_1_2
	-ネスト リスト1_2
- リスト2
- リスト3

<br>

1. 番号付きリスト1
	1. 番号付きリスト1_1
	1. 番号付きリスト1_2
1. 番号付きリスト2
1. 番号付きリスト3

<br>

> 引用文。
>
> 引用文。引用文。引用文。
>
>> 二重引用文。  
>> 二重引用文。  
>> 二重引用文。
>
> 引用文

<br>

バッククォートで囲うと`コード記法`となる。

<br>

これが *強調*  
これも _強調_

<br>

weightRegular **weightBold**  
weightRegular __weightBold__

<br>

強調かつ太文字は ***こう***  
How emphasize and chang font bold is ***THIS.***

<br>

***
---
- - -
* * *
-  -  -
*  *  *

<br>

[Google](https://www.google.co.jp/)  

[定義参照もできる。これはgoogleをリンクとして参照する例][google]  
その他の文章  
…
その他の文章  
[これもgoogleを参照する][google]

[google]: https://www.google.co.jp/

<br>

## GitHub Flavored Markdown (GFM)  
GitHub の独自仕様を加えたMarkdown  
  
~~取り消し線~~  

pre記法

```html
<!-- html -->
<p>こんにちは</p>
```

~~~html
<!-- html -->
<span>チルダでもOK</span>
~~~

```css
/* css */
p {
	color: white;
}
```

~~~js
// js
let sample = 1;
const sample2 = 2;
~~~

### 表
|header1|header2|header3|
|:--|--:|:--:|
|align left|align right|align center|
|a|b|c|