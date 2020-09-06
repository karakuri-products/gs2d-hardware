# gs2d-hardware (gs2d Hardware Manual)

> gs2d ライブラリ・ハードウェアマニュアル

---

## gs2d 対応製品

gs2d 対応が確認できているシリアルサーボ・ドライバは表 1 のとおりです。

> 表 1 　対応製品一覧

| Manufacturer           | Product Name |
| ---------------------- | ------------ |
| karakuri products Inc. | kr-gs2d001   |

karakuri products 社の kr-gs2d001 については ./kr-gs2d001 にまとめています。

---

## ドライバを自作する場合

### ハードウェア要件

gs2d に対応するシリアルサーボ・ドライバを開発する際、以下を満たしてください。

> 1. シリアル信号の送信/受信ライン間のループバックは回路的に無視すること。[↓](#ループバック処理)
> 2. 入力するシリアルおよび GPIO の I/O レベルが 5V 以下の場合は適宜、レベル変換を実装すること。[↓](#レベル変換)

### 設計例

#### ループバック処理

gs2d 対応シリアルバスの設計例を図 1 に示します。

入力するシリアルに対する送信許可信号（TxDEN）を 3 ステートバッファの制御信号に接続します。これにより信号の流れを制御し、送信コマンドの受信側へのループバックを回路的に無視することができます。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91384582-f18d4980-e869-11ea-92ae-d251a97e6583.png" alt="gs2d-hw fig.1" width="40%">
</div>

> 図 1 ループバック処理の一例

gs2d でサポートするシリアルサーボのバスの物理層は RS485、1 wire TTL Serial の 2 種に大別できます。各規格でのループバック処理の設計例は図 2、図 3 を参照ください。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91386735-a0338900-e86e-11ea-94d4-a37e213aa1b0.png" alt="gs2d-hw fig.2" width="55%">
</div>

> 図 2 RS485 方式での設計例

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91386691-898d3200-e86e-11ea-92e9-fdb574efad2a.png" alt="gs2d-hw fig.3" width="40%">
</div>

> 図 3 1 wire TTL Serial 方式での設計例

##### TxDEN について

FT232 などの USB シリアルドライバを利用する際は提供される TxDEN をそのまま活用できます。例えば、FT232 では出荷設定では CBUS2 端子に TxDEN 出力が割り当てられており、これを接続します（図 4）。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91417518-e4815200-e88b-11ea-9c82-37f3e984be1c.png" alt="gs2d-hw fig.4" width="50%">
</div>

> 図 4 FT232 での接続例

Arduino、Teensy 等のマイコンからシリアルを入力する場合、TxDEN に適当な GPIO を接続します。この GPIO をシリアル送信/受診時に適切に制御することで、コマンドのループバックを遮断します。Arduino UNO での例を図 5 に示します。

接続した GPIO の制御は gs2d-cpp ライブラリの How to Use を確認ください。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91422713-7e4bfd80-e892-11ea-8231-b1f5f4a2625a.png" alt="gs2d-hw fig.5" width="85%">
</div>

> 図 5 Arduino UNO での接続例<br>
> (この例では、ディジタルピン 2 を TxDEN として活用、シリアルはハードウェア・シリアル)

#### レベル変換

シリアルサーボ側の信号ラインは一般的に +5V レベルが採用されており、 gs2d もこれに準じます。

上記の例（図 4 ～ 5）では、入力する RX、TX、TXDEN の I/O レベルが +5V であると仮定し、直接、シリアルバス・ドライバに接続していました。しかしそうでない場合（5V 未満の場合）は双方向レベル変換回路を接続し、I/O レベルの差異を吸収してください。

双方向レベル変換回路の具体的な設計例を図 6 に示します。この設計例は V<sub>IOREF</sub> = +5V の場合も対応します。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92326035-28453a00-f08a-11ea-8c71-1b4bdedcff6f.png" alt="gs2d-hw fig.6" width="50%">
</div>

> 図 6 Nch MOS-FET を用いた双方向レベル変換回路の一例<br>
> R は 10kΩ 程度の抵抗、Q は Nch MOS-FET。V<sub>IOREF</sub> には低電圧 Lv. I/O 側の基準電圧を接続します。

図 6 を組込んだシリアルバス・ドライバの設計例を図 7 に示します。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92325756-0480f480-f088-11ea-837d-831aae6f715b.png" alt="gs2d-hw fig.７" width="80%">
</div>

> 図 7 レベル変換を組込んだシリアルバスドライバ回路の一例<br>
> (入力信号側の I/O レベルが +3.3V の場合)

より詳細な設計例は gs2d に対応済みのシリアルサーボドライバ kr-gs2d001 (karakuri products 製) の<a href="./kr-gs2d001/kr-gs2d001_schematic.pdf">回路図</a>を参照ください。

---

## ライセンス

gs2d は Apache License 2.0 とします。詳細は ./LICENSE を参照のこと。
