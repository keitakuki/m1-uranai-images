# m1-uranai-images

「夢叶うらない」(Gemini Canvas 版)が読む画像だけを置くリポジトリ。GitHub Pages で公開する。

公開 URL: https://keitakuki.github.io/m1-uranai-images/

| パス | 中身 |
| --- | --- |
| `brand/m1-logo-2026.png` | M-1 グランプリのロゴ(各画面の上・保存用画像のいちばん下) |
| `brand/yume-logo.png` | 題字の仮ロゴ「M-1 / 夢叶うらない」1600×475(入口・夢を入力する画面・保存用画像のいちばん上)。作り方: `gemini-canvas/make_input_assets.py --logo <ロゴの png> <このリポジトリ>` |
| `cards/sm/<id>.webp` | 絵札の小さい方 384×512(棚・3 枚が表になる画面) |
| `cards/<id>.webp` | 絵札の大きい方 768×1024(結果の画像に描き込む) |

`<id>` はコンビの id(daio, dondecolte, evers, gokai, ichigo, kabe, kaname, konya, magical, milkboy, ozora, sentinel, shinku, shoganeko, stamina, takuro, zero)。

## 保存用画像(Gemini に渡すインプット画像)の素材 `input/`

| パス | 中身 |
| --- | --- |
| `input/bg-tate.webp` | 背景(支給素材 `背景png/縦.png`、1080×1920) |
| `input/cards/<id>.webp` | 絵札(枠・名前入り、高さ 1002)。今は evers・takuro・dondecolte。棚・3 枚の画面・保存用画像のどれもこの絵を使う。2026-11-13 にモチーフ入りの絵(支給素材 `261113_…素材お渡し/絵札/*.png`)に差し替え。作り方: `gemini-canvas/make_input_assets.py --cards <絵札のフォルダ> <このリポジトリ>` |
| `input/footer.webp` | いちばん下の「Made with Google Gemini」(参考画像「縦-大」から切り出し) |

作り方: `gemini-canvas/make_input_assets.py <支給素材のフォルダ> <このリポジトリ>`。

## 画像の差し替え

1. 同じパス・同じファイル名で上書きする(大きい方と小さい方の両方)。
2. コミットして push すると、1 分ほどで公開 URL に出る。
3. GitHub Pages はブラウザに最大 10 分キャッシュさせるので、Canvas 側の画像 URL の末尾(`?v=...`)を新しい値に変えて、古い絵が出ないようにする。

`.nojekyll` は GitHub Pages の Jekyll 処理を止めるためのもの(消さない)。
