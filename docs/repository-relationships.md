# 関連リポジトリ / Related repositories

このリポジトリはシステム全体の**理解レイヤーとオンボーディング標準の参照設計**を担当します。個別プロジェクトの実装、環境、運用手順の正本を所有しません。以下は参照関係であり、統合済みの機能や実行時依存を意味しません。

| リポジトリ | 本リポジトリとの関係 | 状態・責務境界 |
| --- | --- | --- |
| [feature-map-workflow](https://github.com/nakashima-yoshua/feature-map-workflow) | 業務機能単位の知識・出典と `catchup` | 既存機能を参照。全体概要の正本とは分離 |
| [cli-test-mcp](https://github.com/nakashima-yoshua/cli-test-mcp) | 検証実行・証跡取得の選択肢 | 検証環境での利用を判断。必須依存ではない |
| [quality-gate](https://github.com/nakashima-yoshua/quality-gate) | 独立した品質判定・証跡確認 | 判定は人の承認、マージ、本番反映を代替しない |
| [architecture-decision-system](https://github.com/nakashima-yoshua/architecture-decision-system) | 判断規則と設計上の制約の参照 | 案件の意思決定や承認の正本とは区別 |

各プロジェクトは要件・コード・テスト・Runbookを自身の正本として維持し、FMWは識別子と根拠の参照を持ちます。連携は実装済み・任意・構想段階を区別し、相互リンクのためだけに新しい実行依存を作りません。
