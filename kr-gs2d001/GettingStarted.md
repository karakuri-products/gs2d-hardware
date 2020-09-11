# Getting Started with kr-gs2d001

> kr-gs2d001 の使い方

---

## 目次

### 準備編

- A: Arduino シールドとして使う [↓](#gs2d-arduino)
- B: マイコンに接続して使う [↓](#gs2d-mcu)
- C: PC に接続して使う [↓](#gs2d-pc)

### シリアルサーボを動かしてみる

- C++ で動かしてみる
- Python で動かしてみる
- C# で動かしてみる

---

<a id="gs2d-arduino"></a>

### A: Arduino シールドとして使う

kr-gs2d001 を Arduino シールドとして使う場合、以下の (1[↓](#A-1)), (2[↓](#A-2)) を設定し、Arduino に接続します [↓](#A-3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92864593-40c1a580-f438-11ea-8548-93780ff27515.png" alt="GettingStarted fig.a-1" width="90%">
</div>

> 図 1, Arduino シールドとして利用する場合の設定

<a id="A-1"></a>

#### (1) スイッチ (SW1, SW2) の設定

**SW2** を ○ 側に合わせ、シリアルサーボへの入力信号を **Arduino シリアル入力** 設定に切替えます(図 1) 。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92737777-6312df00-f3b6-11ea-9eda-c513566714ba.png" alt="GettingStarted fig.a-1" width="22%">
</div>

> 図 1, SW2 の設定

制御するシリアルサーボの通信規格にあわせて **SW1** を切替え、設定します(図 2)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92323576-d8a84380-f074-11ea-918e-21c6807d2d1a.png" alt="sw1 fig.2" width="50%">
</div>

> 図 2, SW1 の設定

<a id="A-2"></a>

#### (2) ジャンパ (SJ1, SJ2) の設定

Arduino には、ハードウェアシリアルとソフトウェアシリアルの 2 系統のシリアル通信が用意されています。

kr-gs2d001 を Arduino シールドとして使う場合、利用するシリアルの種類に応じて **基板背面のジャンパ (SJ1, SJ2) をハンダでショートさせ、kr-gs2d001 に接続するシリアル信号を切替える必要** があります。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92750157-c5bda800-f3c1-11ea-9488-fde1afc587f0.png" alt="GettingStarted fig.1" width="50%">
</div>

> 図 1 ハードウェアシリアルを利用する場合

**SJ1, SJ2 を H 側にショート**させると **Arduino のハードウェアシリアルピン(RX:CN27-1, TX:CN27-2)に接続** します(図 1)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92754194-90b35480-f3c5-11ea-8cac-c1611a017025.png" alt="GettingStarted fig.1" width="40%">
</div>

> 図 1 ハードウェアシリアルを利用する場合

他方、**S 側にショート**させると **Arduino のソフトウェアシリアルピン(RX:CN27-4, TX:CN27-5)に接続** します(図 2)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92754903-47afd000-f3c6-11ea-804f-ca9b2ebc3b7d.png" alt="GettingStarted fig.2" width="40%">
</div>

> 図 2 ソフトウェアシリアルを利用する場合

<a id="A-3"></a>

#### ピンヘッダの接続

CN25 ~ CN28 に 2.54mm ピンヘッダ（plug）をハンダ付けし、Arduino と接続します(図 3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92746214-04516380-f3be-11ea-8cc5-35892a9308fe.png" alt="GettingStarted fig.2" width="90%">
</div>

> 図 2 kr-gs2d001 と Arduino との接続 (図は Arduino UNO R3 との接続例)

---

<a id="gs2d-mcu"></a>

### B: 外部マイコンに接続して使う

---

<a id="gs2d-pc"></a>

### C: PC と接続して使う

---

## ライセンス

kr-gs2d001 は Apache License 2.0 とします。詳細は LICENSE 参照。
