# 4-2.UIの基本
<br>
この章では、操作説明等の画面表示を実装します。
UIとは、ユーザーインタフェースの略で、プレイヤーに情報を伝える為の物です。
ここでは、画面表示の基本を解説します。
<br>
<br>
<br>



最初に、「Scene」ビューを2D表示にします。
![](/Graphics/Unity/Chapter_4/UI_Standard/1.jpg)
**図. Sceneビューの2D表示**
<br>


こうする事で、UIが設定し易くなります。



次に「Event System」を作成します。
これは、UIへの入力を扱います。

「Hierarchy」ウィンドウから「Create」→「UI」→「Event System」を選択し、作成します。
![](/Graphics/Unity/Chapter_4/UI_Standard/2.jpg)
**図. EventSystemの作成**
<br>


「Event System」を図と同じように設定します。
![](/Graphics/Unity/Chapter_4/UI_Standard/3.jpg)
**図. EventSystemの設定**
<br>


他の場面でも使用するので、プレハブ化します。
![](/Graphics/Unity/Chapter_4/UI_Standard/4.jpg)
**図. EventSystemのプレハブ化**
<br>


これでUIが入力を受け付けるようになりました。



次に、「Canvas」を作成します。
これは、様々な画面表示の器となる物です。

「Hierarchy」ウィンドウから「Create」→「UI」→「Canvas」を選択し、作成します。
![](/Graphics/Unity/Chapter_4/UI_Standard/5.jpg)
**図. Canvasの作成**
<br>


「Canvas」を図と同じように設定します。
![](/Graphics/Unity/Chapter_4/UI_Standard/6.jpg)
**図. Canvasの設定**
<br>


他の場面でも使用する為、
「Canvas」を「Project」ビューの「Prefabs」フォルダ内にドラッグ&ドロップし、プレハブ化します。
![](/Graphics/Unity/Chapter_4/UI_Standard/7.jpg)
**図. Canvasのプレハブ化**
<br>


これで、画面表示を行う準備が整いました。
<br>


文章を画面に表示します。
これは、文章を画面に表示させる為に使用します。

「Canvas」を右クリックし「UI」→「Text」を選択し、作成します。
![](/Graphics/Unity/Chapter_4/UI_Standard/8.jpg)
**図. Textの作成**
<br>


「Text」を選択したまま、キーボードの「F」キーを押します。
すると「Text」にカメラの焦点が合います。
![](/Graphics/Unity/Chapter_4/UI_Standard/9.jpg)
**図. Fキーによる焦点合わせ**
<br>


いつも通りの方法で、位置や回転を調整した後、大きさを変更します。
画面左上の「RectTool」アイコンをクリックします。
![](/Graphics/Unity/Chapter_4/UI_Standard/10.jpg)
**図. RectToolの説明**
<br>


「Text」の周辺に出現した矩形を引っ張る事で、大きさが変更出来ます。
![](/Graphics/Unity/Chapter_4/UI_Standard/11.jpg)
**図. RectToolによる大きさ変更**
<br>


「Rect Transform」コンポーネント左上の正方形をクリックすると「Anchor Presets」が開きます。
これは、位置の基準点を変更出来ます。
![](/Graphics/Unity/Chapter_4/UI_Standard/12.jpg)
**図. AnchorPresetsの説明**
<br>


「Rect Transform」コンポーネント内の「Pivot」の「X」「Y」を「0～1」の範囲で設定すると、
オブジェクトの中心点の位置を設定出来ます。
![](/Graphics/Unity/Chapter_4/UI_Standard/13.jpg)
**図. Pivotの説明**
<br>


「Inspector」ウィンドウから「Text」内の「Text」コンポーネントの「Text」項目に好きな文字を入力します。
![](/Graphics/Unity/Chapter_4/UI_Standard/14.jpg)
**図. Textの文字入力**
<br>


「Text」を図と同じように設定すると、丁度良い感じになります。
![](/Graphics/Unity/Chapter_4/UI_Standard/15.jpg)
**図. Textの設定**
<br>


この状態で「Game」ビューを見ます。
ゲーム実行中は、このように画面表示が行われます。
![](/Graphics/Unity/Chapter_4/UI_Standard/16.jpg)
**図. GameビューでのText表示**
<br>



画像を画面に表示します。
これは、画像を画面に表示させる為に使用します。

「Canvas」を右クリックし「UI」→「Image」を選択し、作成します。
![](/Graphics/Unity/Chapter_4/UI_Standard/17.jpg)
**図. Imageの作成**
<br>


「Inspector」ウィンドウから「Image」内の「Image」コンポーネントを図と同じように設定します。
![](/Graphics/Unity/Chapter_4/UI_Standard/18.jpg)
**図. Imageの設定**
<br>


「Source Image」で画像を選択します。
「Color」で色を付与します。
「Set Native Size」で画像と同じ大きさにします。
<br>



ボタンを画面に表示します。
これは、クリック可能なボタンを画面に表示させる為に使用します。

「Canvas」を右クリックし「UI」→「Button」を選択し、作成します。
![](/Graphics/Unity/Chapter_4/UI_Standard/19.jpg)
**図. Buttonの作成**
<br>


ボタンは、「Image」と「Text」から成り立っています。
証拠に「Button」オブジェクト内に「Image」コンポーネントがあり、
子オブジェクトに「Text」があります。
![](/Graphics/Unity/Chapter_4/UI_Standard/20.jpg)
**図. Buttonの説明**
<br>


「Inspector」ウィンドウから「Button」内の「Button」コンポーネントを図と同じように設定します。
![](/Graphics/Unity/Chapter_4/UI_Standard/21.jpg)
**図. Buttonの設定**
<br>


「Normal Color」は、ボタンの基本色を設定します。
「Highlighted Color」は、マウスが上に置かれた際のボタン色を設定します。
「Pressed Color」は、ボタンが押された際の色を設定します。
「Navigation」は、ボタン選択後に「カーソル」キーで、他のボタンへの移動先を設定出来ます。
「Onclick()」は、ボタン押下後に呼ぶスクリプトを設定します。



以上で3種類のUIを解説しました。
これ以外にも、様々なUIがある為、興味があれば試して見て下さい。



これらは、プロジェクトには不要なので、内容が確認出来たら削除します。
「Button」オブジェクト、「Image」オブジェクト、「Text」オブジェクトを選択し、「Delete」キーを押して下さい。
![](/Graphics/Unity/Chapter_4/UI_Standard/22.jpg)
**図. 不要UIの削除**
<br>


