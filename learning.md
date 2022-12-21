# 知らないことメモ
## テキストアニメーション
- 不明な挙動が発生した時に役立った [overflow: hiddenが指定された要素を持つinline-blockの高さが親の高さと違う理由](https://ja.stackoverflow.com/questions/2603/overflow-hidden%e3%81%8c%e6%8c%87%e5%ae%9a%e3%81%95%e3%82%8c%e3%81%9f%e8%a6%81%e7%b4%a0%e3%82%92%e6%8c%81%e3%81%a4inline-block%e3%81%ae%e9%ab%98%e3%81%95%e3%81%8c%e8%a6%aa%e3%81%ae%e9%ab%98%e3%81%95%e3%81%a8%e9%81%95%e3%81%86%e7%90%86%e7%94%b1)  

- 徐々に表示されるテキストアニメーション [簡単CSSアニメーション＆デザイン20選（ソースコードと解説付き）](https://baigie.me/officialblog/2021/02/25/css-tips-1/)

---

## ブラウザレンダリング
- CPUとGPU [CSS アニメーションについて深く知る](https://qiita.com/yuki153/items/9aac0e5c8d7230a7bbe2#transform-translatex0-%E3%81%AE%E9%81%A9%E5%BF%9C)  
- will-changeプロパティの注意点 [CSS will-changeプロパティについて知っておくべきこと](https://dev.opera.com/articles/ja/css-will-change-property/)
- [CSSホバー処理のパフォーマンスや滑らかさなどを考慮した最適なコードを考察](https://qiita.com/watamura/items/998a8e34c1e1f7504fdd)
- [widthやheightをアニメーション化してはいけない](https://zenn.dev/solo/articles/29b29db9f9a7d0)

- [ReFlowの原因とマークアップの最適化](https://engineering.linecorp.com/ja/blog/reflow-and-markup-optimization/)

---

## transitionとanimationの優位性
- [CSS Transition と Keyframe Animation 違いと優位性](http://better-than-i-was-yesterday.com/css-transition-and-css-animation/)

---

## slick-sliderのお約束  
```html
<div id="slider">
	<div class="slick-slide">
		コンテンツを入れる
	</div>

	<div class="slick-slide">
		コンテンツを入れる
	</div>

	<div class="slick-slide">
		コンテンツを入れる
	</div>
</div>
```
- 上記のように、第2階層はdiv.slick-slideとする
- 【重要】コンテンツは第3階層からにする  
- 【重要】スマホ対応には、コンテンツ第一階層にwidth: 100vw;を指定する

### ダメな例  
```html
<div id="slider">
	<figure class="slick-slide">
		figure自体がコンテンツ
	</figure>

	<figure class="slick-slide">
		figure自体がコンテンツ
	</figure>

	<figure class="slick-slide">
		figure自体がコンテンツ
	</figure>
</div>
```
- ダメな例のようにすると、画像サイズがコントロールできず、スマホ対応できない。

---

## slickSetOptionの注意事項

使用時はresponsive:[{}]を使用していないか注意せよ  

成功例
```js
/*autoplay開始位置設定*/
function triggerScroll(targetObj) {
	let targetFlag = false;
	$(window).on('scroll', function(){
		let scrollTop = $(window).scrollTop();
		let scrollBottom = scrollTop + $(window).height();
		let targetTop = targetObj.offset().top;
		let targetBottom = targetTop + targetObj.height();
		if (scrollBottom > targetTop && scrollTop < targetBottom) {
			if (!targetFlag) {
				targetObj.slick('slickSetOption', {
					autoplay: true,
					responsive:[{
						breakpoint:500,
						settings: {
							autoplay: true
						}
					}]
				},true);
				targetFlag = true;
			}
		}
	});
};
```

失敗例
```js
/*autoplay開始位置設定*/
function triggerScroll(targetObj) {
	let targetFlag = false;
	$(window).on('scroll', function(){
		let scrollTop = $(window).scrollTop();
		let scrollBottom = scrollTop + $(window).height();
		let targetTop = targetObj.offset().top;
		let targetBottom = targetTop + targetObj.height();
		if (scrollBottom > targetTop && scrollTop < targetBottom) {
			if (!targetFlag) {
				targetObj.slick('slickSetOption', {
					autoplay: true,
				},true);
				targetFlag = true;
			}
		}
	});
};
```

ターゲット要素にresponsiveプロパティが指定されていた場合、slickSetOptionでもrespoinsiveに操作したいプロパティを指定しなければならない（今回でいえばautoplay）。ターゲット要素のresponsiveでautoplayに関する記述などないにもかかわらず、この指定をしなければautoplayが適用されなかった。

## 単色にはpngを使う
自然な写真はjpgでもいいようだが。。今回の例では単色ロゴ画像をjpgで書き出したところ、色むらが現れていた。これがpngだと発生しない（アウトラインの淵の部分はギザギザになってしまうがこれは仕方がない。）  
``単色べた塗り = png``で覚えておいてよさそうだ。