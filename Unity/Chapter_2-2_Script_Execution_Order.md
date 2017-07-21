# 2-2.スクリプト実行順序の設定
<br>
ここでは、スクリプトの実行順序を設定します。
Unityは、コンポーネント指向と呼ばれる、プログラムをコンポーネント単位で等価に扱う仕組みで実装します。
その為、プログラムの実行順序は、起動毎に変わってしまいます。
特定のプログラムの先や後に実行しなければならない処理は、順序が入れ替わると、エラーを起こします。
ここで、しっかりと設定しておきましょう。
<br>
<br>
<br>



Unityエディタの左上から「Edit」→「Project Settings」→「Script Execution Order」を選択すると、
「Inspector」ウィンドウに「Script Execution Order」が表示されます。
![](/Graphics/Unity/Chapter_X/Script_Execution_Order/1.jpg)
**図82. ScriptExecutionOrderの開き方**
<br>


枠内に、「Project」ビューから「Debug_EX.cs」をドラッグ&ドロップします。
更にドラッグし、「Default Time」よりも下、一番下に配置します。
![](/Graphics/Unity/Chapter_X/Script_Execution_Order/2.jpg)
**図83. ScriptExecutionOrderへの設定**
<br>


これで、デバッグ表示スクリプトが、一番最後に実行されるようになりました。
他の全スクリプトから、デバック表示命令を受け取ってから、表示処理を実行しないと、
このスクリプトより後のスクリプトが、表示されなくなる為、このように設定しました。
<br>


「Default Time」では、未設定のスクリプトが順不同で実行され、「Unityエディタ」起動の度に実行順序が変わります。
「Default Time」より上は、未設定のスクリプトより早く、設定順序の通りに実行され、
「Default Time」より下は、未設定のスクリプトより遅く、設定順序の通りに実行されます。

ドラッグ以外にも、下の「+」からスクリプトを登録できます。
また、右の「-」で登録を削除します。


