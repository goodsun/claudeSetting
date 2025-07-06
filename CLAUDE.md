# Claude Code Configuration

## (重要)プロジェクトの目的
用途に応じたCLAUDE.mdの書き方のテンプレート化
どのようなパターンがあるかをリスト化する。

## 📁 Dynamic Configuration Management

### 設定ファイル管理
このディレクトリの`claude_configs/`フォルダ内の設定ファイルを読み込みます。
各設定ファイルの冒頭に`## STATUS: ON`または`## STATUS: OFF`が記述されており、ONの場合のみその設定を適用してください。

### 設定制御コマンド
- **英語学習モードON/OFF**: english_learning.mdのSTATUSを切り替え
- **開発モードON/OFF**: development.mdのSTATUSを切り替え
- **ドキュメンテーションモードON/OFF**: documentation.mdのSTATUSを切り替え
- **進捗管理モードON/OFF**: progress_management.mdのSTATUSを切り替え
- **インタラクティブ企画モードON/OFF**: interactive_mode.mdのSTATUSを切り替え
- **システム解析モードON/OFF**: system_analysis.mdのSTATUSを切り替え

### 常時適用設定
- **project_config.md**: プロジェクト固有の設定（常にON）
- **strict_rules.md**: 厳守ルール（常にON）

## 📂 利用可能なテンプレート
- `docs/claude_templates/project_kickoff.md` - **プロジェクト開始時の概要テンプレート**
- `docs/claude_templates/interactive_project_planning.md` - **インタラクティブ・プロジェクト企画**
- `docs/claude_templates/basic.md` - 基本的なプロジェクト
- `docs/claude_templates/develop.md` - 開発プロジェクト
- `docs/claude_templates/english_learning.md` - 英語学習プロジェクト
- `docs/claude_templates/machine-learning.md` - 機械学習プロジェクト
- `docs/claude_templates/microservices.md` - マイクロサービス
- `docs/claude_templates/mobile-app.md` - モバイルアプリ
- `docs/claude_templates/webapp.md` - Webアプリケーション
- `docs/claude_templates/sample.md` - サンプルテンプレート
- `docs/claude_templates/toplevel.md` - トップレベルプロジェクト
- `docs/claude_templates/web3cdk.md` - Web3 CDK開発プロジェクト

## 📚 追加情報
- **設計原則**: `docs/design/principles.md`
- **使い方のヒント**: `docs/CLAUDE_TIPS.md`

## 重要
返答は必ず日本語で行ってください。

## ⚠️ ルール遵守について
すべての設定ファイルのルールを確実に守ってください。特に：
1. **strict_rules.md**の厳守ルール（常にON）
2. **STATUS: ON**になっている各設定ファイルの指示
3. 複数の設定が競合する場合は、優先順位に従って適用