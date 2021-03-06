# 1-3.ウィンドウの解説
<br>
いよいよゲームの中心となる、フィールド場面を作成して行きます。
この場面では、電車や地形、カメラ等が配置されます。
<br>
<br>
<br>



####　まず、シーンファイルを作成します。
<br>


「Scenes」フォルダの下に、「Field」と言うシーンを作成して下さい。
![](/Graphics/Unity/Chapter_2/Field_Scene/1.jpg)  
**図. フィールド場面作成**
<br>



####　次に、フィールド場面管理プログラムを作成します。
これは、ゲームルールを管理し、終了等が行えます。
<br>


「Scene_Manager」と言う空のゲームオブジェクトを作成して下さい。
![](/Graphics/Unity/Chapter_2/Field_Scene/2.jpg)  
**図. Scene_Managerオブジェクト作成**
<br>


「Scene_Manager」オブジェクトに「Field_Manager.cs」と言うC#スクリプトを作成し、貼り付けます。
![](/Graphics/Unity/Chapter_2/Field_Scene/3.jpg)  
**図. Field_Manager.cs貼り付け**
<br>


「Field_Manager.cs」には、以下をコピー&ペーストして下さい。

```c#:Field_Manager.cs
//------------------------------------------------------------------------
// ● 使用ライブラリの宣言
//------------------------------------------------------------------------
using UnityEngine;
using UnityEngine.SceneManagement;
using System.Collections;
//========================================================================
// ■ Field_Manager
//------------------------------------------------------------------------
//	フィールド場面の管理クラス。
//========================================================================

public class Field_Manager : Scene_Manager {
	//--------------------------------------------------------------------
	// ● メンバ変数
	//--------------------------------------------------------------------
	float end_second;	// ゲームが終了する秒数
	//--------------------------------------------------------------------
	// ● 初期化
	//--------------------------------------------------------------------
	protected override void Start() {
		base.Start();

		end_second = 5 * 60 + Time.time;	// 5分後に終了を設定
	}
	//--------------------------------------------------------------------
	// ● 更新
	//--------------------------------------------------------------------
	protected override void Update() {
		base.Update();

		// 終了秒に到達したか、BackSpaceボタンが押された場合
		if ( end_second < Time.time || Input.GetKeyDown(KeyCode.Backspace) )
			SceneManager.LoadScene("Test_Score");	// テスト場面に遷移

		// 終了までの秒数をデバッグ表示
		Debug_EX.add( "end_second : " + (end_second - Time.time) );
	}
}
```

<br>
<br>
<br>


「Scene_Manager.cs」と言うC#スクリプトを作成だけします。
「Field_Manager.cs」内部で自動的に呼ばれる為、貼り付けはしないで下さい。
![](/Graphics/Unity/Chapter_2/Field_Scene/4.jpg)  
**図. Scene_Manager.cs作成**
<br>


「Scene_Manager.cs」には、以下をコピー&ペーストして下さい。

```c#:Scene_Manager.cs
//------------------------------------------------------------------------
// ● 使用ライブラリの宣言
//------------------------------------------------------------------------
using UnityEngine;
using System.Collections;
//========================================================================
// ■ Scene_Manager
//------------------------------------------------------------------------
//	場面管理のクラス。
//========================================================================

public class Scene_Manager : MonoBehaviour {
	//--------------------------------------------------------------------
	// ● メンバ変数
	//--------------------------------------------------------------------
	int fps;						// FPS
	int frame_count;				// フレーム数
	float next_frame_check_second;	// 次回のFPS確認秒数
	//--------------------------------------------------------------------
	// ● 初期化
	//--------------------------------------------------------------------
	protected virtual void Start() {
		Cursor.lockState = CursorLockMode.Confined;	// マウスをウィンドウ枠内に固定
	}
	//--------------------------------------------------------------------
	// ● 更新
	//--------------------------------------------------------------------
	protected virtual void Update() {
		// FPSを計測
		frame_count++;	// フレーム数を加算
		// FPS確認秒数に到達した場合、FPSを更新
		if (next_frame_check_second < Time.time) {
			next_frame_check_second = 1 + Time.time;	// 次回確認秒数を設定
			fps = frame_count;	// FPSをフレーム数とする
			frame_count = 0;	// フレーム数をリセット
		}
		Debug_EX.add("FPS : " + fps);	// FPSをデバッグ表示
	}
}
```

<br>
<br>
<br>


####　更に、デバッグ表示用のプログラムを作成します。
これを行う事で、プログラム内部の問題を画面に表示出来、問題に気が付き易くなります。
<br>


「Scene_Manager」オブジェクトに「Debug_EX.cs」と言うC#スクリプトを作成し、貼り付けます。
![](/Graphics/Unity/Chapter_2/Field_Scene/5.jpg)  
**図. Debug_EX.cs貼り付け**
<br>


「Debug_EX.cs」には、以下をコピー&ペーストして下さい。

```c#:Debug_EX.cs
//------------------------------------------------------------------------
// ● 使用ライブラリの宣言
//------------------------------------------------------------------------
using UnityEngine;
using System.Collections;
//========================================================================
// ■ Debug_EX
//------------------------------------------------------------------------
//	デバック表示の拡張クラス。
//========================================================================

public class Debug_EX : MonoBehaviour {
	//--------------------------------------------------------------------
	// ● メンバ変数
	//--------------------------------------------------------------------
	public static bool is_view { get; private set; }	// 表示するか？
	static ArrayList texts = new ArrayList();			// デバッグ設定用の文章達
	static ArrayList view_texts = new ArrayList();		// デバッグ表示用の文章達
	static GUIStyle gui_style = new GUIStyle();			// 文字描画の体裁
	static int font_size = 14;							// 文字の大きさ
	//--------------------------------------------------------------------
	// ● 追加
	//	色と文字を追加可能。
	//--------------------------------------------------------------------
	public static void add(object o) {
		texts.Add(o);	// 文章達に追加し、一時保存
	}
	//--------------------------------------------------------------------
	// ● 初期化
	//--------------------------------------------------------------------
	void Start() {
		is_view = Debug.isDebugBuild;	// デバッグ中の時のみ表示

		gui_style.normal.textColor = Color.white;	// 文字色を白に設定
		gui_style.fontSize = font_size;				// 文字の大きさを設定
	}
	//--------------------------------------------------------------------
	// ● 更新（遅）
	//--------------------------------------------------------------------
	void LateUpdate() {
		view_texts = new ArrayList(texts);	// 表示文章達に、一時保存文章達をコピー
		texts.Clear();	// 毎フレーム初期化する
		
		// デバッグ表示キーが押された場合、表示フラグを反転
		if ( Input.GetKeyDown(KeyCode.Alpha1) )
			is_view = !is_view;
	}
	//--------------------------------------------------------------------
	// ● デバッグ表示
	//--------------------------------------------------------------------
	void OnGUI() {
		// 表示する場合
		if (is_view) {
			// 描画する矩形を作成
			var rect = new Rect(10, 10, 600, font_size + 5);

			// デバック用文章を走査し、全て画面に表示
			foreach (var text in view_texts) {
				// 色の場合、色を設定
				if (text is Color)
					gui_style.normal.textColor = (Color)text;
					
				// 文字の場合、描画
				else if (text is string) {
					GUI.Label(rect, (string)text, gui_style);
					rect.y += font_size + 5;
				}
			}
		}
	}
}
```
<br>
<br>
<br>


