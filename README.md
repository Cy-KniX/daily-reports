# Daily Reports
📝 日々の学習記録とGitの利用、および品質向上のための設定についてのリポジトリ

## ディレクトリ構成
```
daily-reports/
├── .github/
│   └── workflows/
│       └── report-check.yml       # GitHub Actionsによる日報の自動チェック設定
├── .husky/
│   ├── commit-msg                 # Commitlintを使用したコミットメッセージのフォーマットチェック
│   └── pre-commit
├── reports/
│   ├── 2024/
│   │   ├── 07/
│   │   │   ├── 2024-07-01.md      # 2024年7月の日報
│   │   ├── 08/
│   │   │   ├── 2024-08-01.md      # 2024年8月の日報
│
├── templates/
│   └── daily-template.md          # 日報のテンプレートファイル
├── commitlint.config.js           # Commitlintの設定ファイル
├── package-lock.json
├── package.json
└── README.md
```
## ブランチ運用
- main
- feature/<Issue番号>-日報名ブランチ 例：**feature/#1-daily-report-2024-01-01**

## 日報作成手順
1. 作業開始時に今日の日付で新しいIssueを作成する 例: **2024-01-01**

2. mainブランチをチェックアウトして`git pull`

3. 新しいbrunchの作成  
例:
``` 
git checkout -b feature/#1-daily-report-2024-01-01
 ```

4. テンプレートファイルをコピーして、新しい日報を作成  
例:
``` 
cp templates/daily-template.md reports/2024/01/2024-01-01.md
```

5. commitlintで指定した規則に従いコミットメッセージを作成(typeとその説明については下記に記述)  
コミットメッセージ例:
``` 
docs: Add daily report for 2024/01/01
```
6. ローカルで作業しているブランチをリモートリポジトリにpush  
```
git push origin feature/#1-daily-report-2024-01-01
```
ターミナルから以下の設定をすればgit pushで現在作業中のブランチからpushしてくれるので便利
```
git config --global push.default current

// 上記の設定をすると以下のコマンドだけで良い

git push
```
7. close #<Issue番号>をPullRequestに記述して作成  

8. マージ済みのブランチを削除  

ローカルでマージしブランチを削除する場合  
```
git checkout main

# ローカルでマージするとpost-mergeフックによりブランチを自動削除
git merge feature/#1-daily-report-2024-01-01
```
github上でマージをした場合には以下のコマンドでブランチを削除
- ローカルブランチの削除  
例：
``` 
git branch -d feature/#1-daily-report-2024-01-01
```

### husky、Github Actionsについて
勉強の一環として導入（個人の日報であるため、導入はしなくても良い）
- husky: コミットメッセージのフォーマットをチェックする
- Github Actions: PRに含まれたmdファイルが指定されたフォーマットに従っているかをチェックする

### コミットメッセージのtypeについて
以下のルールに従ってコミットメッセージのtypeを記述  

- **feat**: 新機能の追加（例: `feat: add user login functionality`）
- **fix**: バグの修正（例: `fix: resolve issue with login redirect`）
- **docs**: ドキュメントのみの変更（例: `docs: update README with new API details`）
- **style**: コードの動作に影響しない変更（例: `style: format code with Prettier`）
- **refactor**: バグの修正や機能の追加ではないコードのリファクタリング（例: `refactor: change structure of user service`）
- **perf**: パフォーマンスを向上させるための変更（例: `perf: improve query performance on user list`）
- **test**: テストの追加や修正（例: `test: add unit tests for user service`）
- **build**: ビルドシステムや外部依存に関する変更（例: `build: update webpack configuration`）
- **ci**: CI設定ファイルとスクリプトの変更（例: `ci: add GitHub Actions configuration`）
- **chore**: その他の変更（例: `chore: update dependencies`）
- **revert**: 以前のコミットを取り消す（例: `revert: revert "feat: add user login functionality"`）