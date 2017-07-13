## package.el
Emacs 24 から標準で使えるパッケージ管理ツール．  
自分はまともに使ったことがないので， [package.el](http://emacs-jp.github.io/packages/package-management/package-el.html) を参考に進めてみる．

単体でパッケージをインストールする方法は簡単で，

```
M-x package-install
```

を実行する．すると `Install package:` とミニバッファに表示される．  
ここで `TAB` を押すとパッケージの一覧が表示されるため，その中からインストールしたいパッケージを見つけ，
パッケージ名を入力することでパッケージをインストールすることができる．

また，パッケージを一覧から複数選択してインストール，アンインストールしたい場合には，

```
M-x package-list-packages
```

を実行すると，パッケージの一覧が表示される．  
パッケージ一覧が表示されたときに行える操作は次のようになっている．
    
| キー     | 概要                               |
|----------+------------------------------------|
| =r=      | パッケージ一覧の更新               |
| =i=      | インストールマークをつける         |
| =d=      | 削除マークをつける                 |
| =~=      | 古いパッケージに削除マークをつける |
| =u=      | マークを除去する                   |
| =x=      | マークの実行                       |
| =?=      | パッケージの概要表示               |
| =U=      | アップグレード                     |
| =n=      | 次の行へ移動                       |
| =p=      | 前の行へ移動                       |
| =h=      | help                               |
| =q=, =z= | 終了                               |

`package.el` はデフォルトで [elpha.gnu.org](http://elpa.gnu.org/packages/) からパッケージを取得する．  
見てもらえればわかるが，登録されているパッケージが少ない．  
[package.el](http://emacs-jp.github.io/packages/package-management/package-el.html) で説明されているようにリポジトリを追加する．各リポジトリについては，リンク先を読むとわかる．

```elisp
(require 'package)

(add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/") t)
(add-to-list 'package-archives '("melpa-stable" . "https://stable.melpa.org/packages/") t)
(add-to-list 'package-archives  '("marmalade" . "http://marmalade-repo.org/packages/") t)
(add-to-list 'package-archives '("org" . "http://orgmode.org/elpa/") t)

(package-initialize)
```
    
`elpha` 以外のリポジトリからパッケージをインストールすることができるようになる．  
起動時に自動で指定したパッケージをインストールするためには， `~/.emacs.d/init.el` に以下のように記述するとよい．
    
```elisp
(require 'package)
  
(add-to-list 'package-archives '("melpa" . "https://melpa.org/packages/") t)
(add-to-list 'package-archives '("melpa-stable" . "https://stable.melpa.org/packages/") t)
(add-to-list 'package-archives  '("marmalade" . "http://marmalade-repo.org/packages/") t)
(add-to-list 'package-archives '("org" . "http://orgmode.org/elpa/") t)

(package-initialize)

(defvar my-install-package
  '(
    helm
   ))
    
(dolist (pkg my-install-package)
  (unless (package-installed-p pkg)
    (package-install pkg)))
```

この例では， `helm` がインストールされていない場合にのみ `helm` のインストールを行う．

### 参考

- [Emacs JP - package.el](http://emacs-jp.github.io/packages/package-management/package-el)
- [Qiita - init-loader.el と package.el を導入して快適 Emacs ライフ](http://qiita.com/catatsuy/items/5f1cd86e2522fd3384a0)
- [wagavulin's blog - package.el で自動インストール](http://blog.wagavulin.jp/entry/2016/07/04/211631)
