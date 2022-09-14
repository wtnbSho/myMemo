# Snippet

## scss
### ピラミッド型
よく円3つをピラミッド型にするよね
```scss
$window-margin: 20vw; // 画面の標準余白の合計。今、width:80vw;のため、画面の左右余白の合計は20vwとなる
$object-width: 38vw; // 三角形にしたい要素のwidth。

width: $object-width;
height: $object-width;
&:last-of-type {
	// 要素の動きうる範囲の余白を2分の1し、要素の左右のマージンに当てる。
	// 動きうる範囲とは、「画面幅」から「左右余白幅」を引き、さらに「要素幅」を引いた値。
	// 左右のマージンは上記を1/2した値とすればよい。
	margin: 0 calc((100vw - $window-margin - $object-width) / 2 );
			}
```