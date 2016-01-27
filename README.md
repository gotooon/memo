#最終課題
###トンネリング機能の実装
- packet in 発生時に入ってきたポートを見てカプセル化・脱カプセル化する
flow_mod の作成
- ユーザテーブルをルックアップして VM に対して packet out

###コントローラ・ユーザテーブル初期化

- 設定ファイルから読み込むようにする
- ユーザテーブルの機構を controller に実装

###ARP パケットが到着したときの実装

- ユーザテーブルをルックアップ
- source と同ユーザ管理の VM にのみ ARP を packet out する

![設計](https://github.com/gotooon/memo/blob/master/memo2.JPG)

## 頻出コマンド
`bundle install --binstubs`  
`sudo service network-manager stop (又は start)`  

## エラー時の対処
`sudo rm /tmp/*.pid`  

```bash
sudo ovs-vsctl list-br
sudo ovs-vsctl del-br
```

## trema コマンド
`./bin/trema send_packets --source host1 --dest host2`  
`./bin/trema show_stats host1`  
`./bin/trema run lib/learning_switch13.rb --openflow13 -c trema.conf`  
dump_flow の問題  
`sudo ovs-ofctl dump-flows brlsw (sw1) --protocol=OpenFlow13`  