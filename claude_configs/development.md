# Development Configuration

<!-- このセクションがOFFの場合、以下の内容は無視してください -->

## 🎯 Development Mode Settings

この設定はmode_setting.mdの動作速度設定に連動します：
- **高速モード (STATUS: ON)**: 迅速な開発を優先
- **慎重モード (STATUS: ON)**: 詳細な確認を優先

### 🚀 高速モード時の動作
- ソースコード変更を確認なしで実行
- アイデアを素早く形にすることを優先
- 複数の修正を連続して適用
- エラーが出たら修正して継続

### 🔍 慎重モード時の動作
- ソースコード変更前に毎回確認を求める
- 一つずつ丁寧に変更内容を説明
- ユーザーの承認後に変更を実行
- 重要な修正や本番環境では必須

### Claude Code 標準の確認動作

#### 📋 DRY原則の厳守 (Don't Repeat Yourself)
- **重複コードの排除**: 同じロジックは関数・クラス・モジュールとして切り出す
- **設定の一元化**: 定数・設定値は一箇所で管理し、複数箇所で参照
- **共通処理の抽象化**: 似たような処理は共通関数として実装
- **コピー&ペーストの禁止**: 既存コードをコピーする前に共通化を検討
- **リファクタリングの推奨**: 重複が発見された場合は積極的に統合

#### 🔒 常に確認が必要な操作（モードに関係なく）
- **危険なコマンド**: `rm -rf`, `sudo`, `chmod +x` など
- **Git操作**: `git push`, `git reset --hard`, `git clean -fd`
- **パッケージインストール**: `npm install`, `pip install` 
- **環境変数の変更**: `.env` ファイルの編集
- **データベース操作**: DROP, DELETE, TRUNCATE など
- **ファイル削除**: 既存ファイルの削除

#### ⚡ 高速モードで確認をスキップする操作
- **ファイル作成・編集**: 新規ファイル作成、既存ファイルの修正
- **TypeScript/JavaScript**: コード追加・修正
- **設定ファイル**: package.json, tsconfig.json の更新
- **ドキュメント**: README, CLAUDE.md の更新
- **開発用コマンド**: `npm run build`, `npm test`
- **ローカルデプロイ**: `./deploy.sh local` （Discord機能以外）
- **Discord本番デプロイ**: `./deploy.sh production` （Discord機能専用）

#### 🔍 慎重モードで追加確認する操作
- **全てのファイル編集**: 内容を説明してから実行
- **コマンド実行**: 実行内容を説明してから実行
- **複数ファイル一括変更**: 影響範囲を説明してから実行
- **API仕様変更**: 破壊的変更の可能性を説明

#### 📋 確認メッセージの例
```
慎重モード時:
「app.ts に Discord EOA 機能を追加します。
 - 新しいエンドポイント /discord/member/:userId を追加
 - DynamoDB から EOA 情報を取得する処理を追加
実行してよろしいですか？」

高速モード時:
（確認なしで即座に実行）
```

## 開発支援機能
### コードレビュー機能
- セキュリティの問題を自動チェック
- パフォーマンスの問題を指摘
- コードの可読性を向上

### テスト支援機能
- テストケースの自動生成
- カバレッジの確認
- テスト結果の分析

### デバッグ支援機能
- エラーの詳細な解析
- 修正案の提案
- ログの分析
