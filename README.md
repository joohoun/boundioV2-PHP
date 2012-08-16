boundioV2 PHP Library
====
boundio PHP Library V2 にはプッシュ音認識機能が追加されています。<br />
既存の「boundio PHP Library」のboundio ver2対応バージョンです。

API
--------
以下のAPIに対応しています。

* call
* status
* file/post

利用方法
--------

    // 認証情報設定
    Boundio::configure('userSerialId', '[ユーザーシリアルID]');
    Boundio::configure('appId', '[アプリケーションキー]');
    Boundio::configure('authKey', '[ユーザー認証キー]');

    // 電話発信
    Boundio::call('[電話番号]', '[再生ファイル①%%再生ファイル②]');
     -> Boundio::call('03-1234-5678', 'file(000001)%%file(000002)');
    
    // プッシュ音認識機能の利用方法
    Boundio::call('[電話番号]', '[再生ファイル①%%プッシュ音認識%%再生ファイル②]');
     -> Boundio::call('03-1234-5678', 'file(000001)%%gather(30,4)%%file(000002)');
    　既存のcast設定に「gether(30,4)」を設定することだけでプッシュ音認識機能の利用が可能になります。
    
Functions
--------

* **configure** (*string $key, string $val*)
* **call** (*string $tel_to, string $casts*)<br />
  指定された電話番号へ発信
* **status** (*string $id, string $start, string $end*)<br />
  指定されたIDまたは期間の履歴を取得します
* **file** (*string $text, string $filepath, string $filename*)<br />
  指定された文字を合成したり、ファイルをアップロードします。