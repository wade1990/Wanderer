# Wanderer #

diabloっぽいネトゲつくろうとしたもの  
GoogleChrome/Firefox4.0以上等、WebSocket対応ブラウザに対応。  
スマホは確認してないけどキーボード必須。  

![ss](https://github.com/mizchi/ws-netgame/raw/master/shared/doc/ss2.jpg "ss")

## How to play ##
クラスと種族を選択してキャラ作成  

### ステータスの意味
* str : 筋力 HP/武器による攻撃の影響
* int : 賢さ MP/魔法による攻撃の影響
* dex : 器用 移動速度/命中率/一部のスキルの威力に影響

### Race ###

* Human 平均的 
* Elf   intが高い
* Dwarf strが高い

### Class ###
#### Lord
* 武器と魔法のデュアルクラス
* 回復魔法

#### Warrior
* 物理型
* ノックバック攻撃

#### Sorcerer 
* 魔法型
* 超射程魔法 ＋ 範囲魔法

数字キー[1, 2, 3, 4]で技選択。
敵に近寄ると自動で発動
緑が自分。青が他のプレーヤー。赤がモンスター。

## Install ##
$ git clone git://github.com/mizchi/ws-netgame.git  
$ cd ws-netgame  
$ npm install .  
$ mv config-sample.coffee config.coffee  
$ node server.js  

## ChangeLog ##

### NEXT

### v.0.0.10
* knockout.jsをv1.3devからv2.0.0へ
* ディレクトリの構造を変更
* server/client双方から参照するsharedディレクトリを追加

### v.0.0.9 
* WebSocetネームペース間で、フロア移動ができるように
* スキルの着脱を可能に
* モンスターのバリエーションを追加
* node v0.6 系に対応

### v.0.0.8 
* ダンジョン生成アルゴリズムを変更

### v.0.0.7 
* WebSocketのブロードキャストネームスペースをダンジョン階層ごとに分割

### v.0.0.6 
* 思い出しながらREADME書いてる
* underscore.js導入

### v.0.0.5
* クラスとレーシャルを実装(現状ステータスに補正がつくのみ)
* クラスごとにスキルを割り振り
* Monsterクラスでレーシャルとクラスのみでモンスター定義できるようにした
* Monsterクラスが初期化Lvに応じて強化されるようになった。

### v0.0.4
* Char定義クラスを分割
* Knockbackスキルを実装
* ChainLightningスキルを実装
* スキルポイントの割り振りを実装

### v0.0.3 
* エンジン側でビュースケールを除去して可変で表示できるように。
* 暫定UIを実装

### v0.0.2
* ログインを実装
* 拡張に備えてコードをリファクタリング
* nstore採用+Mongo/Redisの依存を排除

### v0.0.1
* 公開

## TODO ##
気が向いたものから順に実装される

* スキルレベルに応じたスキル強化実装
* クライアント、D&Dでスキル付け替え
* コリジョンマップとオブジェクトマップの分割
* テストコードを書く
* マップ生成アルゴリズムの見直し
* サーバー側からクライアントへアニメーション伝達の仕組みを定義
* アイテムボックスを実装
* エゴアイテム生成アルゴリズムを実装
* プレーヤーネームのバリデーション
* ドキュメントを書く


## 既知のバグ ##
* レベルが挙がるとパスワードが書き換わってログインに失敗する
* パッシブスキルを装備できてしまう
* マップ間移動で、既にそのセッションで使用したネームスペースに戻ろうとするとバグる。


## Ideas ##
やりたいこと  

* Racialに応じたスキル
* ハイトの概念を導入
* スキルを色(属性)で分類してマスタリを簡易化
* 時間に応じてポーションを生成
* オークション
* プレーヤーに陣営を設定して対立するように(WoW風)
* コンソールクライアントを用意 ref: https://github.com/mscdex/node-ncurses
* ゲームコンセプトと世界観を設定