# Getting Started with kr-gs2d001

> kr-gs2d001 の使い方

---

## 目次

### 準備編

- A: Arduino シールドとして使う [↓](#gs2d-arduino)
- B: マイコンに接続して使う [↓](#gs2d-mcu)
- C: PC に接続して使う [↓](#gs2d-pc)

<!-- 
### シリアルサーボを動かしてみる

- C++ で動かしてみる
- Python で動かしてみる
- C# で動かしてみる
-->
---

<a id="gs2d-arduino"></a>

### A: Arduino シールドとして使う

kr-gs2d001 を Arduino シールドとして使う場合、以下の (A-1[↓](#A-1)), (A-2[↓](#A-2)) を設定し、Arduino に接続します [↓](#A-3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/93052091-7b2d7b80-f6a0-11ea-9c1b-2f12ed3a96af.png" alt="GettingStarted fig.a1" width="100%">
</div>

> 図 A1, Arduino シールドとして利用する場合の設定

<a id="A-1"></a>

#### (A-1) スイッチ (SW1, SW2) の設定

**SW2** を ○ 側に合わせ、シリアルサーボへの入力信号を **Arduino シリアル入力** 設定に切替えます(図 A2) 。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92737777-6312df00-f3b6-11ea-9eda-c513566714ba.png" alt="GettingStarted fig.a2" width="22%">
</div>

> 図 A2, SW2 の設定

制御するシリアルサーボの通信規格にあわせて **SW1** を切替え、設定します(図 3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92323576-d8a84380-f074-11ea-918e-21c6807d2d1a.png" alt="GettingStarted fig.a3" width="50%">
</div>

> 図 A3, SW1 の設定

<a id="A-2"></a>

#### (A-2) ジャンパ (SJ1, SJ2) の設定

Arduino には、ハードウェアシリアルとソフトウェアシリアルの 2 系統のシリアル通信が用意されています。

利用するシリアルの種類に応じて **基板背面のジャンパ (SJ1, SJ2) をハンダでショートし、kr-gs2d001 に接続するシリアル信号を切替えてください**。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92750157-c5bda800-f3c1-11ea-9488-fde1afc587f0.png" alt="GettingStarted fig.A4" width="50%">
</div>

> 図 A4, 基板背面のジャンパ(SJ1, SJ2)

**SJ1, SJ2 を H 側にショート**させると **Arduino のハードウェアシリアルピン(RX:CN27-1, TX:CN27-2)を kr-gs2d001 に接続** します(図 A5)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92754194-90b35480-f3c5-11ea-8cac-c1611a017025.png" alt="GettingStarted fig.A5" width="40%">
</div>

> 図 A5, ハードウェアシリアルを利用する場合

他方、**S 側にショート**させると **Arduino のソフトウェアシリアルピン(RX:CN27-4, TX:CN27-5)を kr-gs2d001 に接続** します(図 A6)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92754903-47afd000-f3c6-11ea-804f-ca9b2ebc3b7d.png" alt="GettingStarted fig.A6" width="40%">
</div>

> 図 A6, ソフトウェアシリアルを利用する場合

<a id="A-3"></a>

#### ピンヘッダの接続

CN25 ~ CN28 に 2.54mm ピンヘッダ（plug）をハンダ付けし、Arduino と接続します(図 A7)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92746214-04516380-f3be-11ea-8cc5-35892a9308fe.png" alt="GettingStarted fig.2" width="90%">
</div>

> 図 A7, kr-gs2d001 と Arduino との接続 (図は Arduino UNO R3 との接続例)

#### 電源の供給

---

<a id="gs2d-mcu"></a>

### B: マイコンに接続して使う

以下の (B-1[↓](#B-1)), (B-2[↓](#B-2)) を設定し、マイコンを接続します [↓](#B-3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/93052191-9ef0c180-f6a0-11ea-8ee9-599a20382aa1.png" alt="GettingStarted fig.B1" width="100%">
</div>

> 図 B1, マイコンに接続して使う場合の設定

<a id="B-1"></a>

#### (B-1) スイッチ (SW1, SW2) の設定

**SW2** を ○ 側に合わせ、シリアルサーボへの入力信号を **外部シリアル入力** 設定に切替えます(図 B2) 。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92737777-6312df00-f3b6-11ea-9eda-c513566714ba.png" alt="GettingStarted fig.B2" width="22%">
</div>

> 図 B2, SW2 の設定

制御するシリアルサーボの通信規格にあわせて **SW1** を切替え、設定します(図 B3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92323576-d8a84380-f074-11ea-918e-21c6807d2d1a.png" alt="GettingStarted fig.B3" width="50%">
</div>

> 図 B3, SW1 の設定

<a id="B-2"></a>

#### (B-2) ジャンパ (SJ1, SJ2) の設定

**基板背面のジャンパ (SJ1, SJ2)** を図 B4 中の **H 側もしくは S 側のいずれか一方にハンダでショート** し、外部シリアル信号を入力します。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92750157-c5bda800-f3c1-11ea-9488-fde1afc587f0.png" alt="GettingStarted fig.B4" width="50%">
</div>

> 図 B4, 基板背面のジャンパ(SJ1, SJ2)

**SJ1, SJ2 を H 側にショート**させると **kr-gs2d001 の RX に CN27-1 を、TX に CN27-2 を接続** します(図 B5)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/93054977-2d674200-f6a5-11ea-8b38-f72b3f7a1a77.png" alt="GettingStarted fig.B5" width="40%">
</div>

> 図 B5, H 側をショートさせた場合

他方、**S 側にショート**させると **kr-gs2d001 の RX に CN27-4 を、TX に CN27-5 を接続** します(図 B6)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/93055052-4839b680-f6a5-11ea-8685-5e5405c77e6d.png" alt="GettingStarted fig.B6" width="40%">
</div>

> 図 B6, S 側をショートさせた場合

---

<a id="gs2d-pc"></a>

### C: PC と接続して使う

以下の (C-1[↓](#C-1)) を設定し、PC を接続します [↓](#C-3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/93052646-8208be00-f6a1-11ea-8fc2-460c527c0e0e.png" alt="GettingStarted fig.2" width="100%">
</div>

> 図 C1, PC と接続して使う場合の設定

<a id="C-1"></a>

#### (C-1) スイッチ (SW1, SW2) の設定

**SW2** を ● 側に合わせ、シリアルサーボへの入力信号を **kr-gs2d001 内蔵 USB シリアル入力** 設定に切替えます(図 B2) 。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/93056268-2b05e780-f6a7-11ea-80e6-0c67b471df63.png" alt="GettingStarted fig.C2" width="22%">
</div>

> 図 C2, SW2 の設定

制御するシリアルサーボの通信規格にあわせて **SW1** を切替え、設定します(図 C3)。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92323576-d8a84380-f074-11ea-918e-21c6807d2d1a.png" alt="GettingStarted fig.C3" width="50%">
</div>

> 図 C3, SW1 の設定
---

## ライセンス

kr-gs2d001 は Apache License 2.0 とします。詳細は LICENSE 参照。
