勉強用に

* コマンドラインを使用して実行中のインスタンスのルートボリュームが存続するように変更する
* http://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/terminating-instances.html#preserving-volumes-on-termination

```bash
 $ bundle exec aws ec2 modify-instance-attribute --instance-id i-9af77769 --block-device-mappings  '[{"DeviceName":"/dev/sda1","Ebs":{"DeleteOnTermination":false}}]'
true
```

#### Peco をインストール

Homebrew を使っている場合
```
$ brew tap peco/peco
$ brew install peco
```
```
 bundle exec ec2list | peco | cut -f 3 | xargs -o -n 1 ssh
```
