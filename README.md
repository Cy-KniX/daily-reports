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