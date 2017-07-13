##  雑にパッケージ紹介
ここではいくつかのパッケージを名前を挙げる程度に紹介する．  
詳細についての他の節で述べるつもりである．

- ddskk  
  日本語入力に特化した IME の一つ．  
  SKK は Simple Kana to Kanji conversion program の略称である．
  
  > SKI コンビネータ計算において、SKK という式は恒等関数と同じ結果となる。
  > 作者の佐藤自身も、SKK=I を念頭に置いて、「ユーザの頭の中にある日本語のテキストを，なるべくストレスなしに，そのままディスプレイに出力するプログラムにしたいという気持ちが込められている」としている。
- magit  
  Emacs における Git クライアント．
- elscreen  
  Emacs にタブを導入する．
- powerline  
  みんな大好き powerline を Emacs でするやつ．
- anzu  
  デフォルトの Emacs だと文字列を検索したときにマッチ数がわからない．  
  それを表示するようにできるパッケージ．  
  それだけでなくていい感じの置換コマンドもある．
- undo-tree  
  undo と redo の履歴を木を見ながら操作できる．
- undohist  
  Emacs を再起動しても undo ができる．
- recentf  
  Emacs 標準パッケージ．最近開いたファイルを簡単に開くことができる．
- recentf-ext  
  recentf をいい感じにしてくれる．
- Projectile  
  Git などのプロジェクト管理ツールにより管理されているディレクトリを認識して，管理されているファイルをいい感じに検索できる．
- auto-complete  
  Emacs で補完を行うためのパッケージ．
- company  
  auto-complete と同じく補完を行うためのパッケージ．  
  国内では auto-complete ユーザが多いが，海外だと company の方が多いらしい [要出典]．
- flycheck  
  コードのリアルタイムシンタックスチェックを行うためのパッケージ．  
  同様のことを行うパッケージで flymake があるが，flycheck の方がいいらしい．
- org  
  Emacs を使っていて org-mode を使わないのはもったいない．
- 補完インターフェース 
  - anything  
    Emacs で行う操作に統一的なインターフェイスを提供する．
  - helm  
    anything のフォーク． anything が安定性に重視を置くのに対して，helm は急進的なようだ．  
    今日においては helm が人気なように思われる．
  - ivy  
    これは使ったことがないので，どのような感じなのかわからない．  
    このサイトを作っていくに当たって試してみようと思う．  
    作られたのは，比較的最近なようだ．
  - ido  
    Emacs 標準パッケージ．シンプルな印象．あまり弄ったことない．  
    他にも特定の言語に依存しない便利なパッケージがあるけど，ここではこの辺にしておく．

*参考*
- [wikipedia - SKK](https://ja.wikipedia.org/wiki/SKK)
- [るびきち「新生日刊 Emacs」 - #11 Emacs に革命を起こすパッケージ「helm」（Software Design 2015 年 3 月号掲載記事）Emacs helm インストール 設定 使い方](http://emacs.rubikitch.com/sd1503-helm/)
