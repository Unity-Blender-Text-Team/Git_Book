# OculusRiftDK2をUnityでセットアップ
<br>
「OculusRiftDK2」のセットアップの続きです。 
ここまでで、OculusRiftDK2は、パソコンに接続している状態です。
<br>
<br>
<br>



####　次に、Unity内でOculusをセットアップします。 
<br>
Unityを起動し、プロジェクトを読み込んで下さい。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/1.jpg)  
**図. Unity画面**
<br>


続いて、ダウンロードした「ovr_unity_utilities_1.15.0.zip」を解凍して下さい。
解凍ソフトが入っている場合、起動すると自動で解凍されますが、
そうでない場合は、解凍ソフトを探してインストールしておいて下さい。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/2.jpg)  
**図. 圧縮ファイル**
<br>


解凍されると、「ovr_unity_utilities_1.15.0」フォルダが出来ます。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/3.jpg) 
**図. 解凍後のフォルダ**
<br>


フォルダ内の「OculusUtilities」フォルダを開きます。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/4.jpg)  
**図. 解凍後のフォルダ内**
<br>


その中の「OculusUtilities.unitypackage」を起動して下さい。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/5.jpg)  
**図. OculusUtilitiesフォルダ内**
<br>
<br>
<br>



####　ここからは、Unity内での作業になります。
Unity内で、下記のウィンドウが出ます。
右下の「Import」を押します。
これでOculus関係のファイルが読み込まれます。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/6.jpg)  
**図. パッケージ読み込み画面**
<br>


再起動を促して来た場合、「Restart」を押し、再起動しましょう。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/7.jpg)  
**図. 再起動催促画面**
<br>


バージョン更新を促して来た場合、「Yes」を押しましょう。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/8.jpg)  
**図. バージョン更新催促画面**
<br>


上部メニューから、「Edit　→　Project Settings　→　Player」を選択し、
「Inspector」ウィンドウの「Other Settings」内の「Virtual Reality Supported」チェックを入れます。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/9.jpg)  
**図. VR設定画面**
<br>


Oculusファイルが正常に読み込まれた場合、「Project」ウィンドウにて「OVR」フォルダが作成されている事が確認出来ます。
「OVR/Prefabs」内の「OVRPlayerController」プレハブを、「Scene」ウィンドウにドラッグして下さい。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/10.jpg)  
**図. Oculusプレハブのドラッグ**
<br>


これは、OculusRiftのカメラ移動と歩行機能が、既にプログラムされた物であり、ドラッグして配置するだけで、直ぐに使えます。
<br>
「Hierarchy」ウィンドウから、ドラッグした「OVRPlayerController」を選択して下さい。
位置を調整して、電車の先頭車両の椅子付近に配置して見て下さい。
回転を調整して、電車の進行方向に向かせて下さい。
これらが、アプリ開始時の最初の位置、角度になります。
![](/Graphics/Oculus_Rift_DK2/Setup_For_Unity/11.jpg)  
**図. Oculusプレハブの配置調整後**
<br>


OculusRiftDK2を被り、Unityの再生ボタンを押して、開始してみましょう。
最初、Oculusに健康への警告文が表示され、数秒後Unityの画面が映ります。
上手く電車に乗車出来ましたか？


