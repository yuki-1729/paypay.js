# paypay.js - WIP
PayPay(paypay.ne.jp)用の非公式APIライブラリ(JavaScript版)

## 可能な操作
- ログインを開始する(`loginStart("08012345678", "qwerty")`);
- ログインを完了する(`loginConfirm("https://www.paypay.ne.jp/portal/oauth2/l?id=xxxxxx")`);
- 残高を取得(`getBalance()`);
- 履歴を確認(`getHistory()`);
- プロフィールを確認(`getProfile()`);
- QRコードを取得(`getP2PCode()`);
- 送金リンクを確認(`getLink("XXXXXXXXXXXXXXXX")`);
- 送金リンクを作成(`createLink(10)`);
- 送金リンクを受け取る(`acceptLink("XXXXXXXXXXXXXXXX")`);
- 送金リンクを辞退する(`rejectLink("XXXXXXXXXXXXXXXX")`);

## サンプル
### Login
```js
const { PayPay } = require("paypay");

let paypay = PayPay();

(async() => {
	await paypay.getPayPayVersion();
	await paypay.loginStart("08019816837", "qwerty");
	let token = await paypay.loginConfirm("https://www.paypay.ne.jp/portal/oauth2/l?id=xxxxxx");
	console.log(token);
})();
```

## ライセンス
```
MIT License

Copyright (c) 2024 Yuki

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
