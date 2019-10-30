# git-shadow

* ローカルリポジトリをコピーするコマンド
  * e.g. `make`でしかビルドできないプロジェクト向け
    * ビルド生成物を異なるディレクトリで管理できる

## 仕様
* 元のリポジトリをmaster
* addしたリポジトリをslaveとする
* `.git/shadow`にて情報を管理する
* コミットされていないdiffを含めて同期する
* 現在のmasterのブランチにslaveのブランチは追従する

## how to use
```
git shadow add ~/tmp/$(basename $(git rev-parse --show-toplevel))-shadow
# add commit or change files
git sync
```

## how to install
```
install_path="$HOME/local/bin/"
wgit https://raw.githubusercontent.com/umaumax/git-shadow/master/git-shadow -O "$install_path/git-shadow"
chmod u+x "$install_path/git-shadow"
```
