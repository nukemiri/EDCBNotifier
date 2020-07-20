
# EDCBNotifier

EDCB から LINE や Twitter（ツイート・DM）に通知を送るツールです。

## About・Feature

xtne6f 版 EDCB のバッチファイル実行機能を使い、

- LINE (LINE Notify)
- Twitter (ツイート)
- Twitter (ダイレクトメッセージ)

に EDCB の通知を送信できる Python 製ツールです。

たとえば、EDCB で録画が開始されたときに LINE で録画開始を番組名を添えて通知したり、EPG 自動予約で追加された予約を通知で確認することができます。

LINE への通知は LINE Notify を使って送信します。  
LINE Notify はアプリケーションからの通知を指定したユーザーやグループで受信することができるサービスです。  
通知メッセージは LINE Notify の公式アカウントから受信できます（一度使ってみたほうが早いかも）。

Twitter への通知はツイートでの通知に加え、ダイレクトメッセージでの送信も可能です。  
ダイレクトメッセージは自分宛てに送ることも、DM を送信できる他のアカウントに送ることもできます。  
たとえば、録画通知用の Twitter アカウントを作ってメインアカウントと相互フォローになり、録画通知用のアカウントからメインアカウント宛てに通知を送ることもできます。

通知できるイベントは、

- 予約を追加したとき (PostAddReserve.bat が実行されたとき)
- 予約を変更したとき (PostChgReserve.bat が実行されたとき)
- 録画を開始したとき (PostRecStart.bat が実行されたとき)
- 録画を終了したとき (PostRecEnd.bat が実行されたとき)
- 更新通知が送られたとき (PostNotify.bat が実行されたとき)

の 5 つです。

それぞれのイベントは、個別に通知するかどうかを設定できます。  
更新通知が頻繁に送られてきてうるさい、といったときに［更新通知が送られたとき］のイベントだけ通知しないようにすることも可能です。

通知するメッセージは 5 つのイベントごとに自由に変更できます。  
設定ファイルは Python スクリプトなので、Python の知識があればメッセージをより高度にカスタマイズすることもできそうです。  
EDCB からのマクロに加えて、放送局名から取得したハッシュタグや更新通知タイプ、放送局名やタイトル名の英数字の半角変換など、独自のマクロも用意しています。

## License
[MIT Licence](LICENSE.txt)
