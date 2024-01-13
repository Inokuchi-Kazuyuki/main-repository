# 練習用

## SubModule の確認
### main-repository
#### リポジトリ作成

```
# github に新規リポジトリを作成
gh repo create main-repository --add-readme --public 

# リモートリポジトリを設定
git remote add origin git@github.com:Inokuchi-Kazuyuki/main-repository.git

# プッシュ
git push -u origin main
``````
### sub1-repository
#### リポジトリ作成

```
# github に新規リポジトリを作成
gh repo create sub1-repository --add-readme --public 

# リモートリポジトリを設定
git remote add origin git@github.com:Inokuchi-Kazuyuki/sub1-repository.git

# プッシュ
git push -u origin main
```

### sub2-repository
#### リポジトリ作成

```
# github に新規リポジトリを作成
gh repo create sub2-repository --add-readme --public

# リモートリポジトリを設定
git remote add origin git@github.com:Inokuchi-Kazyuki/sub2-repository.git

# プッシュ
git push -u origin main
```

### SubModule の追加
```
# main-repository で行う
git submodule add git@github.com:Inokuchi-Kazuyuki/sub1-repository

git submodule add git@github.com:Inokuchi-Kazuyuki/sub2-repository
```