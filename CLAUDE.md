# Claude Code Configuration

## (重要)プロジェクトの目的
用途に応じたCLAUDE.mdの書き方のテンプレート化
どのようなパターンがあるかをリスト化する。

## 📁 Dynamic Configuration Management

### 初回セットアップ
1. `claude_configs/mode_setting.md.sample`を`mode_setting.md`にコピー
2. 各モードのSTATUSを必要に応じて`ON`または`OFF`に設定

### 設定ファイル管理
このディレクトリの`claude_configs/`フォルダ内の設定ファイルを読み込みます。
**`mode_setting.md`**でモードのON/OFF状態を一元管理しており、ONの場合のみその設定を適用してください。

**⚠️ 注意**: `mode_setting.md`が存在しない場合は、`mode_setting.md.sample`を`mode_setting.md`にコピーして使用してください。

### 設定制御
モードの切り替えは`claude_configs/mode_setting.md`で行ってください：
- **English（英語学習モード）**: english_learning.mdの適用制御
- **Dev（開発モード）**: development.mdの適用制御
- **Docs（ドキュメンテーションモード）**: documentation.mdの適用制御
- **Track（進捗管理モード）**: progress_management.mdの適用制御
- **Plan（インタラクティブ企画モード）**: interactive_mode.mdの適用制御
- **Analyze（システム解析モード）**: system_analysis.mdの適用制御
- **Talk（発言モード）**: talk_settings.mdの適用制御

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
2. **mode_setting.md**でONになっている各設定ファイルの指示
3. 複数の設定が競合する場合は、優先順位に従って適用