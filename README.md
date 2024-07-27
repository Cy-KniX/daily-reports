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
├── commitlint.config.ts           # Commitlintの設定ファイル
├── package-lock.json
├── package.json
└── README.md
```
## ブランチ運用
- main/master
- feature/日報名ブランチ 例：**feature/daily-report-2024-01-01**

## 日報作成手順
1. 作業開始時に今日の日付で新しいIssueを作成する 例: **2024-01-01**

2. mainブランチをチェックアウトして`git pull`

3. 新しいbrunchの作成  
例:
``` 
git checkout -b feature/daily-report-2024-01-01
 ```

4. テンプレートファイルをコピーして、新しい日報を作成  
例:
``` 
cp templates/daily-template.md reports/2024/01/2024-01-01.md
```

5. commitlintで指定した規則に従いコミットメッセージを作成  
コミットメッセージ例:
``` 
docs: Add daily report for 2024/01/01
```

6. close #<Issue番号>をPullRequestに記述して作成  

### husky、Github Actionsについて
勉強の一環として導入（個人の日報であるため、導入はしなくても良い）
- husky: コミットメッセージのフォーマットをチェックする
- Github Actions: PRに含まれたmdファイルが指定されたフォーマットに従っているかをチェックする