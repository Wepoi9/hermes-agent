<p align="center">
  <img src="assets/banner.png" alt="Hermes Agent" width="100%">
</p>

# Hermes Agent ☤
<p align="center">
  <a href="https://hermes-agent.nousresearch.com/">Hermes Agent</a> | <a href="https://hermes-agent.nousresearch.com/">Hermes Desktop</a>
</p>
<p align="center">
  <a href="https://hermes-agent.nousresearch.com/docs/"><img src="https://img.shields.io/badge/Docs-hermes--agent.nousresearch.com-FFD700?style=for-the-badge" alt="Documentation"></a>
  <a href="https://discord.gg/NousResearch"><img src="https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Discord"></a>
  <a href="https://github.com/NousResearch/hermes-agent/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License: MIT"></a>
  <a href="https://nousresearch.com"><img src="https://img.shields.io/badge/Built%20by-Nous%20Research-blueviolet?style=for-the-badge" alt="Built by Nous Research"></a>
  <a href="README.zh-CN.md"><img src="https://img.shields.io/badge/Lang-中文-red?style=for-the-badge" alt="中文"></a>
  <a href="README.ur-pk.md"><img src="https://img.shields.io/badge/Lang-اردو-green?style=for-the-badge" alt="اردو"></a>
  <a href="README.es.md"><img src="https://img.shields.io/badge/Lang-Español-orange?style=for-the-badge" alt="Español"></a>
</p>

