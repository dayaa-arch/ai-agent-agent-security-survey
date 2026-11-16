# AI Agent / Agent Security 論文サーベイ

AIエージェントとAgent Securityの論文を、基礎から2026年の最新まで43本読むためのリポジトリ。

- 読了状況は下の表の「状態」列で管理する（`未読` → `読書中` → `読了`）
- 1本読んだら `notes/` に [TEMPLATE.md](notes/TEMPLATE.md) をコピーしてメモを書き、表の「メモ」列からリンクする
- 2026年の論文の多くはまだpreprint。査読前の結果として扱う

## 読む順番

1. **全体像をつかむ:** CoALA → Toward Secure LLM Agents（サーベイ）
2. **agentの骨格:** ReAct → Reflexion → SWE-agent → τ-bench
3. **攻撃の原点:** Greshake et al. → AgentDojo → MCPTox
4. **防御の現在地:** CaMeL → Design Patterns → The Attacker Moves Second → AgentDyn

4は「ベンチマーク上では防御できた → 適応的な攻撃や現実的な環境では崩れる」という流れになっている。デモで見えた結果と、証拠として言える結果を区別する練習になる。

## AIエージェント: 基礎（2022〜2023）

| # | 論文 | 年・状態 | 何を押さえるか | 状態 | メモ |
|---|---|---|---|---|---|
| A01 | [MRKL Systems](https://arxiv.org/abs/2205.00445) (Karpas et al.) | 2022 preprint | LLM＋外部ツールという発想の原型 | 未読 | |
| A02 | [ReAct](https://arxiv.org/abs/2210.03629) (Yao et al.) | ICLR 2023 | 推論→行動→観測ループ。すべての出発点 | 未読 | |
| A03 | [Toolformer](https://arxiv.org/abs/2302.04761) (Schick et al.) | NeurIPS 2023 | モデル自身がAPI呼び出しを学習する | 未読 | |
| A04 | [Reflexion](https://arxiv.org/abs/2303.11366) (Shinn et al.) | NeurIPS 2023 | 失敗を言語で振り返り、次の試行に活かす | 未読 | |
| A05 | [Generative Agents](https://arxiv.org/abs/2304.03442) (Park et al.) | UIST 2023 | memory・reflection・planningの構成 | 未読 | |
| A06 | [Voyager](https://arxiv.org/abs/2305.16291) (Wang et al.) | 2023 | スキルライブラリを蓄積し続けるagent | 未読 | |
| A07 | [AutoGen](https://arxiv.org/abs/2308.08155) (Wu et al.) | 2023 | multi-agent会話フレームワークの代表 | 未読 | |
| A08 | [CoALA](https://arxiv.org/abs/2309.02427) (Sumers et al.) | TMLR 2024 | agentの認知アーキテクチャを整理する枠組み。全体地図として最初に読む | 未読 | |

## AIエージェント: 評価と実用化（2023〜2025）

| # | 論文 | 年・状態 | 何を押さえるか | 状態 | メモ |
|---|---|---|---|---|---|
| B01 | [WebArena](https://arxiv.org/abs/2307.13854) (Zhou et al.) | ICLR 2024 | 実Webサイト環境でのタスク評価 | 未読 | |
| B02 | [SWE-bench](https://arxiv.org/abs/2310.06770) (Jimenez et al.) | ICLR 2024 | 実GitHub issueの解決。coding agent評価の標準 | 未読 | |
| B03 | [GAIA](https://arxiv.org/abs/2311.12983) (Mialon et al.) | ICLR 2024 | 汎用アシスタント能力の評価 | 未読 | |
| B04 | [OSWorld](https://arxiv.org/abs/2404.07972) (Xie et al.) | NeurIPS 2024 | 実OS上のcomputer use評価 | 未読 | |
| B05 | [SWE-agent](https://arxiv.org/abs/2405.15793) (Yang et al.) | NeurIPS 2024 | agent-computer interfaceの設計が性能を左右する | 未読 | |
| B06 | [τ-bench](https://arxiv.org/abs/2406.12045) (Yao et al.) | 2024 | 同じタスクを繰り返したときの一貫性（信頼性）を測る | 未読 | |
| B07 | [Why Do Multi-Agent LLM Systems Fail?](https://arxiv.org/abs/2503.13657) (Cemri et al.) | 2025 | multi-agentの失敗を分類する | 未読 | |

## AIエージェント: 最新（2026）

| # | 論文 | 状態（出版） | 何を押さえるか | 状態 | メモ |
|---|---|---|---|---|---|
| C01 | [APEX-Agents](https://arxiv.org/abs/2601.14242) | preprint | 投資銀行アナリストやコンサルタントが作った、複数アプリをまたぐ長期タスクでagentを評価 | 未読 | |
| C02 | [MASBench / MAS-Orchestra](https://www.emergentmind.com/topics/masbench) (Ke et al.) | preprint、2026年1月 | multi-agentが単独agentより有利になる条件と、協調がオーバーヘッドや誤り伝播を生む条件を切り分ける | 未読 | |
| C03 | [The Long-Horizon Task Mirage? (HORIZON)](https://arxiv.org/abs/2604.11978) | preprint | 長期タスクでagentがどこで、なぜ崩れるかを領域横断で診断 | 未読 | |
| C04 | [Agents' Last Exam](https://arxiv.org/abs/2606.05405) | preprint | 経済的価値のある実務タスクを対象に、タスクが増え続ける「living benchmark」として設計 | 未読 | |
| C05 | [Long-Horizon-Terminal-Bench](https://arxiv.org/abs/2607.08964) | preprint | 46の長期ターミナルタスクで、1タスク平均980万トークン・約89分を消費。コスト問題の実例 | 未読 | |
| C06 | [MAMath-Bench](https://arxiv.org/abs/2610.26943) | preprint、2026年10月 | multi-agentの協調は、強い単独LLMの最終正答率を安定して上回らない | 未読 | |

## Agent Security: 基礎（2022〜2024）

| # | 論文 | 年・状態 | 何を押さえるか | 状態 | メモ |
|---|---|---|---|---|---|
| D01 | [Ignore Previous Prompt](https://arxiv.org/abs/2211.09527) (Perez & Ribeiro) | 2022 | prompt injectionを最初期に体系化 | 未読 | |
| D02 | [Not what you've signed up for](https://arxiv.org/abs/2302.12173) (Greshake et al.) | AISec 2023 | **indirect prompt injectionの原点**。最優先で読む | 未読 | |
| D03 | [ToolEmu](https://arxiv.org/abs/2309.15817) (Ruan et al.) | ICLR 2024 | ツール実行をLLMで模擬し、危険な動作を検出 | 未読 | |
| D04 | [StruQ](https://arxiv.org/abs/2402.06363) (Chen et al.) | USENIX Security 2025 | 命令とデータを構造的に分離する防御 | 未読 | |
| D05 | [InjecAgent](https://arxiv.org/abs/2403.02691) (Zhan et al.) | ACL Findings 2024 | ツール統合agentへの間接injectionベンチマーク | 未読 | |
| D06 | [Spotlighting](https://arxiv.org/abs/2403.14720) (Hines et al.) | 2024 | 外部データに目印を付ける軽量防御。後続研究の定番baseline | 未読 | |
| D07 | [AgentDojo](https://arxiv.org/abs/2406.13352) (Debenedetti et al.) | NeurIPS 2024 | 攻撃と防御を同時に測る、現在の標準ベンチマーク | 未読 | |
| D08 | [AgentPoison](https://arxiv.org/abs/2407.12784) (Chen et al.) | NeurIPS 2024 | memory・RAGを汚染する攻撃 | 未読 | |
| D09 | [Agent Security Bench](https://arxiv.org/abs/2410.02644) (Zhang et al.) | ICLR 2025 | 攻撃・防御を網羅的に形式化 | 未読 | |
| D10 | [AgentHarm](https://arxiv.org/abs/2410.09024) (Andriushchenko et al.) | ICLR 2025 | agentが有害タスクを実行してしまう度合いを測る | 未読 | |

## Agent Security: 設計による防御（2025）

| # | 論文 | 状態（出版） | 何を押さえるか | 状態 | メモ |
|---|---|---|---|---|---|
| E01 | [CaMeL: Defeating Prompt Injections by Design](https://arxiv.org/abs/2503.18813) | preprint (Google DeepMind / ETH) | 信頼できるクエリから制御フローとデータフローを先に抽出し、外部データがプログラムの流れを変えられないようにする。AgentDojoでは防御なしの84%に対し、77%のタスクを安全性の保証付きで解いた | 未読 | |
| E02 | [Design Patterns for Securing LLM Agents against Prompt Injections](https://arxiv.org/abs/2506.08837) (Beurer-Kellner et al.) | preprint、2025年6月 | 権限分離の設計パターン集。ゼロトラスト的な設計の材料 | 未読 | |
| E03 | [MCPTox](https://arxiv.org/abs/2508.14925) | AAAI 2026 | 稼働中の実MCPサーバー45台・353ツールを使ったtool poisoning評価。汚染されたツールは実行されなくても、説明文を読まれるだけで攻撃が成立する | 未読 | |
| E04 | [The Attacker Moves Second](https://arxiv.org/abs/2510.09023) (Nasr et al.) | preprint、2025年10月 | 適応的な攻撃者を想定すると、既存防御の多くが破られる | 未読 | |

## Agent Security: 最新（2026）

| # | 論文 | 状態（出版） | 何を押さえるか | 状態 | メモ |
|---|---|---|---|---|---|
| F01 | [MCP-SafetyBench](https://arxiv.org/abs/2512.15163) | ICLR 2026 | 実MCPサーバー上の多段タスクで、MCP攻撃への耐性を体系的に評価 | 未読 | |
| F02 | [AgentDyn](https://arxiv.org/abs/2602.03117) | preprint | Shopping・GitHub・Daily Lifeの60タスク、560の攻撃ケース。AgentDojoで攻撃成功率をほぼゼロにできた防御が実環境でも使えるかを問い直す。評価した10の防御はほぼすべて、安全性が不十分か過剰防御のどちらか | 未読 | |
| F03 | [The Landscape of Prompt Injection Threats in LLM Agents](https://arxiv.org/abs/2602.10453) | preprint (SoK) | 既存ベンチマークで有効に見える防御の多くは文脈入力を抑え込んでいるだけで、文脈依存の推論が必要な現実の設定には一般化しない | 未読 | |
| F04 | [Skill-Inject](https://arxiv.org/abs/2602.20156) | NeurIPS 2026 poster | skillファイル経由の攻撃を202の攻撃・タスク対で評価。モデルの大型化や単純な入力フィルタでは解決せず、文脈を考慮した認可の枠組みが必要と結論 | 未読 | |
| F05 | [The Attack and Defense Landscape of Agentic AI](https://arxiv.org/abs/2603.11088) | preprint (survey) | 設計空間・攻撃・防御を一体で整理するagent securityの包括的サーベイ | 未読 | |
| F06 | [When the Manual Lies (MCP-TDP)](https://arxiv.org/abs/2605.24069) | preprint | ツール説明文の汚染を、6つのリスク分類・32の現実的ケースで評価 | 未読 | |
| F07 | [Defenses & Enablers for Skill Injection Attacks](https://arxiv.org/abs/2606.01567) | preprint | skillファイルへのアクセスを仲介する「guardian」agentによる防御を評価 | 未読 | |
| F08 | [Toward Secure LLM Agents](https://arxiv.org/abs/2606.10749) | preprint (survey) | 247本の論文を、情報フロー・委譲された権限・永続状態の3軸で統合。agent securityをプロンプト水準の安全性の延長ではなく、ソフトウェア・システムセキュリティの問題として捉える | 未読 | |

## 出典についての注意

- 2025年以降の論文は、リスト作成時にWeb検索でarXivページなどを確認したもの
- 2024年以前の定番論文は、リスト作成者の知識から挙げたもの。arXiv番号は読むときに各ページで確かめる
- MASBenchはarXiv番号が未確認のため、まとめページへのリンクにしている
