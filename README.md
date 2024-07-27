# Daily Reports
📝 日々の学習記録とGitの利用、および品質向上のための設定についてのリポジトリ

# ディレクトリ構成
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
├── templates/
│   └── daily-template.md          # 日報のテンプレートファイル
├── commitlint.config.js           # Commitlintの設定ファイル
├── package.json
└── README.md
```
## ブランチ運用
- main/master
- feature/日報名ブランチ 例：**feature/daily-report-2024-01-01**

## 日報作成手順
1. 新しいbrunchの作成（以下に例を記述）
``` git checkout -b feature/daily-report-2024-01-01 ```

2. テンプレートファイルをコピーして、新しい日報を作成
``` cp templates/daily-template.md reports/2024/01/2024-01-01.md ```

