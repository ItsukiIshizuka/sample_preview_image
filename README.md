# README

## What
1. 画像アップロード即時プレビュー機能を実施
    1. アップロードと同時にプレビュー生成
    1. 画像の下に"削除ボタン"が付与された状態で生成される *** *今回は削除機能の実装なし***

## Why
* メルカリ画像編集機能の細分化

## gem list
* pry-rails
* jquery-rail https://github.com/rails/jquery-rails
* haml-rails https://github.com/haml/haml-rails
* carrierwave

## 構築手順
* productテーブル作成(name:string)
* imageテーブル作成(image:string, product_id:外部キー)
* 親 productモデル 子 imageモデル で構築
* "carrierwave"導入後、以下のコードを実行

```
rails g uploader images
```
* image モデルに以下の一文を追加

```
mount_uploader :image, ImagesUploader
```

## 参考記事
* [jQueryでcssプロパティを動的に変化](https://qiita.com/kazTera/items/ab5dd9fb5b2579b25c4d)
* [CarrierWaveでアップロード画像の即時プレビュー](https://kurose.me/carrierwave-preview/)
### jQuery
* [onload](https://techacademy.jp/magazine/15558)
* [readAsDataURL](https://lab.syncer.jp/Web/API_Interface/Reference/IDL/FileReader/readAsDataURL/)
* 