**[Nous Research](https://nousresearch.com) が開発する、使うほど成長するAIエージェントです。** 経験からスキルを作り、使いながら磨き、知識を記憶に残すよう自ら働きかけます。過去の会話を検索し、セッションを重ねるごとにあなたへの理解も深めていきます。こうした学習の仕組みを備えたエージェントは、Hermesだけです。月額5ドルのVPSからGPUクラスター、使っていない間はほとんど費用のかからないサーバーレス環境まで、さまざまな場所で実行できます。ノートPCに縛られることもありません。クラウドVMで作業させながら、Telegramから話しかけられます。

モデルは自由に選べます。[Nous Portal](https://portal.nousresearch.com)、OpenRouter、OpenAI、自前のエンドポイントなど、[多くのプロバイダー](https://hermes-agent.nousresearch.com/docs/integrations/providers)に対応しています。`hermes model` で切り替えられ、コードの変更も特定サービスへの固定も必要ありません。

<table>
<tr><td><b>本格的なターミナルインターフェース</b></td><td>複数行編集、スラッシュコマンドの補完、会話履歴、作業の中断と指示変更、ツール出力のストリーミングに対応したフル機能のTUIを備えています。</td></tr>
<tr><td><b>いつもの場所から使える</b></td><td>Telegram、Discord、Slack、WhatsApp、Signal、CLIに、単一のゲートウェイプロセスから接続できます。音声メモの文字起こしや、プラットフォームをまたいだ会話の継続にも対応します。</td></tr>
<tr><td><b>学習を続ける仕組み</b></td><td>エージェントが整理するメモリと、定期的な保存の働きかけ。複雑なタスク後のスキル自動作成。利用中のスキル改善。LLMによる要約を組み合わせたFTS5セッション検索で、別のセッションの会話も振り返れます。<a href="https://github.com/plastic-labs/honcho">Honcho</a>による対話的なユーザーモデリングを備え、<a href="https://agentskills.io">agentskills.io</a>のオープン標準と互換性があります。</td></tr>
<tr><td><b>定期実行の自動化</b></td><td>任意のプラットフォームに結果を届けるcronスケジューラーを内蔵しています。日次レポート、夜間バックアップ、週次監査などを、自然言語で指示して無人で実行できます。</td></tr>
<tr><td><b>委任と並列処理</b></td><td>独立したサブエージェントを起動し、複数の作業を並行して進められます。RPC経由でツールを呼び出すPythonスクリプトを作れば、複数段階の処理をコンテキストコストなしのターンにまとめられます。</td></tr>
<tr><td><b>ノートPC以外でも動作</b></td><td>ローカル、Docker、SSH、Singularity、Modal、Daytona、Vercel Sandboxの7種類のターミナルバックエンドに対応しています。DaytonaとModalではサーバーレス環境を継続利用できます。使っていない間はエージェントの環境が休止し、必要なときに起動するため、セッション間の費用をほぼ抑えられます。月額5ドルのVPSからGPUクラスターまで、用途に合わせて実行できます。</td></tr>
<tr><td><b>研究用途にも対応</b></td><td>軌跡データの一括生成や圧縮に対応し、次世代のツール呼び出しモデルの学習に活用できます。</td></tr>
</table>

---

## かんたんインストール

### Linux、macOS、WSL2

```bash
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
```

### Windows（ネイティブ、PowerShell）

> **補足:** Windowsネイティブ環境では、WSLを使わずにHermesを実行できます。CLI、ゲートウェイ、TUI、各種ツールがそのまま動作します。WSL2を使う場合は、上記のLinux/macOS向けコマンドも利用できます。不具合を見つけた場合は、[issueを報告](https://github.com/NousResearch/hermes-agent/issues)してください。

PowerShellで次のコマンドを実行します。

```powershell
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

ソース版インストーラーは、Python 3.14、Node.js、npm、ripgrep、FFmpeg、Python依存パッケージの管理をPMに委ねます。Gitが見つからない場合は、検証済みのGit for WindowsアーカイブをHermesのツールストアに配置します。システムのGitは置き換えません。MSIX/App Installer版と更新管理の違いについては、[インストール方法](https://hermes-agent.nousresearch.com/docs/getting-started/installation)を参照してください。

> **Android / Termux:** aarch64端末向けに、署名済みAPTリポジトリを提供しています。タグ付きリリースの`stable`チャンネルと、プレリリースの`canary`チャンネルがあります。パッケージにはPython、Node.js、TUIが含まれます。デスクトップ／サーバー向けインストーラースクリプトではなく、[Termuxガイド](https://hermes-agent.nousresearch.com/docs/getting-started/termux)を利用してください。
>
> **Windows:** Windowsネイティブ環境を正式にサポートしています。上記のPowerShellコマンドで必要なものをすべてインストールできます。WSL2を使う場合はLinux向けコマンドも利用できます。Windowsネイティブ版は`%LOCALAPPDATA%\hermes`に、WSL2版はLinuxと同じく`~/.hermes`にインストールされます。

インストール後、シェルを再読み込みしてHermesを起動します。

```bash
source ~/.bashrc    # reload shell (or: source ~/.zshrc)
hermes              # start chatting!
```

### トラブルシューティング

#### Windows Defenderやウイルス対策ソフトが`uv.exe`をマルウェアとして検出する

ウイルス対策ソフト（Bitdefender、Windows Defenderなど）が、Hermesの`bin`フォルダーにある`uv.exe`（`%LOCALAPPDATA%\hermes\bin\uv.exe`）を隔離する場合、**誤検知**です。このファイルはAstralの`uv`で、HermesがPython環境を管理するために同梱しているRust製のパッケージマネージャーです。機械学習ベースのウイルス対策エンジンは、パッケージのダウンロードやインストールを行う未署名のRustバイナリを誤検知することがあります。

**正規のファイルであることを確認するには:**

```powershell
# Install GitHub CLI if needed
winget install --id GitHub.cli

# Login to GitHub
gh auth login

# Run verification
$uv = "$env:LOCALAPPDATA\hermes\bin\uv.exe"
$ver = (& $uv --version).Split(' ')[1]
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
$zip = "$env:TEMP\uv.zip"
Invoke-WebRequest "https://github.com/astral-sh/uv/releases/download/$ver/uv-x86_64-pc-windows-msvc.zip" -OutFile $zip -UseBasicParsing
gh attestation verify $zip --repo astral-sh/uv
Expand-Archive $zip "$env:TEMP\uv_x" -Force
(Get-FileHash "$env:TEMP\uv_x\uv.exe").Hash -eq (Get-FileHash $uv).Hash
```

attestationに「Verification succeeded」と表示され、最後の行が`True`なら問題ありません。

**Hermesを除外リストに追加するには:**
- **Windows Defender:** 管理者としてPowerShellを起動し、`Add-MpPreference -ExclusionPath "$env:LOCALAPPDATA\hermes\bin"`を実行します。
- **Bitdefender:** Bitdefenderのコンソールで例外を追加します（Protection > Antivirus > Settings > Manage Exceptions）。
- ファイルのハッシュではなく、**フォルダー**を除外してください。Hermesの更新で`uv`も更新され、バージョンごとにハッシュが変わります。

詳しくは、Astral側の報告をご覧ください: [astral-sh/uv#13553](https://github.com/astral-sh/uv/issues/13553)、[astral-sh/uv#15011](https://github.com/astral-sh/uv/issues/15011)、[astral-sh/uv#10079](https://github.com/astral-sh/uv/issues/10079)。

---

## 使い始める

```bash
hermes              # Interactive CLI — start a conversation
hermes model        # Choose your LLM provider and model
hermes tools        # Configure which tools are enabled
hermes config set   # Set individual config values
hermes config get   # Print individual config values
hermes gateway      # Start the messaging gateway (Telegram, Discord, etc.)
hermes setup        # Run the full setup wizard (configures everything at once)
hermes claw migrate # Migrate from OpenClaw (if coming from OpenClaw)
hermes update       # Update to the latest version
hermes doctor       # Diagnose any issues
```

📖 **[ドキュメント全文 →](https://hermes-agent.nousresearch.com/docs/)**

---

## APIキーを個別に集めずに使う — Nous Portal

Hermesは引き続き、好みのプロバイダーと組み合わせて使えます。一方、モデル、ウェブ検索、画像生成、TTS、クラウドブラウザーのためにAPIキーを5つも用意するのは避けたい、という場合は、**[Nous Portal](https://portal.nousresearch.com)**の1つのサブスクリプションですべて利用できます。

- **300以上のモデル** — `/model <name>`で好きなモデルを選択できます。
- **Tool Gateway** — ウェブ検索、画像生成（FAL）、音声合成（OpenAI）、クラウドブラウザー（Browser Use）をサブスクリプション経由で利用できます。追加のアカウントは不要です。

インストール直後なら、次のコマンドだけで設定できます。

```bash
hermes setup --portal
```

OAuthでログインし、Nousをプロバイダーに設定して、Tool Gatewayを有効にします。設定内容はいつでも`hermes portal info`で確認できます。詳しくは[Tool Gatewayのドキュメント](https://hermes-agent.nousresearch.com/docs/user-guide/features/tool-gateway)をご覧ください。

必要に応じて、ツールごとに自分のAPIキーを設定することもできます。ゲートウェイは一括で切り替える方式ではなく、バックエンドごとに利用できます。

---

## CLIとメッセージングのクイックリファレンス

Hermesの利用方法は2通りあります。`hermes`でターミナルUIを起動するか、ゲートウェイを実行してTelegram、Discord、Slack、WhatsApp、Signal、Emailから話しかけます。会話中に使えるスラッシュコマンドの多くは、どちらの方法でも共通です。

| 操作 | CLI | メッセージングプラットフォーム |
| ------------------------------ | --------------------------------------------- | -------------------------------------------------------------------------------- |
| 会話を始める | `hermes` | `hermes gateway setup`と`hermes gateway start`を実行し、ボットにメッセージを送信 |
| 新しい会話を始める | `/new`または`/reset` | `/new`または`/reset` |
| モデルを変更する | `/model [provider:model]` | `/model [provider:model]` |
| 性格を設定する | `/personality [name]` | `/personality [name]` |
| 直前のターンを再試行／取り消す | `/retry`、`/undo` | `/retry`、`/undo` |
| コンテキストを圧縮／使用状況を確認する | `/compress`、`/usage`、`/insights [--days N]` | `/compress`、`/usage`、`/insights [days]` |
| スキルを探す | `/skills`または`/<skill-name>` | `/<skill-name>` |
| 実行中の作業を中断する | `Ctrl+C`または新しいメッセージを送信 | `/stop`または新しいメッセージを送信 |
| プラットフォーム固有の状態を確認する | `/platforms` | `/status`、`/sethome` |

コマンド一覧は[CLIガイド](https://hermes-agent.nousresearch.com/docs/user-guide/cli)と[Messaging Gatewayガイド](https://hermes-agent.nousresearch.com/docs/user-guide/messaging)をご覧ください。

---

## ドキュメント

ドキュメントはすべて**[hermes-agent.nousresearch.com/docs](https://hermes-agent.nousresearch.com/docs/)**にあります。

| セクション | 内容 |
| --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| [クイックスタート](https://hermes-agent.nousresearch.com/docs/getting-started/quickstart) | インストールから設定、最初の会話までを2分で案内 |
| [CLIの使い方](https://hermes-agent.nousresearch.com/docs/user-guide/cli) | コマンド、キー割り当て、性格設定、セッション |
| [設定](https://hermes-agent.nousresearch.com/docs/user-guide/configuration) | 設定ファイル、プロバイダー、モデル、各種オプション |
| [Messaging Gateway](https://hermes-agent.nousresearch.com/docs/user-guide/messaging) | Telegram、Discord、Slack、WhatsApp、Signal、Home Assistant |
| [セキュリティ](https://hermes-agent.nousresearch.com/docs/user-guide/security) | コマンド承認、DMのペアリング、コンテナー分離 |
| [ツールとツールセット](https://hermes-agent.nousresearch.com/docs/user-guide/features/tools) | 40以上のツール、ツールセットの仕組み、ターミナルバックエンド |
| [スキルシステム](https://hermes-agent.nousresearch.com/docs/user-guide/features/skills) | 手順的記憶、Skills Hub、スキルの作成 |
| [メモリ](https://hermes-agent.nousresearch.com/docs/user-guide/features/memory) | 永続メモリ、ユーザープロファイル、ベストプラクティス |
| [MCP連携](https://hermes-agent.nousresearch.com/docs/user-guide/features/mcp) | MCPサーバーを接続して機能を拡張 |
| [Cronスケジュール](https://hermes-agent.nousresearch.com/docs/user-guide/features/cron) | プラットフォームへの配信に対応した定期タスク |
| [コンテキストファイル](https://hermes-agent.nousresearch.com/docs/user-guide/features/context-files) | すべての会話に反映するプロジェクトコンテキスト |
| [アーキテクチャ](https://hermes-agent.nousresearch.com/docs/developer-guide/architecture) | プロジェクト構成、エージェントループ、主要クラス |
| [コントリビューション](https://hermes-agent.nousresearch.com/docs/developer-guide/contributing) | 開発環境の構築、PRの進め方、コードスタイル |
| [CLIリファレンス](https://hermes-agent.nousresearch.com/docs/reference/cli-commands) | すべてのコマンドとフラグ |
| [環境変数](https://hermes-agent.nousresearch.com/docs/reference/environment-variables) | 環境変数の完全なリファレンス |

---

## OpenClawからの移行

OpenClawを使っていた場合、Hermesは設定、メモリ、スキル、APIキーを自動で取り込めます。

**初回セットアップ時:** セットアップウィザード（`hermes setup`）が`~/.openclaw`を自動検出し、設定を始める前に移行を提案します。

**インストール後に移行する場合:**

```bash
hermes claw migrate              # Interactive migration (full preset)
hermes claw migrate --dry-run    # Preview what would be migrated
hermes claw migrate --preset user-data   # Migrate without secrets
hermes claw migrate --overwrite  # Overwrite existing conflicts
```

取り込まれるデータ:

- **SOUL.md** — 性格設定ファイル
- **メモリ** — MEMORY.mdとUSER.mdの項目
- **スキル** — ユーザー作成のスキル → `~/.hermes/skills/openclaw-imports/`
- **コマンド許可リスト** — 承認パターン
- **メッセージング設定** — プラットフォーム設定、許可ユーザー、作業ディレクトリ
- **APIキー** — 許可リスト対象のシークレット（Telegram、OpenRouter、OpenAI、Anthropic、ElevenLabs）
- **TTSアセット** — ワークスペースの音声ファイル
- **ワークスペースの指示** — AGENTS.md（`--workspace-target`を指定）

すべてのオプションは`hermes claw migrate --help`で確認できます。dry-runで内容を確認しながらエージェントの案内で移行するには、`openclaw-migration`スキルを利用してください。

---

## コントリビューション

コントリビューションを歓迎します。開発環境の構築、コードスタイル、PRの進め方については[コントリビューションガイド](https://hermes-agent.nousresearch.com/docs/developer-guide/contributing)をご覧ください。

環境の有効化、日常の使い方、依存関係の変更、環境の終了方法は、まず[PM開発ワークフロー](website/docs/reference/package-management.md#developer-workflow)を確認してください。
[開発環境のセットアップ](CONTRIBUTING.md#development-setup)では、専用のテスト環境と検証コマンドを説明しています。

---

## コミュニティ

- 💬 [Discord](https://discord.gg/NousResearch)
- 📚 [Skills Hub](https://agentskills.io)
- 🐛 [Issues](https://github.com/NousResearch/hermes-agent/issues)
- 🔌 [computer-use-linux](https://github.com/avifenesh/computer-use-linux) — Hermesやその他のMCPホストで使えるLinuxデスクトップ操作用MCPサーバー。AT-SPIアクセシビリティツリー、Wayland/X11入力、スクリーンショット、コンポジターのウィンドウ指定に対応しています。
- 🔌 [HermesClaw](https://github.com/AaronWong1999/hermesclaw) — コミュニティ製のWeChatブリッジ。同じWeChatアカウント上でHermes AgentとOpenClawを動かせます。

---

## ライセンス

MIT — [LICENSE](LICENSE)をご覧ください。

[Nous Research](https://nousresearch.com)が開発しています。
