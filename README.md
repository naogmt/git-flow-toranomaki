# git-flow-toranomaki
git flow の基本まとめメモ

## github flow について、丁寧に解説してください。

GitHub Flowは、ソフトウェア開発プロジェクトにおいて作業を効率的に行うためのシンプルなワークフローです。基本的には以下の5つのステップで構成されています。

1. **ブランチ作成**: `main` ブランチから新しいブランチを作成します。
2. **コードの追加・修正**: 新しいブランチ上でコードの変更を行い、コミットします。
3. **プルリクエスト作成**: コードの変更が完了したら、プルリクエスト（PR）を作成します。
4. **コードレビュー**: 他のチームメンバーがプルリクエストをレビューします。
5. **マージ**: レビューが通れば、`main` ブランチにマージします。

### 具体的な業務の例

#### ブランチ名
- 新機能追加: `feature/add-login`
- バグ修正: `fix/null-pointer-exception`

#### コミットコメント
- 新機能追加: `Add login functionality`
- バグ修正: `Fix null pointer exception in User class`

#### 例のリスト
1. `git checkout -b feature/add-login` で新しいブランチを作成。
2. コードを変更して `git commit -m "Add login functionality"` でコミット。
3. GitHub上でプルリクエストを作成。
4. チームメンバーがレビューを行い、問題がなければ `main` ブランチにマージ。

このようにして、GitHub Flowはチーム内でのコードの共有やレビューを効率的に行います。特にAIやデータサイエンスのプロジェクトでもこのフローは有用ですよ。

## ブランチ名の具体例を表形式でまとめてください

もちろんです、ブランチ名の具体例を表形式でまとめてみます。

| ケース               | ブランチ名                |
|----------------------|---------------------------|
| 新機能（ログイン）    | `feature/add-login`       |
| バグ修正              | `fix/null-pointer-exception` |
| ドキュメント追加      | `docs/update-readme`      |
| リファクタリング      | `refactor/cleanup-code`   |
| デザイン変更          | `design/new-header`       |
| テストケース追加      | `test/add-unit-tests`     |
| 緊急のホットフィックス | `hotfix/security-issue`   |

このような命名規則は、チーム内で共有しておくと、ブランチの目的が一目でわかるので便利です。

## コミットコメントの具体例も表形式でまとめてください。

もちろん、コミットコメントの具体例も表形式でまとめてみます。

| ケース            | コミットコメント                   |
|-------------------|------------------------------------|
| 新機能の追加       | `Add login functionality`          |
| バグ修正           | `Fix null pointer exception in User class` |
| ドキュメントの更新 | `Update README with new instructions` |
| コードの整理       | `Refactor User class for better readability` |
| デザインの変更     | `Update header design`              |
| テストケースの追加  | `Add unit tests for User class`     |
| 緊急の修正         | `Hotfix for security vulnerability` |

これらのコメントはコミットの内容を簡潔に、しかし明確に表しています。これにより、後でレビューする際や履歴を遡る際に、どのコミットが何を目的としているのか容易に理解できます。

## Git操作の基本

初期設定
   1 git config --global user.name naogmt
   2 git config --global user.email ＊＊＊＊@gmail.com
   3 git config --list

作業ディレクトリ作成
   4 cd .\github\
   5 mkdir sample-play
   6 cd sample-play

ローカルリポジトリ作成
   7 git init

リモートリポジトリ作成
（githubの方で行う）
ギットの承認キー設定
＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊＊


リモートとローカルリポジトリの紐づけ
   8 git remote add origin https://github.com/ryohei8/sample-v.git

以下だとエラー 
  9 git pull

リモートリポジトリとブランチを指定してローカルにプル
  10 git pull https://github.com/ryohei8/sample-v.git main
  11 ls
  12 ls

ローカルリポジトリに変更をステージ
  13 git add index.html

ローカルに変更をコミット
  14 git commit -m "[add] index"
  15 git log

リモートに変更をプッシュする
  16 git push origin main

ブランチを作り移動
  17 git branch sub1
  18 git branch sub2
  19 git branch
  20 git checkout sub1
  21 git branch

ブランチsub1で変更しコミット
  22 git add .\index2.html
  23 git commit -m "[add] index2"

リモートのブランチsub1も作りプッシュ
  24 git push origin sub1

ブランチsub2でリモートのsub1をプル
  25 git checkout sub2
  26 git branch
  27 git pull
  28 git pull https://github.com/ryohei8/sample-v.git sub1
  29 ls

メインに戻りsub2をマージする
  30 git checkout main
  31 git merge sub2
  32 ls

リモートにプッシュ
  33 git push origin main

ブランチをローカルリモート共に削除
  34 git branch -d sub1 sub2
  35 git branch
  36 git push --delete origin sub1

注意
・ローカルのブランチ名とリモートのブランチ名を一致させる
・mainでは作業しないこと
