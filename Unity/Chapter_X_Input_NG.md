# X.キー入力の設定
<br>
この章では、キー入力を設定します。
UIのボタン入力や、キャラクターの移動や回転等に、キー入力が多用される為、
ここで設定します。
<br>
<br>
<br>



Unityエディタの左上から「Edit」→「Project Settings」→「Input」を選択すると、
「Inspector」ウィンドウに「InputManager」が表示されます。
![](/Graphics/Test/Test.jpg)  
**図. テスト画像**
<br>


「Axes」横の矢印をクリックすると、展開します。
複数の名前がありますが、これらはスクリプトから呼び出す事で、入力に使用出来ます。
![](/Graphics/Test/Test.jpg)  
**図. テスト画像**
<br>


例として「Input.GetButtonDown("Cancel");」と文字列で呼び出し、
「ESC」キーとゲームパッド「1ボタン」が押されたかを取得出来ます。
<br>

このように、複数のボタンや、複数のデバイスを一括で設定し取得出来る為、
とても重要な設定項目となっています。
<br>


しかし、ここでは詳細の説明を割愛します。
「Unityエディタ」ではなく、エクスプローラー（フォルダの事）を開いて下さい。
「/VR_Romance_Car/ProjectSettings/InputManager.asset」をテキストエディタで無理やり開きます。
![](/Graphics/Test/Test.jpg)  
**図. テスト画像**
<br>


中身を全て消して、以下をコピー&ペーストして下さい。

```text:InputManager.txt
%YAML 1.1
%TAG !u! tag:unity3d.com,2011:
--- !u!13 &1
InputManager:
  m_ObjectHideFlags: 0
  serializedVersion: 2
  m_Axes:
  - serializedVersion: 3
    m_Name: move_x
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: left
    positiveButton: right
    altNegativeButton: a
    altPositiveButton: d
    gravity: 3
    dead: 0.001
    sensitivity: 3
    snap: 1
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: move_y
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: down
    positiveButton: up
    altNegativeButton: s
    altPositiveButton: w
    gravity: 3
    dead: 0.001
    sensitivity: 3
    snap: 1
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Fire1
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: left ctrl
    altNegativeButton: 
    altPositiveButton: mouse 0
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Fire2
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: left alt
    altNegativeButton: 
    altPositiveButton: mouse 1
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Fire3
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: left shift
    altNegativeButton: 
    altPositiveButton: mouse 2
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Jump
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: space
    altNegativeButton: 
    altPositiveButton: 
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: camera_x
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0
    sensitivity: 0.1
    snap: 0
    invert: 0
    type: 1
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: camera_y
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0
    sensitivity: 0.1
    snap: 0
    invert: 0
    type: 1
    axis: 1
    joyNum: 0
  - serializedVersion: 3
    m_Name: Mouse ScrollWheel
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0
    sensitivity: 0.1
    snap: 0
    invert: 0
    type: 1
    axis: 2
    joyNum: 0
  - serializedVersion: 3
    m_Name: move_x
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.19
    sensitivity: 1
    snap: 0
    invert: 0
    type: 2
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: move_y
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.19
    sensitivity: 1
    snap: 0
    invert: 1
    type: 2
    axis: 1
    joyNum: 0
  - serializedVersion: 3
    m_Name: Fire1
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: joystick button 0
    altNegativeButton: 
    altPositiveButton: 
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Fire2
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: joystick button 1
    altNegativeButton: 
    altPositiveButton: 
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Fire3
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: joystick button 2
    altNegativeButton: 
    altPositiveButton: 
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Jump
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: joystick button 3
    altNegativeButton: 
    altPositiveButton: 
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Submit
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: return
    altNegativeButton: 
    altPositiveButton: joystick button 0
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Submit
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: enter
    altNegativeButton: 
    altPositiveButton: space
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Cancel
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: escape
    altNegativeButton: 
    altPositiveButton: joystick button 1
    gravity: 1000
    dead: 0.001
    sensitivity: 1000
    snap: 0
    invert: 0
    type: 0
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_LThumbstickX
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 0
    type: 2
    axis: 0
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_LThumbstickY
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 1
    type: 2
    axis: 1
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_RThumbstickX
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 0
    type: 2
    axis: 2
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_RThumbstickY
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 1
    type: 2
    axis: 3
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_DpadX
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 0
    type: 2
    axis: 4
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_DpadY
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 1
    type: 2
    axis: 5
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_LIndexTrigger
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 0
    type: 2
    axis: 12
    joyNum: 0
  - serializedVersion: 3
    m_Name: Oculus_GearVR_RIndexTrigger
    descriptiveName: 
    descriptiveNegativeName: 
    negativeButton: 
    positiveButton: 
    altNegativeButton: 
    altPositiveButton: 
    gravity: 0
    dead: 0.001
    sensitivity: 1
    snap: 0
    invert: 0
    type: 2
    axis: 11
    joyNum: 0

```

これでこのプロジェクトで使用する共通の入力設定が出来ました。


