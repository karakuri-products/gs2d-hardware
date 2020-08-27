# gs2d-hw (gs2d Hardware Manual)

> gs2d ライブラリ・ハードウェアマニュアル

---

## ハードウェア要件

gs2d に対応するシリアルサーボ・ドライバを開発する際は、以下を満たしてください。

> - シリアル信号の送信/受信ライン間のループバックは回路的に無視すること。

### 設計例

設計例を図 1 に示します。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91384582-f18d4980-e869-11ea-92ae-d251a97e6583.png" alt="gs2d-hw fig.1" width="50%">
</div>

> 図 1 ループバック処理の一例

入力するシリアルに対応する送信許可信号（TxDEN）を、図 1 のとおり 3 ステートバッファの制御信号に接続します。これによりコマンド送信時の受信側へのループバックを回路的に無視できます。

現在、シリアルバスサーボの物理層の規格は RS485、1 wire TTL Serial の 2 種に大別できます。各規格におけるループバック処理の設計例は図 2、図 3 を参照ください。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91386735-a0338900-e86e-11ea-94d4-a37e213aa1b0.png" alt="gs2d-hw fig.2" width="70%">
</div>

> 図 2 RS485 方式での設計例

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91386691-898d3200-e86e-11ea-92e9-fdb574efad2a.png" alt="gs2d-hw fig.3" width="50%">
</div>

> 図 3 1 wire TTL Serial 方式での設計例

#### TxDEN について

FT232 などの USB シリアルドライバを利用する際はピン上の TxDEN をそのまま活用できます。

Arduino、Teensy 等のマイコンからシリアルを入力する場合は、適当な GPIO を接続し、シリアル送信/受診時に適切に駆動し、コマンドのループバックを遮断できるように設計してください。

## gs2d 対応製品

gs2d への対応が確認できている製品は表 1 のとおりです。

> 表 1 　対応製品一覧

| Manufacturer                                        | Product Name |
| --------------------------------------------------- | ------------ |
| 株式会社 karakuri products (karakuri products Inc.) | kr-gs2d001   |

karakuri products 社の kr-gs2d001 については ./kr-gs2d001 にまとめています。

## ライセンス

gs2d は Apache License 2.0 とします。詳細は ./LICENSE を参照のこと。
