---
title: Firefox 108 for developers
slug: Mozilla/Firefox/Releases/108
l10n: 
  sourceCommit: f7eb57fe7b7063932cf93af70ffb70d063ac912d
---

{{FirefoxSidebar}}

このページでは、開発者に影響する Firefox 108 の変更点をまとめています。Firefox 108 は、2022 年 12 月 13 日にリリースされました。

## ウェブ開発者向けの変更点一覧

### HTML

- {{HTMLElement("source")}} 要素で、{{HTMLElement("picture")}} 要素の子要素であるときに [`height`](/ja/docs/Web/HTML/Element/source#attr-height) および [`width`](/ja/docs/Web/HTML/Element/source#attr-width) 属性をサポートしました。
  この機能は設定項目 `dom.picture_source_dimension_attributes.enabled` で制御しており、既定値を `true` にしました ({{bug(1795953)}})。

#### 廃止

### CSS

- 設定項目 `layout.css.trig.enabled` の既定値を `true` に設定して、[三角関数](/ja/docs/Web/CSS/CSS_Functions#trigonometric_functions) が使用可能になりました。
  `sin()`、`cos()`、`tan()`、`asin()`、`acos()`、`atan()`、`atan2()` 関数を使用できます ({{bug(1774589)}}、{{bug(1787070)}})。
- [数学関数](/ja/docs/Web/CSS/CSS_Functions#math_functions) で `pi` や `e` のようなよく知られた定数を使用できるようにするため、CSS の [`<calc-constant>`](/ja/docs/Web/CSS/calc-constant) 型を実装しました ({{bug(1682444)}}、{{bug(1787070)}})。
- 設定項目 `layout.css.container-queries.enabled` で、コンテナークエリーの長さの単位をサポートしました。
  この設定を `true` にすると、クエリーコンテナーの寸法に比例する長さの単位である`cqw`、`cqh`、`cqi`、`cqb`、`cqmin`、`cqmax` を使用できます。
  これらの単位について、詳しくは [CSS Container Queries](/ja/docs/Web/CSS/CSS_Container_Queries#container_query_length_units) の文書をご覧ください ({{bug(1744231)}})。
- 設定項目 `layout.css.font-variant-emoji.enabled` で、[`font-variant-emoji`](/ja/docs/Web/CSS/font-variant-emoji) プロパティをサポートしました。設定項目の既定値は `false` です。このプロパティで、絵文字を表示するときの既定の表現スタイルを設定できます ({{bug(1461589)}})。

#### 廃止

### JavaScript

#### 廃止

### HTTP

- [`Content-Security-Policy`](/ja/docs/Web/HTTP/Headers/Content-Security-Policy) HTTP ヘッダーの [`style-src-elem`](/ja/docs/Web/HTTP/Headers/Content-Security-Policy/style-src-elem) および [`style-src-attr`](/ja/docs/Web/HTTP/Headers/Content-Security-Policy/style-src-attr) ディレクティブをサポートしました。
  サーバーはそれぞれのディレクティブを使用して、`<style>` 要素や `rel="stylesheet"` を持つ `<link>` 要素のスタイルシート、および個々の要素に適用するスタイルの正当な提供元を指定できます ({{bug(1529338)}})。
- [`Content-Security-Policy`](/ja/docs/Web/HTTP/Headers/Content-Security-Policy) HTTP ヘッダーの [`script-src-elem`](/ja/docs/Web/HTTP/Headers/Content-Security-Policy/script-src-elem) および [`script-src-attr`](/ja/docs/Web/HTTP/Headers/Content-Security-Policy/script-src-attr) ディレクティブをサポートしました。
  サーバーはそれぞれのディレクティブを使用して、`<script>` 要素の JavaScript、および `onclick` などのイベントハンドラーのインラインスクリプトの正当な提供元を指定できます ({{bug(1529337)}})。

#### 廃止

### セキュリティ

#### 廃止

### API

#### DOM

#### Media、WebRTC、Web Audio

- [Web MIDI API](/ja/docs/Web/API/Web_MIDI_API) が、[安全なコンテキスト](/ja/docs/Web/Security/Secure_Contexts) で使用可能になりました。
  [`navigator.requestMIDIAccess()`](/ja/docs/Web/API/Navigator/requestMIDIAccess) を呼び出すとアクティブな MIDI デバイスを持つユーザーに対して、API を有効にするために必要な [Site Permission Add-On](https://support.mozilla.org/ja/kb/site-permission-add-ons) のインストールを促します。
  詳しくは {{bug(1795025)}} をご覧ください。

#### 廃止

### WebAssembly

#### 廃止

### WebDriver conformance (WebDriver BiDi, Marionette)

#### WebDriver BiDi

- [仕様書の変更](https://github.com/w3c/webdriver-bidi/pull/259) に従って、ログ項目のレベル `"warning"` を `"warn"` に改名しました ({{bug(1797115)}})。
- 名前が空文字列であるサンドボックスとともに `script.evaluate` および `script.callFunction` を使用するとき、既定のレルムを使用して評価するようになりました ({{bug(1793589)}})。
- `browsingContext.domContentLoaded` イベントをサポートしました ({{bug(1756610)}})。

#### Marionette

- `WebDriver:PerformActions` のために、ポインターアクションの `tiltX`、`tiltY`、`twist` プロパティをサポートしました ({{bug(1793832)}})。
- `WebDriver:GetElementText` が、整形された XML の要素のテキストを返さない不具合を修正しました ({{bug(1794099)}})。
- `HTMLDocument` を、`WebElement` の参照としてシリアライズしないようになりました ({{bug(1793920)}})。
- `WebDriver:NewWindow` が、`about:newtab` ではなく `about:blank` のタブを持つウィンドウを開くようになりました ({{bug(1533058)}})。

## アドオン開発者向けの変更点一覧

- [バージョン番号](/ja/docs/Mozilla/Add-ons/WebExtensions/manifest.json/version) が推奨するフォーマットに従っていない拡張機能がインストールされているときに、Firefox が警告を表示するようになりました ({{bug(1793925)}})。

### 廃止

### その他

## 過去のバージョン

{{Firefox_for_developers(107)}}
