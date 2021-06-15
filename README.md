# blog ※記述中！！！！
###### tags: `勉強会`
## 使用技術
記事生成：hugo
記事の記述：markdown

## Hugoをまだダウンロードしてない方
 [こちら](https://)

## git_cloneするときの注意
初めてダウンロードする時
```
git clone --recursive {クローンしたいリポジトリ}
```
をしないと使用しているsubmoduleがcloneされません。
間違って普通にcloneしてしまったときは
```
git submodule update --init --recursive
```
> [引用元](https://qiita.com/kentarosasaki/items/3e670567c0512b9d411e)

## 記事作成手順

1. ターミナルでblogのディレクトリ内に移動
`Workspace/private/blog`
2. `hugo new "タイトル".md`を入力．
拡張子に注意！
3. 作成したファイルを開いて記事を書く.
4. ターミナルで`hugo`を入力
5. gitにデータをあげる
6. 終わり
