# System Understanding Architecture

[English](README.md) | **日本語**

システム理解、ドキュメント、ソースコード、テスト、AIコンテキストを単一のGitリポジトリで統合管理するための参照アーキテクチャです。

## 目的

このリポジトリの目的は、単に仕様を保存することではありません。読み手がシステムについて正確なメンタルモデルを短時間で形成し、必要な実装詳細へ最短距離で到達できるドキュメント体系を定義します。

従来の要件、設計書、ソースコード、DB資産、テスト、インフラを正本として維持し、その上に薄い**理解レイヤー（Understanding Layer）**を配置します。

AI開発では、AIも同じ知識アーキテクチャを利用しますが、未信頼の実行主体として扱います。人は意味、境界、Invariant、リスク受容、承認を所有し、AIは限定された範囲で探索、実装、検査、証跡整理を担当します。

## 情報構造

```text
理解レイヤー
    ↓
要件 / 設計 / 意思決定
    ↓
実装 / DB / テスト / インフラ
    ↓
自動検査の証跡 / 人間レビュー
```

ナビゲーションは逆方向にも成立させます。コードやデータ構造から、それが存在する理由となった業務目的・要件・意思決定まで遡れることを目標とします。

## リポジトリ構造

```text
.
├─ AGENTS.md                 # AI作業規則
├─ README.md                 # English entry point
├─ README.ja.md              # 日本語エントリーポイント
├─ docs/
│  ├─ understanding/         # 理解レイヤー
│  │  ├─ invariants.md
│  │  └─ ai-development-policy.md
│  ├─ requirements/          # 要件
│  ├─ design/                # 設計
│  ├─ decisions/             # ADR
│  └─ templates/             # Change Contract / Human Review等
├─ src/                      # ソースコード
├─ tests/                    # テスト
├─ db/                       # DB資産
└─ infra/                    # インフラ
```

日本語ドキュメントは各ディレクトリの `ja/` 以下に、英語版と同じ相対構造で配置します。ID、ファイルの役割、参照先は言語間で一致させます。

## 推奨読解順序

1. [システム概要](docs/understanding/ja/system-overview.md)
2. [業務マップ](docs/understanding/ja/business-map.md)
3. [ケイパビリティマップ](docs/understanding/ja/capability-map.md)
4. [アーキテクチャマップ](docs/understanding/ja/architecture-map.md)
5. [Invariant](docs/understanding/ja/invariants.md)
6. [変更ガイド](docs/understanding/ja/change-guide.md)
7. 要件、設計、ADR、コード、テスト、DB、インフラの詳細へ進む

## 理解設計の共通契約

理解ドキュメントは原則として、次の6点に答えます。

1. **目的（Purpose）** — なぜ存在するか
2. **文脈（Context）** — システム全体のどこに位置するか
3. **責務（Responsibility）** — 何を担当し、何を担当しないか
4. **流れ（Flow）** — 何が入り、何が起き、何が出るか
5. **依存関係（Dependencies）** — 何に依存し、何へ影響するか
6. **変更影響（Change Impact）** — 変更時に何を確認すべきか

## トレーサビリティ

意味のある境界・ルールには、言語に依存しない安定したIDを使用します。

- `CAP-BILLING`
- `BR-BILL-001`
- `REQ-BILL-001`
- `UC-BILL-001`
- `INV-BILL-001`
- `ADR-0001`

すべてのメソッドへIDを付与するのではなく、ケイパビリティ、ルール、モジュール、API、バッチ、テーブル、テストなど意味のある境界でトレーサビリティを維持します。

## 運用ルール

- ドキュメントと関連コードの変更は、原則として同一Pull Requestでレビューする。
- 理解レイヤーには詳細仕様を重複記載せず、正本となる詳細成果物へリンクする。
- 各機能について、業務目的からコード・テストまで辿れる経路を維持する。
- 変更の正しさだけでなく、初見の読み手が変更を発見し理解できるかをレビューする。
- Markdownとリポジトリ内リンクを基本とし、特定ツールへの依存を抑える。

## 多言語化方針

- 技術ID、パス、コード識別子は翻訳しない。
- 内容の意味と責任範囲を言語間で一致させる。
- 一方の言語で仕様上の変更が発生した場合、対応する翻訳も同じPRで更新する。
- 将来別言語を追加する場合も、同じ規則で言語コードのディレクトリを追加する。

## AI開発

AIエージェントはリポジトリ全体を無差別に検索せず、理解レイヤーから探索を開始します。

```text
README
  → システム概要
  → 業務 / ケイパビリティマップ
  → Invariant
  → 関連要件 / ADR
  → 設計
  → ソース / DB / テスト
```

振る舞いを変更する作業は [Change Contract](docs/templates/ja/change-contract-template.md) で境界を定義します。AIの作業完了状態は `HUMAN_REVIEW_REQUIRED` とし、[Human Review Request](docs/templates/ja/human-review-request-template.md) を業務意味から高リスク実装の順に提出します。

責任、証跡、最小権限、停止条件、承認規則は [AI開発ポリシー](docs/understanding/ja/ai-development-policy.md) と `AGENTS.md` を参照します。