# 変更ガイド

## 目的

「何を変更したいか」から、理解すべき業務・要件・設計・コード・テストへ逆引きするための入口です。

## AI開発時の変更フロー

```text
変更要求
  → Change Contract
  → Capability
  → Invariant
  → 要件 / ADR
  → 設計
  → コード / DB / インターフェース
  → テスト / 自動検査
  → Human Review Request
  → 人による承認
```

AIに委託する場合は、実装前に変更可能範囲を定義します。重大な曖昧さ、Invariantとの衝突、スコープ拡大、未検証の高リスク影響を発見した場合、AIは停止して人間レビューを依頼します。

## 変更探索順序

1. **業務活動** — `business-map.md`
2. **ケイパビリティ** — `CAP-...`
3. **Invariant** — `INV-...`
4. **業務要件 / ルール** — `BR-...`
5. **機能要件 / ユースケース** — `REQ-...`, `UC-...`
6. **関連ADR** — `ADR-...`
7. **詳細設計** — `docs/design/...`
8. **アプリケーション / DB / 外部IF / テスト** — `src/`, `db/`, `tests/`
9. **運用 / 移行 / 検証 / ロールバック** — `infra/` と関連設計

## 変更時の確認

- どの業務成果が変わるか
- 何を変更しないか
- どのCapabilityが責任を持つか
- どのInvariantを維持するか
- 現在の動作を説明する要件・ADRは何か
- どのコード、データ、IF、テストが実現しているか
- どの下流動作が壊れ得るか
- 何で検証し、どうロールバックするか
- 各主張が `CONFIRMED` / `INFERRED` / `UNVERIFIED` / `HUMAN_DECISION` のどれか

実装前には `docs/templates/ja/change-contract-template.md`、人の承認前には `docs/templates/ja/human-review-request-template.md` を使用します。