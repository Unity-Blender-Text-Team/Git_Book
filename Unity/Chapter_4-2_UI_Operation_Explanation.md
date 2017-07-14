# 4-2.操作説明UIの作成
<br>
この章では、操作説明や、スコア等の画面表示を実装します。
UIとは、ユーザーインタフェースの略で、プレイヤーに情報を伝える為の物です。
ここでは、アプリの操作説明を行うUIを作成します。
<br>
<br>
<br>



「Scene」ビューを2D表示にすると操作が行い易いです。



空のゲームオブジェクトを作成し「UI_Info」と名付け、図と位置を合わせます。
これが、操作説明UIのトップのオブジェクトとなります。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/1.jpg)
**図. UI_Infoの作成**
<br>


「UI_Info」の子オブジェクトとして「Image」を作成します。
「Back_Ground」と名付け、図と位置を合わせます。
これが、操作説明UIの背景となります。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/2.jpg)
**図. Back_Groundの作成**
<br>


「Image」の「Source Image」から好きな画像を選択し、背景にしましょう。
とりあえず、選択すると出現する「Select Sprite」画面の一番下の方にある
四角形の画像の中から、気に入った画像をお選び下さい。
筆者は「UI_Sprite」を選択しました。
また、好きな色を選択しましょう。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/3.jpg)
**図. SourceImageの設定**
<br>


更に「Back_Ground」の子オブジェクトとして「Text」を作成します。
「Text」と名付け、図と位置を合わせます。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/4.jpg)
**図. Textの作成**
<br>


「Text」の中に、適当にアプリの操作説明を記述します。

```text:操作説明文章.txt
操作説明

首を動かして、景色を見よう！
```

文字サイズ等は、図に合わせるとピッタリになります。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/5.jpg)
**図. Textの設定**
<br>


「Text」に「Outline」コンポーネントを追加します。
これは、文字に縁取りを付け、見栄えを良くします。
「Add Component」→「UI」→「Effects」→「Outline」から追加します。
「Effect Color」で色を設定します。
「Effect Distance」で縁取りの大きさを設定します。
面倒なら、図と合わせて下さい。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/6.jpg)
**図. Outlineの追加**
<br>


次に、操作説明UIのトップである「UI_Info」を選択し、
「Add Component」→「Layout」→「Canvas Group」を追加し、
図と設定を合わせて下さい。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/7.jpg)
**図. CanvasGroupの追加**
<br>


「Alpha」は「0～1」で不透明度を設定出来、「0」にすると完全に消えます。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/8.jpg)
**図. CanvasGroupの説明**
<br>


操作説明UIの挙動を追加します。
「UI_Info」オブジェクトに「UI_Info.cs」スクリプトを追加し、
以下をコピー&ペーストして下さい。

```c#:UI_Info.cs
//------------------------------------------------------------------------
// ● 使用ライブラリの宣言
//------------------------------------------------------------------------
using UnityEngine;
using System.Collections;
//========================================================================
// ■ UI_Info
//------------------------------------------------------------------------
//	操作説明のUIクラス。
//========================================================================

public class UI_Info : MonoBehaviour {
	//--------------------------------------------------------------------
	// ● メンバ変数
	//--------------------------------------------------------------------
	CanvasGroup group;	// 画布集団
	float end_second;	// 終了秒数
	//--------------------------------------------------------------------
	// ● 初期化
	//--------------------------------------------------------------------
	void Start() {
		// 画布集団を設定
		group = GetComponent<CanvasGroup>();	// 取得
		group.alpha = 1;						// 表示させる

		end_second = 10 + Time.time;	// 10秒後に表示終了を設定
	}
	//--------------------------------------------------------------------
	// ● 更新
	//--------------------------------------------------------------------
	void Update() {
		// 終了秒数経過した場合
		if (end_second < Time.time)
			group.alpha = 0;	// 画布集団を非表示
	}
}
```


最後に、軽量化をします。
操作説明UIのトップである「UI_Info」を選択し、
右上の「Static」にチェックを入れて下さい。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/9.jpg)
**図. Staticの設定**
<br>


すると「Change Static Flags」ウィンドウが開き、
子オブジェクトも変更するか尋ねられるので、
「Yes, change Children」を選択します。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/10.jpg)
**図. ChangeStaticFlagsの設定**
<br>


これで操作説明UIの全オブジェクトが「Static」になりました。
これは、動かないオブジェクトに設定する事で、
計算を省略出来、若干アプリの動作が軽くなります。
「Rect Transform」や「Transform」を変更しないオブジェクトには、
積極的にチェックを入れましょう。
<br>



尚、階層はこのようになっています。
![](/Graphics/Unity/Chapter_4/UI_Operation_Explanation/11.jpg)
**図. UI_Infoの階層の説明**
<br>


