# sam-pipeline-work

AWS SAM + CodePipeline ハンズオン

## 事前準備: CodeCommit リポジトリの作成とソースの Push

以下の手順は CloudShell から実行します。

### 1. CodeCommit リポジトリの作成

```bash
aws codecommit create-repository --repository-name sam-pipeline-work --repository-description "SAM Pipeline Hands-on"
```

### 2. ソースファイルのアップロード

CloudShell 画面の「アクション」→「ファイルをアップロード」から `sam-pipeline-work.zip` をアップロードします。

> **事前に**: ローカル PC で sam-pipeline-work フォルダを ZIP に圧縮しておいてください。

### 3. ファイルの展開と Push

```bash
unzip sam-pipeline-work.zip -d sam-pipeline-work
cd sam-pipeline-work
git init -b main
git add .
git commit -m "Initial commit"
git remote add origin codecommit://sam-pipeline-work
git push -u origin main
```

> **補足**: CloudShell では `git-remote-codecommit` がプリインストールされており、
> IAM 認証情報も自動で使用されるため、追加の認証設定は不要です。
