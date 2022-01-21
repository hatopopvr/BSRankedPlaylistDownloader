# BSRankedPlaylistDownloader
[Beat Saber用] Apluluさん([@aplulu_cat](https://twitter.com/aplulu_cat))作成のBeat Saber用ランク譜面の難易度別及びPP別のプレイリスト[BSRankedPlaylist](https://github.com/aplulu/bs-ranked-playlist)から `ranked_all.zip` をダウンロード・解凍し、
BeatSaberのPlaylistsディレクトリに展開・上書きするスクリプトです。


Apluluさん作成のプレイリストを使用するには [PlaylistManager](https://github.com/rithik-b/PlaylistManager) が必要です。
[ModAssistant](https://github.com/Assistant/ModAssistant) などを使用して`PlaylistManager`をインストールしてください。

## 使い方

### 導入

releaseから、`BSRankedPlaylistDownloader.zip`をダウンロードし解凍します。

- `playlist_downloader.exe`
- `config.ini`

### 設定

BeatSaberのPlaylistsディレクトリを `config.ini`の`param`、`playlist_dir`に設定します。
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

### 捕捉 

定期的に実行するには、タスクスケジューラ等に登録ください。

## 連絡先
Twitter [@hatopop_vr](https://twitter.com/hatopop_vr)
