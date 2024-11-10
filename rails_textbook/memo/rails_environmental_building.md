## Rails の環境構築

### Ruby と Rails のインストール

asdf で Ruby をインストール

```shell
asdf plugin list all | grep ruby    // rubyのプラグインを表示
asdf plugin add ruby https://github.com/asdf-vm/asdf-ruby.git    // rubyのプラグインをインストール
asdf list all ruby                  // インストール可能なrubyバージョンを表示
asdf install ruby 3.1.0             // rubyのバージョンを指定してインストール
asdf global ruby 3.1.0              // グローバルで使用するrubyバージョンを指定
```

<br>

以下のコマンドで Rails をインストール

```shell
gem i rails    // Railsをインストール
```

<br>

Rails は `~/.asdf/shims` にインストールされるため、以下のコマンドを実行し、PATH を通す

```shell
echo 'export PATH="$HOME/.asdf/shims:$PATH"' >> ~/.zshrc    // .zshrcにexportコマンドを記入
source ~/.zshrc    // 現在のshellに.zshrcを読み込み
```

<br>

### Rails プロジェクトのコマンド

#### プロジェクトの作成

以下のコマンドで Bundler をインストール

```shell
gem install bundler    // Bundler をインストール
```

<br>

以下のコマンドでプロジェクトを作成

```shell
rails new SampleProject    // SampleProjectを作成
```

<br>

#### web サーバーの起動

以下のコマンドで Rails のサーバーを起動

```shell
rails s    // Railsのサーバーを起動
```

※ 省略せずに `rails server` でも良い<br>

<br>

#### ページの作成

以下のコマンドで ページを作成する

```shell
rails g controller hello index    // ひな形となるファイルを生成
```

<br>

※ もしも rails g コマンドを打ち間違えて違うファイルを作成してしまった時は、打ち間違えたコマンドの g の部分を d にして再実行すると、rails g コマンドで作成したファイルをまとめて削除してくれます

#### リクエスト処理の流れ

rails へリクエストが送られると、<br>
routes -> controller -> view の流れで処理が行われる<br>

#### 変数

@はじまりの変数のことをインスタンス変数と言います<br>
インスタンス変数を使用することで、コントローラからビューへ情報を伝えることができる<br>
@はじまりでない変数はローカル変数と呼ばれ、メソッドを抜けると使えなくなる<br>
