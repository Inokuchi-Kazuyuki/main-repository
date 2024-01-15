# Git SubModules お試し

## リポジトリ準備

main、sub1、sub2 の３つのリポジトリを作成  
GitHub CLI [^1] を使用
```
# main-repository
gh repo create main-repository --add-readme --public

# sub1-repository
gh repo create sub1-repository --add-readme --public

# sub2-repository
gh repo create sub2-repository --add-readme --public
```

## リポジトリの設定
GitHub CLI で repo create する時に同時に行えるが、Git コマンド[^2] で行う

### main-repository
```
# リモートリポジトリを設定
git remote add origin git@github.com:Inokuchi-Kazuyuki/main-repository.git

# プッシュ
git push -u origin main
``````

### sub1-repository
```
# リモートリポジトリを設定
git remote add origin git@github.com:Inokuchi-Kazuyuki/sub1-repository.git

# プッシュ
git push -u origin main
```

### sub2-repository
```
# リモートリポジトリを設定
git remote add origin git@github.com:Inokuchi-Kazyuki/sub2-repository.git

# プッシュ
git push -u origin main
```

## SubModule の追加
main-repository で以下のコマンドを実行する
```
# sub1-repository を SubModule として追加
git submodule add git@github.com:Inokuchi-Kazuyuki/sub1-repository

# sub2-repository を SubModule として追加
git submodule add git@github.com:Inokuchi-Kazuyuki/sub2-repository
```

## メインリポジトリへの反映
### sub1-repository を修正する  
main-repository 内ではなく sub1-repository のリポジトリで行う  
```
# repo1-repository の内容を変更してプッシュ
git commit -m "更新"
git push -u origin main
```

### sub1-repository の変更を main-repository に反映する
```
# main-repository で行う
git -C sub1-repository checkout origin/main
# 変更をステージに追加
git add .
# 変更をコミット
git commit -m "XXXXX"
# リモートリポジトリにプッシュ
git push -u origin main

or

# sub1-repository に移動
cd sub1-repository
# ブランチを切り替える
git checkout main
# リモートリポジトリから最新を反映
git pull

# main-repository に移動
cd main-repository
# 変更をステージに追加
git add .
# 変更をコミット
git commit -m "XXXXX"
# リモートリポジトリにプッシュ
git push -u origin main
```

[^1]: [GitHub CLI の リポジトリに関する Manual](https://cli.github.com/manual/gh_repo)
[^2]: [Git コマンドのマニュアル](https://git-scm.com/docs)
