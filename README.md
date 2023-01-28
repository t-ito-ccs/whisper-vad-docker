# whisper-vad-docker
# Name
WhisperAIを使用したVadと連携するDockerのdocker-composeによる起動

# Requiment
```
windowsへのnVidiaドライバのインストール
WSL2
docker
docker-compose
```

# Structure
```
```

# Usage
```
1.WSL2のインストール、nVidiaドライバの設定
パワーシェルを管理者で起動し、wsl --installを実行
nVidiaのドライバを入れるとnVidia-smi(ドライバのブリッジ)が勝手にインストールされる模様
nvidia-smi -Lで設定が見れれば問題なし

2.dockerのインストール
sudo apt install -y curl
curl -s https://raw.githubusercontent.com/karaage0703/ubuntu-setup/master/install-docker.sh | /bin/bash
sudo service docker start

3.docker-composeによる起動
docker compose up -d
(docker compose upとするとコンソールにてログが確認できる)

4.localhostへの接続
WSL2ではwindows上から公開されているポートにアクセスできる為、以下にアクセスする
http://localhost:7860

5.終了時
docker compose down
(docker compose upで起動した場合は別の画面を開き上記のコマンドを実行する)
```

# Note
・volumes配下について
```
volumes配下には.cacheフォルダがあり、OpenAIの言語モデルをダウンロードしてくるようになっている。
その為、初回の処理時にはダウンロード時間分処理に時間がかかる。
```

# Author
# Licence
# Reference
・参考サイト
```
・ゲーミングPCのWindows環境セットアップ
https://zenn.dev/karaage0703/articles/211d89cc0a29a1

・Windows11 + WSL2 (Ubuntu22.04) のNVIDIA GPUについて。とnvidia-dockerをすこし
https://zenn.dev/unilorn/articles/028e0b24864599

・Whisper Webui
https://gitlab.com/aadnk/whisper-webui
```
