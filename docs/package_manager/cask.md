## Cask
[Cask](https://github.com/cask/cask) はファイルにインストールしたいパッケージ名を記述し，コマンドラインからコマンドを叩くことでパッケージをインストールする．  
パッケージ管理ツールとして紹介されることが多いが，プロジェクト管理用のツールの 1 つらしい．  
自分はパッケージ管理ツールとしての側面しか知らないため，ここでもその方向で説明していく．

### インストール
   インストールするには，

   ```
   $ curl -fsSL https://raw.githubusercontent.com/cask/cask/master/go | python
   ```

   を実行するか，macOS ならば

   ```
   $ brew install cask
   ```

   Homebrew でインストールすることもできる．

   curl でインストールした場合，パスを通す必要があるかもしれない．

### 初期化
   始めに `~/.emacs.d` で Cask を初期化する必要がある．  
   以下のコマンドを実行すると，

   ```
   $ cd ~/.emacs.d
   $ cask init
   ```
     
   `~/.emacs.d/Cask` というファイルが生成される．
### インストールするパッケージの指定
   `Cask` ファイルには，最初からいくつかのパッケージが書かれている． 

   自分の環境で実行した場合に生成された `Cask` ファイルは以下のようになっていた．

   ```
   (source gnu)
   (source melpa)

   (depends-on "bind-key")
   (depends-on "cask")
   (depends-on "dash")
   (depends-on "drag-stuff")
   (depends-on "exec-path-from-shell")
   (depends-on "expand-region")
   (depends-on "f")
   (depends-on "flycheck")
   (depends-on "flycheck-cask")
   (depends-on "htmlize")
   (depends-on "idle-highlight-mode")
   (depends-on "magit")
   (depends-on "multiple-cursors")
   (depends-on "nyan-mode")
   (depends-on "pallet")
   (depends-on "popwin")
   (depends-on "prodigy")
   (depends-on "projectile")
   (depends-on "s")
   (depends-on "smartparens")
   (depends-on "smex")
   (depends-on "use-package")
   (depends-on "web-mode")
   (depends-on "yasnippet")
   ```

   どれもメジャーな（？）パッケージで，あって困ることはないと思うので，特に消す必要はないだろう．  
   `Cask` ファイルを見るとわかるが，Cask ではインストールしたいパッケージを

   ```
   (depends-on "package name") 
   ```

   の形で記述する．バージョンの指定やリポジトリの URL を指定することもできる．

   ```
   (depends-on "package name" "version")
   (depends-on "package name" :git "url")
   ```
     
   また，リポジトリの追加も行える．
     
   ```
   (source repository)
   ```
### パッケージのインストール
   `Cask` ファイルにインストールしたいパッケージを記述したら，

   ```
   $ cd ~/.emacs.d
   $ cask install
   ```

   を実行すると，パッケージがインストールされる．
### Emacs の初期化ファイルの設定
   Cask でインストールしたパッケージを Emacs から使えるようにするために， `~/.emacs.d/init.el` に次のコードを追加する必要がある．
     
   ```
   ;; macOS の場合
   (require 'cask)
   ;; Linux の場合
   ;; (require 'cask "~/.cask/cask.el")

   (cask-initialize)
   ```

   これにより，Cask でインストールしたパッケージが Emacs から利用可能になる．
### コマンド
     
   - パッケージのアップデート
     ```
     $ cask update
     ```
   - Cask のアップグレード
     ```
     $ cask upgrade-cask
     ```
   - 古くなったライブラリ一覧
     ```
     $ cask outdated
     ```
   - パッケージ一覧
     ```
     $ cask list
     ```
    より詳しいことは，[Cask](http://cask.readthedocs.io/en/latest/index.html) を見てください．

### TODO Pallet

### 参考
- [vdeep - Emacs Cask でパッケージ管理してみよう](http://vdeep.net/emacs-cask)
- [Qiita - brew install cask した場合の cask.el の場所](http://qiita.com/toshiwo/items/84cfa5e940ffdd69afaa)
- [理系学生日記 - Cask とは何であるのか、および init.el が非常にシンプルになった件](http://kiririmode.hatenablog.jp/entry/20141228/1419762171)
