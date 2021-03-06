## ①課題内容（どんな作品か）
今回は卒業制作で目指している聴覚障害者支援アプリの機能を意識して製作しました。

音声認識を実行し、文字起こしをします。
そのデータを管理者側と閲覧者側のそれぞれのページで取得し、リアルタイムで反映します。

管理者側のみ文章の変更や削除が可能です。
また、管理者はルーム名・主催者名・会場名を設定でき、どこで誰が発信している情報なのかを閲覧者に提供します。
​
​
## ②工夫した点・こだわった点
文字起こしデータにそれぞれ編集・削除ボタンを割り振り、できるだけ早く文字修正ができるようにしました。
そのため、キーを取得する必要がありますが、画面が見づらくなるためキーは隠しています。

文字の編集の際には、編集ボタンを押下すると編集用テキストボックスに元の文字が表示されるようにしています。
理由は、1,2文字程度の修正の際に初めから文字を入力すると時間がかかり、その後の音声編集に遅れが出るため、
また、文字が消えてしまうと内容を忘れてしまいかねないため、管理者に配慮をしています。
また、行数が増えれば増えるほど編集の場所がわかりにくくなったり、
複数人で管理編集をする場合、だれかが編集をしているかわからなくなるため、編集中はボタンの色を黄色くすることで、
重複の編集を防止しています。

難しかったのは、ルーム名や会場名の設定です。
本来はページ（トーク）ごとにIDを割り振り、それとリレーションさせる形で各種設定をしたほうがいいかとは思いますが、
FirebaseだとトークごとのIDの割り振りが難しいため、今回は音声認識と紐づける形で各種設定の情報をテーブルに入れています。
たとえば、文字起こしが始まった後にルーム名を編集した場合、
編集完了後に次の文字起こしの命令がかかったタイミングで設定情報も更新され、
閲覧者側では最新の文字起こしデータに紐づいた設定が呼び出され、画面上部に表示されます。


​
​
## ③質問・疑問（あれば）


​
​
## ④その他（感想、シェアしたいことなんでも）
本当は音声認識がいちいち止まる＆毎回マイク許可をするのはめんどくさいので、
停止ボタンを押すまで音声認識を継続させたかったのですが、プログラムをサーバーに置いた状態でないと難しいようで、
今回は諦めました。
さくらインターネットサーバーが利用できるようになったら再挑戦したいです。