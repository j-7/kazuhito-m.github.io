# AWSで「シンプルな構成」を作るための知見メモ

DBは「レプリカ一台」APPのインスタンスは2台、ALBでロードバランス…そんな構成を「簡単に」つくるためのメモ。

# ヘルプページを出す。

- Route53とS3で「メンテナンス中のソーリー画面」を出す
  - <http://d.hatena.ne.jp/minamijoyo/20150213/p2>

# Route53

- セキュリティ周りについて
  - <https://blog.manabusakai.com/2015/09/route53-domain-security/>

# デプロイのアイディア

## `CodeDeploy` を使う

- SpringBootのアプリをJenkinsとCodeDployでデプロイする仕組み
  - <https://qiita.com/ryosukehayashi/items/6a419ab73a98ce8e8217>
- 上記で使う「SpringBootアプリの"Fully Executable War"」について
  - <https://qiita.com/yoshidan/items/696cfa68f3dbbad8140c>
- AWS再入門、コードデプロイ編
  - <https://dev.classmethod.jp/cloud/aws/cm-advent-calendar-2015-aws-re-entering-codedeploy/>
-

# 監視

## RDSまわり

- コツ
  - <https://moomindani.wordpress.com/2014/12/15/monitoring-rds-postgresql/>

# セキュリティ

## WAF

- WAF自体の入門
  - <https://dev.classmethod.jp/security/getting-started-waf/>
- AWS WAFを使ってみよう
  - <https://qiita.com/yamakozawa-mediba/items/047065c8adca4674e625>
  - CloudFrontかALBにつけられるらしい
- 気付かぬうちに成長してるかわいい子？ AWS WAFの知られざる実力
  - <http://ascii.jp/elem/000/001/567/1567420/>
- AWS Black Belt Online Seminar 2017 AWS WAF
  - <https://www.slideshare.net/AmazonWebServicesJapan/20171122-aws-blackbeltawswafowasptop10>

## IAM

ほんとうは、AIMはセキュリティの範疇では無いかも知れないけれど

- IAMによるAWS権限管理運用ベストプラクティス
  - <https://dev.classmethod.jp/cloud/aws/iam-bestpractice-1/>

## IDS

- Amazon EC2でIDS(侵入検知システム)を導入する – AIDE –
  - <https://dev.classmethod.jp/cloud/amazon-ec2-ids-aide/>


# Applicationとデプロイ

## SpringBootとEC2

- EC2上にSpringBootアプリをデプロイ
  - <https://www.magata.net/memo/index.php?AWS%20EC2%BE%E5%A4%C7%20Spring%20Boot%A5%A2%A5%D7%A5%EA%B5%AF%C6%B0>
  - 環境変数で制御するみたい

# 個々のプロダクトの知見

## ALB

- 豆知識
  - <http://blog.serverworks.co.jp/tech/2017/02/08/alb-tagert-health-status/>
- 入門
  - <https://jyo-to.okinawa/20170611/1275/>

## s3

- VPCひも付け
  - <https://jyo-to.okinawa/20170611/1264/>

## 番外:ACM(証明書発行)

基本、今回の状況では使えない

- 簡単だよ、という話
  - <https://www.slideshare.net/IkunaWada/acmssl>

# 機能別

## スケジュール実行

- AWS Lambda の Scheduled Event を試してみた #reinvent
  - <https://dev.classmethod.jp/cloud/aws/lambda-scheduled-event/>
- スケジュールされたイベントでの AWS Lambda の使用
  - <https://docs.aws.amazon.com/ja_jp/lambda/latest/dg/with-scheduled-events.html>

## ClamAVと定義実行について

- Amazon LinuxにClamAVを導入する
  - <https://dev.classmethod.jp/cloud/aws/install-clamav-to-amazon-linux/>
- ClamAVのオンアクセススキャンついて
  - <http://tbpgr.hatenablog.com/entry/2017/04/20/080000>

## SpringBOot+SecureCookieについて

- 基本
  - <https://qiita.com/syukai/items/92d7dfc22b6ac34f9b87>

# 構築例

- 見積もりとほぼ同構成
  - <https://qiita.com/kite_999/items/6607d684412b14690901>
- 構築はしてないが、概念の説明
  - <http://stefafafan.hatenablog.com/entry/aws>
- さらにミニマムな構成例
  - <https://tech.recruit-mp.co.jp/infrastructure/retry-aws-minimum-vpc-server-environment/>
- 初心者向けSpringBootデプロイまで
  - <https://qiita.com/KevinFQ/items/119521ebd12bb7890761>
