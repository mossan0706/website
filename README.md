# website

できるできる詐欺になると困るので、新卒かつ配属後 2 ヶ月くらいから新製品のメイン開発者をやった時のアプリを技術的な部分で当たり障りなく再現。（直属の先輩がいなくなって 95%くらい私のコードだったのは内緒）
それをさらに拡張してウェブサイトを作成します。

# 環境構築

## docker-desktop をインストールする

https://www.docker.com/products/docker-desktop/

ここで落とす、ついでに起動

## このリポジトリをローカルに持ってくる

このリポジトリをローカルに持ってくる（圧倒的 GUI 派（タイポ王）なので [GitHub Desktop](https://desktop.github.com/) で説明）

1. [リポジトリに移動](https://github.com/mossan0706/website)
2. 緑色の Code ボタンを押す
3. Open with GitHub Desktop を押す
4. 大体の場合、そのまま指示にしたかっクローンする

## env ファイルの作成

プロジェクトルート（C:\Users\(あなたの名前)\Documents\GitHub\website）に `.env` という名前でファイルを作成し、下記を記述

```.env
# 環境を指定（今はdevelopment or productionのみ対応
# development はnest.jsを--watchモードで、nextをnext devで起動する
NODE_ENV=development

POSTGRES_USER=postgres
POSTGRES_PASSWORD=password
POSTGRES_DB=postgres
```

## イメージの作成、コンテナの起動

（ここからはコマンドで、、、こっちのほうが動作が少ないんですよ、、、）

```sh
cd "C:\Users\(あなたの名前)\Documents\GitHub\website" # macは ~/Documents/GitHub/website かな？

# イメージを作成
docker-compose build

# コンテナの起動
docker-compose up -d
```

http://localhost:3000/
http://localhost:4000/

ここに行って起動してればそれで終わり！！！

# コーディング規約（戒め）

基本、設定されている ESlint に従う

ID: dbaeumer.vscode-eslint
リンク: https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint

レコメンドで上記拡張機能が入ってるから保存すればきれいになるやろ？、、、とは思いつつ、手動での方法も下記に

```sh
cd frontend
npm run lint
```

```sh
cd backend
npm run lint
```

（命名規則など真面目な奴は後で追記します）
