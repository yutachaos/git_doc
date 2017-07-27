# gitとは
- wiki見ろ
	- https://ja.wikipedia.org/wiki/Git
- linuxを開発したライナストーバルズがlinuxカーネルの開発のために開発した分散型バージョン管理システム

- linuxの開発は多数の開発者がいて、各々の開発者が自分のソースコードの管理・統合をするのが非常に困難になる。その管理のために開発されたソフトウェアです。

# 分散型バージョン管理システムとは
- リモートサーバ等にある中心リポジトリの完全なコピーを手元（ローカル環境）に作成して、そのローカルリポジトリを使って作業を行う。

- ?
- 何それ?

# gitの利点
- gitはローカルとリモート両方に全てのファイル履歴を持っています。つまりサーバが壊れたとしても誰かのデータが残っていれば復元可能!
- 履歴差分管理
	- ファイルデータの保存履歴、テキストデータの差分を表示する機能があり、いつどこで誰がそのデータを替えたのが追いやすい。gitがbackupを取ってくれるので昔のデータに戻ることも出来ます。
- エンジニアに認められる。
	- 非エンジニアで使えるだけでこいつは出来る奴と認められるでしょう。
	 
## gitの概念図
- [画像を差し込み]

## git用語
- branch
	- 管理するファイルをひとまとめにしたもの ゲームのセーブデータみたいな感じ
- repository
	- 履歴管理するbranchをまとめたもの
- local repository
	- local(操作する人のPC)に保存されているrepository 
- remote repository
	- remote(共有サーバー)に保存されているrepository
- git add
	- 保存するファイルを追加すること
- git commit 
	- git addしたファイルをlocalのbranchに保存すること   
- git push
	- localに保存した内容をremote repositoryに反映、コピーすること
- git branch
	- gitにbranchを作成するコマンド セーブデータの作成
- git checkout 
	- branchの切り替えをするコマンド セーブデータのロード 
- git merge
	- 他の人が作ったbranchと内容を統合する
- git fetch
	- remote repositoryにあるデータを取得する
	 
- git pull 
	- git fetch + git merge remote repositoryから最新を取得した上でmergeする。
	
## まず使ってみよう
- gitの基本コマンド
	- リポジトリの作成
		- git init
	- クローンする
		- 共有リポジトリから、ローカルリポジトリにクローンする方法です。
			- git clone {repository名}
	- ファイルの追加（コミットの準備）
		- 追加したいファイルの選択
			- git add {file名}
	- ファイルのコミットする
		- branchへの保存 
			- git commit -m 'メッセージ' 
	- プッシュ
		- ローカル(自分のパソコン)に保存されたbranchをリモート(共用のサーバ)に保存します。
			- git push origin master
	- 履歴の確認
		- git log
	
### git ホスティングサービス
- gitをwebでも扱えるようにしたソフトウェア
- remoteにあがっているgitのファイルをwebでも参照編集することもできる(ファイル共有に便利)
- githubを始め有料・無料で色々なものがあるが、gitの機能に加えて、Pull Request,issue,milestoneなど、プロジェクトを進めるための色々な機能が搭載されている

### github
- gitホスティングサービスで一番有名、無料・有料版などたくさんある。
- 使っている企業が有名!(amazon,google,microsoft,mixi,cookpad,gree,リクルート・・・etc)
- 連携できる機能も豊富(CircleCI,travis CI,Codetree,Asana・・・etc)
	 
## gitlab
- githubを元に作られた gitホスティングサービス github clone
- 無料でいろんなサービスを使うことができる!
- 最初期はgithubと比べてサービスが少ないと言われていたが、今はissue,Merge Request,wikiやGitlab CIなどの色々な機能が追加されている。

# Markdown
- Markdownとは
- wiki読(略
- 元々は普通のテキストをhtmlライクな装飾ができるテキストを作成するために作られた記法。
- githubやgitlab,backlog,qiitaで利用することができる。簡単な資料やメモを作る時に便利!
- テキストベースなのでgitで差分を表示できる
- このスライドもMarkdownで作成

## 書き方
- 見出し
	- 見出しは`#`の数で表現する

```
# 段落1  

## 段落2

### 段落3

#### 段落4

##### 段落5

###### 段落6

```

- 表示

# 段落1  

## 段落2

### 段落3

#### 段落4

##### 段落5

###### 段落6

## リスト
- リストは `-`,`*`,`+`のどれかとインデントで表現する。

- 例

```
- リスト1
	- リスト2 
		- リスト3
			- リスト4
				- リスト5
					- リスト6
						- リスト7
```

- 表示
- リスト1
	- リスト2 
		- リスト3
			- リスト4
				- リスト5
					- リスト6
						- リスト7							
## コード
- プログラムコード、htmlなどはMarkdown記法と競合してしまう場合があるので  ```バッククオート三つで囲んで表現する。
- 例

````
```
 
def main():
    print("Hello World")
 
if __name__ == '__main__':
    main()
```
````
- 表示

``` 
def main():
    print("Hello World")
 
if __name__ == '__main__':
    main()
```

- gitlabやqiitaなどの場合```の後ろに言語名をつけるとsyntax highlightされます。

```python
def main():
    print("Hello World")
 
if __name__ == '__main__':
    main()
```

### 強調
- 文字列を強調して表示することができます。
- ボールド \*\* \*\* アスタリスク二つで囲む 
	- **ボールド**
- コード \` \` バッククオートで囲む 
	- `コード`
- イタリック \_ \_  アンダースコアで囲む 
	- __コード__

### other 
- 他にも表やリンク、引用、水平線、画像の埋め込みなどがありますが、割愛

### hands on 
- 下記の表示をMarkdownにしてみよう
	- gitで実際に書いたMarkdownを表示する。
	 
# 参考URL
- GitHubを全社員(非エンジニア含む)に導入してよかったこと：プロジェクト管理ツールとしての効果と使い方
	- http://tech.cunited.jp/post/150337087525/github
- 非エンジニアがGitとGithubでぶち当たる3つの壁
	- https://news.d-lighted.jp/blog-staff/how-to-teach-git
- サルでもわかるgit入門
	- http://www.backlog.jp/git-guide/   
- SVNを捨ててGitを使うべき5つの理由
	- http://qiita.com/YusukeHosonuma/items/14c59f3878d640a401a1
- Markdown記法 チートシート
	- http://qiita.com/Qiita/items/c686397e4a0f4f11683d
  
 