# EtherCAT_Obj_Latch

2023/06/12

## タッチプルーブオブジェクト

* 60B8h:Touch probe function
* 60B9h:Touch probe status
    - bit0-7:touch prove1　→ モーション命令のラッチID選択の _eMC_TRIGGER_LATCHID(_mdLtch1)
    - bit8-15:touch prove2　→ モーション命令のラッチID選択の _eMC_TRIGGER_LATCHID(_mdLtch2)

<b>Object Dictionary 定義</b>
[!TP_OD](./pic/touchprove_OD.png)

## MC_Home
<b>原点復帰動作 × MCE機能</b>
[!MC_HOME_MCE](./pic/MC_HOME_MCE.png)

<b>コメント</b>
&emsp;MCE機能 = オブジェクト?ステータス信号も含む?

(予想)
* ラッチ機能：60B8h
* ラッチステータス：60b9h
* ラッチ位置1:60BA
* 正転側駆動禁止入力：60E0h?
* 逆転側駆動禁止入力：60E1h?
* 原点近傍入力：←これがIAI製品では実現できないということ?
← 外付けセンサーの入力信号だったら代わりに使うことはできそうだけど...
* エンコーダーZ相検出：
* 外部ラッチ入力1:

⇒ アイエイアイの内部信号として持っていないものを外部センサーを使って実現するということ?<TODO>
⇒ その場合、既存のシステムのアプリケーションをそのまま実現できないのか?
⇒ ドライバー側でフィードバック座標位置のクリアーをしない仕様はあり?
⇒ そもそも仕様的に可能?

