# BSRankedPlaylistDownloader
[Beat Saber用] Apluluさん([@aplulu_cat](https://twitter.com/aplulu_cat))作成のBeat Saber用ランク譜面の難易度別及びPP別のプレイリスト[BSRankedPlaylist](https://github.com/aplulu/bs-ranked-playlist)から `ranked_all.zip` をダウンロード・解凍し、
BeatSaberのPlaylistsディレクトリに展開・上書きするスクリプトです。


Apluluさん作成のプレイリストを使用するには [PlaylistManager](https://github.com/rithik-b/PlaylistManager) が必要です。
[ModAssistant](https://github.com/Assistant/ModAssistant) などを使用して`PlaylistManager`をインストールしてください。

## 適用範囲
本プログラムは以下の環境でのみ動作を確認しています。
- Windows 10 pro 64bit

## 使い方

### 導入

[release](https://github.com/hatopopvr/BSRankedPlaylistDownloader/releases)から、`BSRankedPlaylistDownloader.zip`をダウンロードし、任意のディレクトリに解凍し配置します。  
※私の場合は以下に配置しています  : )
`C:\tools\playlist_downloader\playlist_downloader_1.01`

`release`の内容には以下が含まれます。

- `playlist_downloader.exe`
- `config.ini`
- `LICENSE`
- `python-used-licenses.csv`
- `README.md`

### 設定

`config.ini`を開き、BeatSaberのPlaylistsディレクトリを `param`、`playlist_dir`に設定します。  
Playlistsディレクトリは `[Beat Saberインストールディレクトリ]\Playlists` にあります。

```config.ini
[param]
# apluluさんの最新プレイリスト
url = https://github.com/aplulu/bs-ranked-playlist/releases/latest/download/ranked_all.zip

# プレイリストのディレクトリ
playlist_dir = C:\Program Files (x86)\Steam\steamapps\common\Beat Saber\Playlists

# 作業ディレクトリ
work_dir = work

# 作業ディレクトリ削除フラグ True:削除 / False:削除しない
clean_flag = True

# logディレクトリ
log_dir = log
```

`playlist_downloader.exe`を実行すると、`work_dir`に設定した作業ディレクトリと、`log_dir`に設定したlogディレクトリが作成されます。  
以下のような内容のlogが出力されておれば、正常に完了しています。

```
2022-01-21 22:22:18,231 - __main__ - INFO - ---------------------------------
2022-01-21 22:22:18,231 - __main__ - INFO - 作業を開始します。
2022-01-21 22:22:18,231 - __main__ - INFO - 作業ディレクトリを作成します。
2022-01-21 22:22:18,232 - __main__ - INFO - 作業ディレクトリの作成が完了しました。:work\20220121222218
2022-01-21 22:22:18,232 - __main__ - INFO - ダウンロードを開始します
2022-01-21 22:22:19,552 - __main__ - INFO - ダウンロードが完了しました。:work\20220121222218\ranked_all.zip
2022-01-21 22:22:19,552 - __main__ - INFO - zipの解凍を開始します。
2022-01-21 22:22:19,567 - __main__ - INFO - zipの解凍を完了しました。:work\20220121222218\ranked_all
2022-01-21 22:22:19,567 - __main__ - INFO - playlistを配置します。
2022-01-21 22:22:19,567 - __main__ - INFO - 処理対象は 19 件です。
2022-01-21 22:22:19,578 - __main__ - INFO - 19 件のplaylistの配置が完了しました。:C:\Program Files (x86)\Steam\steamapps\common\Beat Saber\Playlists
2022-01-21 22:22:19,578 - __main__ - INFO - 作業ディレクトリの削除を開始します。
2022-01-21 22:22:19,580 - __main__ - INFO - 作業ディレクトリの削除が完了しました。:work\20220121222218
2022-01-21 22:22:19,580 - __main__ - INFO - 作業が完了しました。
2022-01-21 22:22:19,580 - __main__ - INFO - ---------------------------------
```

### 捕捉 (スケジューラの設定) 

定期的に実行するには、タスクスケジューラ等をご利用ください。  
※以下は私の場合の設定例です。 : )

#### 全般
名前：BSRankedPlaylistDownloader  
操作：ユーザーがログオンしているときのみ実行する  
最上位の特権で実行する  
構成：Widnwos10  

#### 操作
プログラム/スクリプト：`C:\tools\playlist_downloader\playlist_downloader_1.01\playlist_downloader.exe`
開始(オプション)：`C:\tools\playlist_downloader\playlist_downloader_1.01`

#### トリガー
毎日、4:00、繰り返し間隔 12時間、有効

## ライセンス

このソフトウェアは、[MITライセンス](https://github.com/hatopopvr/BSRankedPlaylistDownloader/blob/main/LICENSE)のもとで公開されています。

## 各種ライブラリのライセンスについて
`playlist_downloader.exe`に内包する具体的なライブラリのライセンスについては、同梱する[python-used-licenses.csv](https://github.com/hatopopvr/BSRankedPlaylistDownloader/blob/main/python-used-licenses.csv)を参照願います。

## 連絡先
Twitter [@hatopop_vr](https://twitter.com/hatopop_vr)
