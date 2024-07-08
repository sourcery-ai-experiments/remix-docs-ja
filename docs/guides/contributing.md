---
title: 貢献
description: Remix に貢献していただきありがとうございます！プルリクエストを送信する前に知っておくべきことをすべてご紹介します。
---

# Remix への貢献

Remix の開発を安定して、安定して、オープンにすることを目指しています。これは、私たちを素晴らしいユーザーのコミュニティなしではできません！

このドキュメントでは、開発プロセスと環境のセットアップ方法について説明します。

**作業が受け入れられる可能性を高めるために、貢献する前にこのドキュメントをよくお読みください！**

## 貢献者ライセンス契約

プルリクエストを送信するすべての貢献者は、貢献の所有権を明示的に私たちに譲渡する貢献者ライセンス契約（CLA）に署名する必要があります。

プルリクエストを開始すると、remix-cla-bot が CLA を確認し、[contributors.yml][contributors_yaml] に名前を追加することで署名するように促します。

[CLA を読む][cla]

## ロール

このドキュメントでは、次のロールを持つ貢献者を参照しています。

- **管理者**: 管理権限を持つ GitHub 組織チーム。ロードマップを設定および管理します。
- **コラボレーター**: 書き込みアクセス権を持つ GitHub 組織チーム。問題、PR、ディスカッションなどを管理します。
- **貢献者**: あなた！

---

## 開発プロセス

### 機能開発

新しい機能のアイデアがある場合は、プルリクエストを送信しないでください。代わりに、次のプロセスに従ってください。

1. 貢献者は [GitHub ディスカッション][proposals] に **提案** を追加します。
2. Remix **管理者チーム** は **ロードマッププランニング** 会議で提案を受け入れます。
   - 提案は、管理者が提案から **問題** を作成し、問題を [**ロードマップ**][roadmap] に追加した場合に受け入れられます。
3. 管理者は、問題に **所有者** を割り当てます。
   - 所有者は、API、動作、実装に関するすべての決定を含め、機能の提供を担当します。
   - 所有者は、より大きな問題のために他の貢献者と協力して作業を編成します。
   - 所有者は、Remix チームの内外からの貢献者になる場合があります。
4. 所有者は提案から **RFC** を作成し、開発を開始できます。
5. 特に最初の方では、ペアプログラミングが強く推奨されます。

### バグ修正プルリクエスト

バグを見つけたと思われる場合は、それを修正する PR を送っていただければ幸いです！次のガイドラインに従ってください。

1. 貢献者は、プルリクエストに修正とともに失敗するテストを追加します。
   - 最初のコミットは、失敗するテストとそのテストを修正するコードの変更にするのが理想的です。
   - これは厳密には強制されませんが、非常に高く評価されます！
2. 管理者は、ロードマッププランニングの一環として、オープンなバグ修正 PR を確認します。
   - 簡単なバグ修正はすぐにマージされます。
   - その他はロードマップに追加され、所有者に割り当てられて作業を確認し、仕上げます。

テストケースのないバグ修正 PR は、すぐに閉じられる場合があります（一部のものはテストが難しいですが、ここでは判断力を使用します）。

### バグレポート問題

バグを見つけたと思われるが、PR を送信する時間がない場合は、次のガイドラインに従ってください。

