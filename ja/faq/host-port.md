---
title: ホストとポート番号
description: ホストとポート番号を変更するには？
---

# ホストとポート番号を変更するには？

いくつかの方法で接続変数を変更することができます。以下、優先度の低い順ものから列挙しています:

## `package.json` 内の nuxt 設定を使う:

`package.json` 内:

```json
"config": {
  "nuxt": {
    "host": "0.0.0.0",
    "port": "3333"
  }
},
"scripts": {
  "dev": "nuxt"
}
```

## 環境変数 HOST と PORT を使う:

```js
"scripts": {
  "dev": "HOST=0.0.0.0 PORT=3333 nuxt"
}
```

**メモ**: より良いクロスプラットフォーム開発サポートのために [cross-env](https://www.npmjs.com/package/cross-env) を使うことができます。

インストール:

```bash
npm install --save-dev cross-env
```

```js
"scripts": {
  "dev": "cross-env HOST=0.0.0.0 PORT=3333 nuxt"
}
```

## 環境変数 NUXT_HOST と NUXT_PORT を使う:

HOST と PORT に似ていますが、HOST と PORT を他の用途に使っている場合に NUXT_HOST と NUXT_PORT を使います:

```js
"scripts": {
  "dev": "NUXT_HOST=0.0.0.0 NUXT_PORT=3333 nuxt"
}
```

## 引数として直接指定する:

```js
"scripts": {
  "dev": "nuxt --hostname myhost --port 3333"
}
```
