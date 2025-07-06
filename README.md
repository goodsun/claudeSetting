# claudeSetting

## 概要
このプロジェクトは、Claude Code（Anthropic公式CLI）で使用するCLAUDE.mdファイルのテンプレート管理システムです。プロジェクトの目的や用途に応じて最適化されたCLAUDE.md設定を簡単に適用できるようにすることを目的としています。

## 主な特徴

### 1. 動的設定管理
`claude_configs/`フォルダ内の設定ファイルをON/OFFで切り替えることができます：
- **英語学習モード** (`english_learning.md`) - 日英翻訳機能、タイポ指摘
- **開発モード** (`development.md`) - 開発効率を高める設定
- **ドキュメンテーションモード** (`documentation.md`) - ドキュメント作成支援
- **進捗管理モード** (`progress_management.md`) - タスク管理機能

### 2. 豊富なテンプレート
様々なプロジェクトタイプに対応したテンプレートを提供（`docs/claude_templates/`内）：
- `basic.md` - 基本的なプロジェクト
- `develop.md` - ソフトウェア開発プロジェクト
- `english_learning.md` - 英語学習プロジェクト
- `machine-learning.md` - 機械学習プロジェクト
- `microservices.md` - マイクロサービスアーキテクチャ
- `mobile-app.md` - モバイルアプリケーション開発
- `webapp.md` - Webアプリケーション開発
- `sample.md` - サンプルテンプレート
- `toplevel.md` - トップレベルプロジェクト
- `web3cdk.md` - Web3 CDK開発プロジェクト

## ディレクトリ構成
```
claudeSetting/
├── CLAUDE.md                # メイン設定ファイル
├── README.md               # このファイル
├── claude_configs/         # 動的設定ファイル
│   ├── english_learning.md # 英語学習設定
│   ├── development.md      # 開発設定
│   ├── documentation.md    # ドキュメント設定
│   ├── progress_management.md # 進捗管理設定
│   ├── project_config.md   # プロジェクト固有設定（常時ON）
│   └── strict_rules.md     # 厳守ルール（常時ON）
└── docs/                   # ドキュメント
    ├── CLAUDE_TIPS.md      # 使い方のヒント
    ├── claude_templates/   # プロジェクトテンプレート
    │   ├── basic.md
    │   ├── develop.md
    │   ├── english_learning.md
    │   ├── machine-learning.md
    │   ├── microservices.md
    │   ├── mobile-app.md
    │   ├── sample.md
    │   ├── toplevel.md
    │   └── webapp.md
    └── design/
        └── principles.md   # 設計原則
```

## 使い方

### 1. 基本的な使い方
1. プロジェクトの目的に合わせてテンプレートを選択
2. 必要に応じて`claude_configs/`内の設定をON/OFFに切り替え
3. Claude Codeを起動して作業開始

### 2. 設定の切り替え方法
各設定ファイルの冒頭にある`## STATUS: ON`または`## STATUS: OFF`を編集することで、機能の有効/無効を切り替えられます。

例：英語学習モードをOFFにする場合
```markdown
## STATUS: OFF
```

### 3. カスタマイズ
- `project_config.md`にプロジェクト固有の設定を追加
- `strict_rules.md`に厳守すべきルールを記載
- 新しいテンプレートを`claude_templates/`に追加可能

## 注意事項
- 常時適用設定（`project_config.md`、`strict_rules.md`）は常にON状態です
- 複数の設定が競合する場合は、優先順位に従って適用されます
- Claude Codeは設定ファイルに従って日本語で応答します（CLAUDE.mdの指示による）
