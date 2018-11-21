# ReasonML 學習指引

Written by @jihchi 2018-11-13

> 撰寫本文的動機在於，希望給具備 React Web Application 開發經驗的 JavaScript Developers 學習及導入 ReasonML 的快速上手指引。閱讀完本文及相關資源後，便可開始進行 ReasonML 的 React Web Application 開發。

## 起手入門

ReasonML 是由 Facebook 基於 OCaml 語言所發展出來的新語法（syntax）及工具鏈（toolchan）。OCaml 是一個發展至今已有 20 多年歷史的 Functional Programming Language 。現今 ReasonML 的一項重點應用即是 JavaScript / Web Development 。

請先依照以下步驟閱讀文件，閱讀完畢之後，便可對於語言及相關工具、函式庫有基礎認識：

1. 首先，請前往 ReasonML 的「[What & Why](https://reasonml.github.io/docs/en/what-and-why)」開始，讀完後對於 ReasonML 這個語言有初步瞭解。
1. 瞭解 ReasonML 只是表面（syntax）而骨子（backend）裡是 OCaml 之後，接下來的問題便是，如何產生出 JavaScript 程式碼及如何與 JavaScript 交互作用？同樣請前往 BuckleScript 的「[What & Why](https://bucklescript.github.io/docs/en/what-why)」開始，讀完後對於 BucketScript 產生 JavaScript 程式碼有更進一步的認識。
1. ReasonML 對 React / JSX 支援及相容程度很高，請前往 ReasonReact 的「[What & Why](https://reasonml.github.io/reason-react/docs/en/what-and-why)」，瞭解與 JavaScript 的 React 之間差異。

除了上述文件之外，下列兩個 API 文件往後的開發會時常交互查詢：

- ReasonML API documentation: https://reasonml.github.io/api/
- BuckleScript API documentation: https://bucklescript.github.io/bucklescript/api/

需要注意的是，BuckleScript API 範例 signature 使用的是 OCaml 語法，若不習慣 OCaml 語法可以安裝 [reason-tools](https://github.com/reasonml/reason-tools) 這套 [Chrome](https://chrome.google.com/webstore/detail/reason-tools/kmdelnjbembbiodplmhgfjpecibfhadd) / [FireFox](https://addons.mozilla.org/en-US/firefox/addon/reason-tools/) extension 即時切換語法，方便閱讀。

Web Application 開發可以從 BuckleScript 所提供的 API 找起，例如 [Js](https://bucklescript.github.io/bucklescript/api/Js.html)、[Belt](https://bucklescript.github.io/bucklescript/api/Belt.html) 等模組，若找不到也可以從 ReasonML 所提供 API 尋找，例如 [Pervasives](https://reasonml.github.io/api/Pervasives.html)、[Printf](https://reasonml.github.io/api/Printf.html) 等模組 。
> 💡 API 文件有 index of values（[BuckleScript](https://bucklescript.github.io/bucklescript/api/index_values.html)、[ReasonML](https://reasonml.github.io/api/index_values.html)）頁面，可以列出所有支援的 functions，開啟頁面使用 Browser 內建搜尋字串快速尋找。

> ![index of values - ReasonML](raw/index_of_values_re.jpg)
＄
## 如何撰寫 BuckleScript bindings？

對於採用 ReasonML 開發 Web Application，能夠沿用既有 JavaScript 十分重要，無論是 JS 的 3rd-party 函式庫或“逃生”用 JS code。

| 預期產生的 JS Code | ReasonML | 備註 |
| :------------ |:---------------:|:---------------:|
|
```js
window.location.href
```
 |
```re
[@bs.val] [@bs.scope ("location")] external href : string = "href";
```
 | 詳細可參考 https://bucklescript.github.io/docs/en/bind-to-global-values |

## Topics TBD
- Write unit test for component created by ReasonReact
- What’s ‘a, ‘b, etc. meaning on function signature? It’s difficult to understand API document.
- What’s .rmi extension? (ReasonML FAQ has answered)
- 有什麼好用的常用的 library, bs-json, graphQL ppx...
