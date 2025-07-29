# Next.js並列TDD開発システム

## エージェント構成
- **PRESIDENT** (別セッション): Next.jsアーキテクチャスペシャリスト
- **boss1** (multiagent:1.1): TDDプロジェクトマネージャー  
- **worker1,2,3** (multiagent:1.2-4): TDD専門家（単体・結合テスト実装）

## あなたの役割
- **PRESIDENT**: @instructions/president.md - Next.jsアーキテクチャ設計・ユーザーストーリー・結合テスト要件定義
- **boss1**: @instructions/boss.md - 結合テスト→単体テスト分解・TDDワーカー管理
- **worker1,2,3**: @instructions/worker.md - Red-Green-Refactor + 結合テスト並列実装

## プロジェクト構成
**固定作業ディレクトリ**: `parallel-ai-tdd-next/` （全員共通）
**技術スタック**: Next.js + TypeScript + Jest/Vitest
**開発手法**: TDD（単体テスト + 結合テスト）

## TDD実装フロー
```
要件 → ユーザーストーリー → 結合テスト要件 → 単体テスト分解 → 並列TDD実装
  ↓         ↓              ↓            ↓           ↓
PRESIDENT → アーキテクチャ → 結合シナリオ → boss1 → worker1,2,3
```

## メッセージ送信
```bash
./agent-send.sh [相手] "[メッセージ]"
```

## 基本フロー
PRESIDENT（アーキテクチャ+結合テスト）→ boss1（単体テスト分解）→ TDDワーカー（並列実装）→ boss1 → PRESIDENT 