1. Stackblitz、Replit、CodeSandbox などの、私たちが訪問してバグを観察できる場所で、問題の最小限の再現を作成します。

   - [https://remix.new][https_remix_new] はこれを非常に簡単にします。

2. これが不可能な場合（ホスティング設定に関連しているなど）、バグを観察するための明確な手順を README に記述して実行できる GitHub リポジトリを作成してください。

3. 問題を開いて再現へのリンクを貼ります。

再現のないバグレポートは、すぐに閉じられ、再現を求められます。

### ロードマッププランニング会議

Remix の開発を、ライブストリーミングされたプランニング会議で常に確認できます。

- Remix 管理チームは毎週会合を開き、コミュニティに進捗状況を報告し、ロードマップに提案と検証済みバグを追加します。
  - Remix 管理者間の満場一致で、ロードマップに提案を追加する必要があります。
  - 提案は「拒否」されず、「受け入れ」られるだけです。
  - 貢献者は、提案に引き続き投票し、コメントできます。提案に新しいアクティビティがある場合は、将来のレビューのためにバブルアップされます。
  - Remix 管理チームは、何らかの理由で提案をロックする場合があります。
- 会議は [Remix YouTube チャンネル][youtube] でライブストリーミングされます。
  - 会議中は、[Discord][discord] の `#roadmap-livestream-chat` に誰でも参加できます。
  - Remix コラボレーターは参加を招待されています。

### 問題追跡

ロードマップの問題が大きい場合は（複数のタスク、作成者、PR などを伴う）、管理チームによって一時的なプロジェクトボードが作成されます。

- 元の問題は、ロードマッププロジェクトに残って一般的な進捗状況を確認できます。
- サブタスクは、一時的なプロジェクトで追跡されます。
- 作業が完了したら、一時的なプロジェクトはアーカイブされます。
- 所有者は、問題をサブプロジェクトに表示し、作業を配信可能な作業の塊に分割する責任があります。
- 長期実行ブランチよりもビルド/機能フラグが推奨されます。

### RFC

- 計画されているすべての問題には、問題が _計画済み_ から _進行中_ に移動する前に、正式な RFC ディスカッションカテゴリに RFC が投稿されている必要があります。
- 一部の提案は、すでに十分な RFC になっている場合があり、正式な RFC ディスカッションカテゴリに移動するだけです。
- RFC が投稿されたら、開発を開始できますが、所有者は、必要に応じて方向を変更するために、コミュニティからのフィードバックを考慮することが期待されます。

### 所有者へのサポート

- 所有者は、[Discord][discord] の `#collaborators` プライベートチャネルに追加され、アーキテクチャと実装に関するヘルプを受けることができます。このチャネルはプライベートなので、ノイズを最小限に抑え、管理者がメッセージを見逃さず、所有者がブロックを解除できるようにします。所有者は、他のチャネルやどこでもこれらの質問について話し合うこともできます！
- 管理者は、所有者と積極的に協力して、問題とプロジェクトが整理されていること（正しいステータス、関連する問題へのリンクなど）、ドキュメント化され、前進していることを確認します。
- 進捗状況が停滞している場合は、問題の所有者を再割り当てすることができます。

### 毎週のロードマップレビュー

毎週、Remix チームと外部の **所有者** はロードマップのレビューを招待されます。

- ブロッカーを特定する
- チームとコミュニティ内のペアプログラミングの機会を見つける

### コラボレーターの役割

リポジトリをきれいに整理された状態に保つために、コラボレーターは次の操作を実行します。

### 問題タブ

- 再現のないバグレポートは、すぐに閉じられ、再現を求められます。
- 提案にするべき問題は、提案に変換されます。
- 質問は、**Q＆A ディスカッション** に変換されます。
- 有効な再現がある問題は、**検証済みバグ** としてラベル付けされ、ロードマッププランニング会議で管理者によってロードマップに追加されます。

### プルリクエストタブ

- **開発プロセス** を経ていない機能は、すぐに閉じられ、代わりにディスカッションを開くように要求されます。
- テストケースのないバグ修正 PR は、すぐに閉じられ、テストを求められる場合があります（一部のものはテストが難しいですが、コラボレーターはここで判断力を使用します）。

---

## 開発セットアップ

コードベースに貢献するには、リポジトリをフォークする必要があります。これは、どのタイプの貢献をしているかによって少し異なります。

次の手順で、このリポジトリへの変更の貢献をセットアップできます。

1. リポジトリをフォークします（[このページ][fork] の右上にある <kbd>Fork</kbd> ボタンをクリックします）。

2. フォークをローカルにクローンします。

   ```shellscript nonumber
   # ターミナルで、クローンを配置する親ディレクトリに cd し、その後
   git clone https://github.com/<your_github_username>/remix.git
   cd remix

   # *コードの変更* を行う場合は、必ず dev ブランチをチェックアウトしてください。
   git checkout dev
   ```

3. `pnpm` を実行して依存関係をインストールします。`npm` を使用してインストールすると、不要な `package-lock.json` ファイルが生成されます。

4. `npx playwright install` を実行して Playwright をインストールし、テストを正しく実行できるようにします。または、[Visual Studio Code プラグイン][vscode_playwright] を使用します。

5. `pnpm test` を実行して、ローカル開発のためにすべてが設定されていることを確認します。

### ブランチ

**重要**: GitHub で PR を作成する際には、ベースを正しいブランチに設定してください。

- **`dev`**: コードの変更用です。
- **`main`**: ドキュメントと一部のテンプレートの変更用です。

PR を作成するときに、GitHub で「変更を比較する」の見出しの下にあるドロップダウンでベースを設定できます。

<img src="https://raw.githubusercontent.com/remix-run/react-router/main/static/base-branch.png" alt="" width="460" height="350" />

### テスト

このプロジェクトでは、`jest` と `playwright` を組み合わせてテストに使用しています。integration フォルダーには統合テストのスイートがあり、パッケージには独自の jest 設定があり、その後、プロジェクトのルートにあるプライマリ jest 設定で参照されます。

統合テストとプライマリテストは、`npm-run-all` を使用して並行して実行でき、テストが可能な限り迅速かつ効率的に実行されます。これらの 2 つのテストセットを個別に実行するには、個々のスクリプトを実行する必要があります。

- `pnpm test:primary`
- `pnpm test:integration`

プロジェクト、ファイル、テストのフィルタリングのための監視プラグインもサポートしています。フィルタリングするには、`--testNamePattern`、`--testPathPattern`、`--selectProjects` を組み合わせて使用できます。例：

```shellscript nonumber
pnpm test:primary --selectProjects react --testPathPattern transition --testNamePattern "initial values"
```

これらのための監視モードプラグインもあります。そのため、`pnpm test:primary --watch` を実行して `w` を押すと、使用可能な監視コマンドが表示されます。

または、`cd` でそのプロジェクトに移動し、`pnpm jest` を実行することで、プロジェクトを完全に独立して実行できます。これにより、そのプロジェクトの jest 設定が取得されます。

## 開発ワークフロー

### パッケージ

Remix は、複数のパッケージのコードをホストするためにモノレポを使用しています。これらのパッケージは `packages` ディレクトリにあります。

[pnpm workspaces][pnpm_workspaces] を使用して、依存関係のインストールとさまざまなスクリプトの実行を管理しています。すべてをインストールするには、リポジトリのルートから `pnpm install` を実行します。

### ビルド

リポジトリのルートから `pnpm build` を実行すると、ビルドが実行されます。`pnpm watch` で監視モードでビルドを実行できます。

### プレイグラウンド

アプリ用の機能を開発しているときに、実際のアプリと対話できることは非常に役立つことがよくあります。そのため、アプリを `playground` ディレクトリに配置すると、ビルドプロセスによってすべての出力が自動的に `playground` ディレクトリ内のすべてのアプリの `node_modules` にコピーされます。ライブリロードイベントもトリガーされます！

新しいプレイグラウンドを生成するには、次を実行します。

```shellscript nonumber
pnpm playground:new <?name>
```

プレイグラウンドの名前はオプションで、デフォルトでは `playground-${Date.now()}` です。その後、生成されたディレクトリに `cd` し、`npm run dev` を実行します。別のターミナルウィンドウで `pnpm watch` を実行すると、ライブリロードの魔法 🧙‍♂️ で好きな Remix 機能を開発できます。

`pnpm playground:new` から生成されたプレイグラウンドは、`scripts/playground/template` のテンプレートに基づいています。テンプレートを何か変更したい場合は、`scripts/playground/template.local` にカスタムテンプレートを作成できます。これは `.gitignored` なので、自由にカスタマイズできます。

### テスト

テストを実行する前に、ビルドを実行する必要があります。ビルド後、リポジトリのルートから `pnpm test` を実行すると、**すべてのパッケージ** のテストが実行されます。特定のパッケージのテストを実行する場合は、`pnpm test:primary --selectProjects <display-name>` を使用してください。

```shellscript nonumber
# すべてのパッケージをテストする
pnpm test

# @remix-run/express のみをテストする
pnpm test:primary --selectProjects express
```

## リポジトリのブランチング

このリポジトリでは、さまざまな目的のために別のブランチが維持されています。これらは次のようになります。

```
- main   > 最新のリリースと現在のドキュメント
- dev    > 安定リリース間のコードの積極的な開発中
```

さまざまな機能と実験のための他のブランチがある場合がありますが、すべての魔法はこれらのブランチから発生します。

## ナイトリーリリースの仕組みは？

ナイトリーリリースは、`main` ブランチからアクションファイルをスケジュールされたワークフローとして実行します。スケジュールされたワークフローは常にデフォルトブランチの最新のコミットを使用します。これは、[ナイトリーアクションファイルのこのコメント][nightly_action_comment] によって示されます。ただし、ナイトリーリリースのカット元であるため、セットアップ中は `dev` ブランチをチェックアウトします。そこから、git SHA が同じかどうかを確認し、何か変更があった場合にのみ新しいナイトリーをカットします。

## エンドツーエンドテスト

Remix のすべてのリリース（安定版、実験版、ナイトリー版、プレリリース版）について、`create-remix` からすべての公式アダプターで Remix アプリをエンドツーエンドで完全にテストし、それらを本番環境にデプロイします。これは、デフォルトの [テンプレート][templates] と、Fly と Arc の CLI を使用して実行されます。その後、いくつかの簡単な Cypress アサーションを実行して、開発とデプロイされたアプリの両方が正常に動作していることを確認します。

[proposals]: https://github.com/remix-run/remix/discussions/categories/proposals
[roadmap]: https://github.com/orgs/remix-run/projects/5
[youtube]: https://www.youtube.com/@Remix-Run/streams
[discord]: https://rmx.as/discord
[contributors_yaml]: https://github.com/remix-run/remix/blob/main/contributors.yml
[cla]: https://github.com/remix-run/remix/blob/main/CLA.md
[fork]: https://github.com/remix-run/remix
[pnpm_workspaces]: https://pnpm.io/workspaces
[vscode_playwright]: https://playwright.dev/docs/intro#using-the-vs-code-extension
[nightly_action_comment]: https://github.com/remix-run/remix/blob/main/.github/workflows/nightly.yml#L8-L12
[templates]: ./templates
[https_remix_new]: https://remix.new

