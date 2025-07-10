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
- **インタラクティブ企画モード** (`interactive_mode.md`) - 対話型プロジェクト企画

### 2. 豊富なテンプレート
様々なプロジェクトタイプに対応したテンプレートを提供（`docs/claude_templates/`内）：
- `project_kickoff.md` - **プロジェクト開始時の概要テンプレート**
- `interactive_project_planning.md` - **インタラクティブ・プロジェクト企画**
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

### 3. 🎯 インタラクティブ・プロジェクト企画（NEW!）
Claudeと対話しながらプロジェクトを企画し、project_kickoff.mdを自動生成する機能：

#### 特徴
- **段階的な対話フロー**: アイデア発掘→深掘り→機能設計→技術選択→計画立案
- **自動生成**: 対話内容から完全なproject_kickoff.mdを生成
- **技術選択支援**: スキルレベルに応じた技術スタック提案
- **フレンドリーな対話**: 絵文字とカジュアルな表現でサポート

#### 起動方法
```
"新しいプロジェクトを一緒に企画しましょう"
```

#### 対話例
```
Claude: 「どんなサービスを作りたいですか？🚀」
User: 「読書管理アプリかな...」
Claude: 「面白いですね！個人用？コミュニティ機能も？」
→ 段階的に深掘りして最適なproject_kickoff.mdを生成
```

## ディレクトリ構成
```
claudeSetting/
├── CLAUDE.md                # メイン設定ファイル
├── README.md               # このファイル
├── claude_configs/         # 動的設定ファイル
│   ├── mode_setting.md     # モード設定（個人用・要作成）
│   ├── mode_setting.md.sample # モード設定テンプレート
│   ├── english_learning.md # 英語学習設定
│   ├── development.md      # 開発設定
│   ├── documentation.md    # ドキュメント設定
│   ├── progress_management.md # 進捗管理設定
│   ├── interactive_mode.md # インタラクティブ企画設定
│   ├── project_config.md   # プロジェクト固有設定（常時ON）
│   └── strict_rules.md     # 厳守ルール（常時ON）
└── docs/                   # ドキュメント
    ├── CLAUDE_TIPS.md      # 使い方のヒント
    ├── claude_templates/   # プロジェクトテンプレート
    │   ├── project_kickoff.md        # プロジェクト開始テンプレート
    │   ├── interactive_project_planning.md # インタラクティブ企画
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

## 🚀 初回セットアップ（重要）

### ステップ1: 設定ファイルの準備
```bash
# 設定ファイルをコピー
cp claude_configs/mode_setting.md.sample claude_configs/mode_setting.md
```

### ステップ2: 設定の確認・調整
`claude_configs/mode_setting.md`を開いて、各モードのON/OFF状態を確認・調整してください。

### ステップ3: Claude Codeを起動
```bash
claude-code
```

## 使い方

### 1. 🚀 新規プロジェクト開始（推奨）
**インタラクティブ企画モード**を使用して、Claudeと対話しながらプロジェクトを企画：

```bash
# Claude Codeを起動
claude-code

# インタラクティブ企画を開始
"新しいプロジェクトを一緒に企画しましょう"
```

### 2. 📋 既存プロジェクト向け
1. プロジェクトの目的に合わせてテンプレートを選択
2. 必要に応じて`claude_configs/mode_setting.md`内の設定をON/OFFに切り替え
3. Claude Codeを起動して作業開始

### 3. ⚙️ 設定の切り替え方法
`claude_configs/mode_setting.md`内の各モードのSTATUSを`ON`または`OFF`に変更することで、機能の有効/無効を切り替えられます。

例：英語学習モードをOFFにする場合
```markdown
### 英語学習モード
- **ファイル**: english_learning.md
- **STATUS**: OFF
```

### 4. 🎯 推奨設定パターン

#### スタートアップ・MVP開発
`mode_setting.md`内で以下のように設定：
```
english_learning: OFF
development: ON (高速モード)
interactive_mode: ON
progress_management: ON
```

#### エンタープライズ開発
`mode_setting.md`内で以下のように設定：
```
development: ON (慎重モード)
documentation: ON
progress_management: ON
interactive_mode: OFF
```

#### 学習・実験プロジェクト
`mode_setting.md`内で以下のように設定：
```
english_learning: ON
development: ON (高速モード)
interactive_mode: ON
documentation: OFF
```

### 5. 🛠️ カスタマイズ
- `project_config.md`にプロジェクト固有の設定を追加
- `strict_rules.md`に厳守すべきルールを記載
- 新しいテンプレートを`claude_templates/`に追加可能

## 注意事項
- **初回利用時**: 必ず`mode_setting.md.sample`を`mode_setting.md`にコピーしてください
- 常時適用設定（`project_config.md`、`strict_rules.md`）は常にON状態です
- 複数の設定が競合する場合は、優先順位に従って適用されます
- Claude Codeは設定ファイルに従って日本語で応答します（CLAUDE.mdの指示による）
- `mode_setting.md`はgit管理対象外です（個人設定のため）

## 🎉 主な効果・メリット

### 開発効率向上
- プロジェクト開始時の設定時間を大幅短縮
- 目的に応じた最適化された設定で即座に作業開始
- 対話型企画によるアイデアの具体化

### 学習効果
- 英語学習機能による技術用語の習得
- プロジェクト企画プロセスの学習
- 技術選択の理由と背景の理解

### 品質向上
- 厳守ルールによる一貫性の確保
- 段階的開発による計画的な実装
- 適切な技術選択によるリスク軽減

### チーム活用
- 統一された設定による開発体験の標準化
- 新メンバーのオンボーディング支援
- プロジェクト知識の蓄積と共有

---

**Claude Code × claudeSetting で、プロジェクト開発をもっと楽しく、効率的に！**
