---
title: XMLHttpRequest.status
slug: Web/API/XMLHttpRequest/status
l10n:
  sourceCommit: b5b33acd44e7bb9c7be2efc75ba9a04b8bf8b2b2
---

{{APIRef('XMLHttpRequest')}}

**`XMLHttpRequest.status`** プロパティは読み取り専用で、 `XMLHttpRequest` のレスポンスにおける数値の HTTP [ステータスコード](/ja/docs/Web/HTTP/Status)を返します。

リクエストが完了する前は、 `status` の値は 0 になります。 `XMLHttpRequest` がエラーになった場合も、ブラウザーはステータスとして 0 を返します。

## 値

数値です。

## 例

```js
const xhr = new XMLHttpRequest();
console.log('UNSENT: ', xhr.status);

xhr.open('GET', '/server');
console.log('OPENED: ', xhr.status);

xhr.onprogress = () => {
  console.log('LOADING: ', xhr.status);
};

xhr.onload = () => {
  console.log('DONE: ', xhr.status);
};

xhr.send();

/**
 * 出力結果は以下の通り。
 *
 * UNSENT: 0
 * OPENED: 0
 * LOADING: 200
 * DONE: 200
 */
```

## 仕様書

{{Specifications}}

## ブラウザーの互換性

{{Compat}}

## 関連情報

- [HTTP ステータス](/ja/docs/Web/HTTP/Status)の一覧
- [HTTP](/ja/docs/Web/HTTP)
