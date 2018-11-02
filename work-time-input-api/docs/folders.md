# フォルダー構成

generatorが作成した各フォルダについての説明を記載。

## public/

公開するファイルを格納する場所。
API毎にフォルダを作成し、その中に格納する。  
以下、「user」APIの格納例。

```shell
.
└── public/    
    └── user/
        ├── user.jpg
        ├── user.js
        └── user.css
```

---

## server/

サーバーのコードを格納場所。
エントリポイントの「index.ts」、各APIにルーティングする「routes.js」を格納する。

### server/api/
API関連ファイルを格納する。

#### server/api/controllers

API毎にフォルダを作成し、その中に以下の2ファイルを格納する。

##### router.ts
* controller.tsの各コントローラにリクエストを振り分ける。

##### controller.ts
* リクエストの中身をサービスに渡し、サービスの応答を待つ。  
応答のコールバックでレスポンスを作成する。

#### server/api/services

コントローラから呼び出されるサービスを格納する。
ファイル名の命名規則は以下。
```
API名.service.ts
```
### server/common

サーバ本体の「server.ts」やロガー等の共通で扱うものを格納する。

---

## test/

テストコードを格納場所。
API毎にファイルを作成する。
命名規則は以下。
```
API名.controller.ts
```
---