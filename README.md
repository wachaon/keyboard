# keyboard
*keyboard* は [*wes*](https://github.com/wachaon/wes) でキーボードを操作するモジュールです。

## インストール

```bash
wes install @wachaon/keyboard --bare
```

## コンパイル
*keyboard* は付属のC#のソースコードをコンパイルせずに実行できますが、コンパイルすることで
より高速に動作可能になります。

```bash
wes keyboard --compile
```

既定値ではコンパイルされた実行ファイルは *keyboard.exe* としてカレントディレクトリに配置されます。
より高度なコンパイルが必要な場合は `csharpscript/compile(input, options)` を使用してください。

## `send(keyCode)`

`keyCode` に数値を渡すことでそのキーコードを送信します。文字列が渡すと *WScript.Shell* の `SendKeys(keyCode)` を実行します。
*keyboard* には特殊キーを含むキーコードが内包されています。詳細は *index.js* を確認してください。

```javascript
const keyboard = require('keyboard')

keyboard.send(keyboard.VK_I) // i
keyboard.send(keyboard.VK_P) // p
keyboard.send('config{Enter}') // config + EnterKey
```

## `press(keyCode)` ` release(keyCode)`

`press(keyCode)` はキーボードを押す操作、 ` release(keyCode)` は離す操作をします。
ただし、 現状では `press` は押し続ける操作はしません。
`keyCode` は数値のみで文字列は受付しません。
