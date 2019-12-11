# README

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
* 画像のアップロードテスト

## What
1. fields_forを用いた画像の編集
    1. Edit画面表示時に、productに紐づいたimage(画像)を表示
    1. Edit画面に表示されたimageの変更
1. fields_forを用いた画像の削除
    1. オプション "allow_destroy"を付与
    1. params[:_destroy]をinputにhiddenで持たせる
    1. [:_destroy]の値が"1"になっていたら、データ送信時に該当データを削除


## Why
* メルカリ画像編集機能の細分化

## 参考記事
* [前回: fields_forとcarrierwave用いた画像の保存](https://github.com/ItsukiIshizuka/sample_create_image)
* [fields_forの上手な使い方](https://qiita.com/kouuuki/items/5daf2b5f34273d8457f7)
* [accepts_nested_attributes_forのオプション"allow_destroy"の使いかた](https://qiita.com/NateRive/items/be35c1a52aef8fd0d355)
* [accepts_nested_attributes_for時の子テーブルのバリデーション掛け方](https://stackoverflow.com/questions/37622669/accepts-nested-attributes-for-with-validations-and-using-find-or-create-by)

