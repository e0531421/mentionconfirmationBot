Discord Mention Counter Bot (メンション回数カウンターBot)
指定したユーザーが、サーバー内で「誰に」「何回」メンションしたかをカウントして一覧表示するシンプルなDiscordボットです。

✨ 主な機能
メンションの集計: 特定のユーザーが送信したメッセージをスキャンし、メンションされたユーザーと回数を集計します。

ランキング表示: メンション回数が多い順に並び替えて、見やすいランキング形式で表示します。

スラッシュコマンド対応: Discordの最新のUIであるスラッシュコマンド (/who_mentioned) に対応しています。

⚙️ 必要なもの
Python 3.8 以降

Discord.py (pip install discord.py)

Discordボットアカウント及びそのトークン

🚀 導入・設定方法
1. bot.py の準備
このリポジトリにある bot.py のコードをコピーし、お使いのPCに bot.py という名前で保存してください。

2. 必要なライブラリのインストール
ターミナル（コマンドプロンプト）で以下のコマンドを実行し、discord.py ライブラリをインストールします。

Bash

pip install discord.py
3. Discordボットの準備

Discord Developer Portalにアクセスし、新しいアプリケーションを作成します。

「Bot」タブに移動し、Add Bot をクリックしてボットユーザーを作成します。

ボットのトークンをコピーしておきます。（Reset Token ボタンから確認・再発行できます）

Privileged Gateway Intents の項目にある MESSAGE CONTENT INTENT を必ず有効（ON）にしてください。

4. ボットの設定
保存した bot.py ファイルの最後の行を編集します。

Python

# 'YOUR_DISCORD_BOT_TOKEN' の部分を自分のBotトークンに書き換えてください
client.run('YOUR_DISCORD_BOT_TOKEN')
先ほどコピーしたご自身のボットトークンを 'YOUR_DISCORD_BOT_TOKEN' の部分に貼り付けてください。

5. ボットをサーバーに招待
Developer Portalの「OAuth2 > URL Generator」タブに移動します。

SCOPES で bot と applications.commands を選択します。

BOT PERMISSIONS で以下の権限を選択します。

View Channels (チャンネルを見る)

Send Messages (メッセージを送信)

Read Message History (メッセージ履歴を読む)

生成されたURLにアクセスし、ボットをあなたのDiscordサーバーに追加します。

6. ボットの起動
以下のコマンドでボットを起動します。

Bash

python bot.py
ターミナルに「〇〇としてログインしました。」と表示されれば成功です。

使い方
Discordサーバーのテキストチャンネルで、以下のスラッシュコマンドを実行します。

/who_mentioned

コマンドに続けて、メンションを調べたいユーザーを指定してください。ボットがサーバー内の発言を解析し、結果を返信します。

⚠️ 注意点
このボットは、コマンドが実行されるたびにサーバーの全メッセージ履歴をスキャンします。メッセージ数が非常に多いサーバーでは、結果が表示されるまでに時間がかかったり、DiscordのAPI制限に達したりする可能性があります。

ボットに「メッセージ履歴を読む」権限がないチャンネルは、カウントの対象外となります。

📄 ライセンス
このプロジェクトは MIT License の下で公開されています。
