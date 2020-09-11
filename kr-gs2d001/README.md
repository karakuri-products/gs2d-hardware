# kr-gs2d001

> gs2d 対応 シリアルサーボ・ドライバ kr-gs2d001

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91549700-49a77700-e962-11ea-84e7-53ee81f47ddc.png" alt="gs2d-hw fig.1" width="80%">
</div>

---

## 概要

kr-gs2d001 は、gs2d ライブラリに対応したシリアルサーボ・ドライバです。

本製品と gs2d ライブラリにより、 2 種類の規格 ( RS485、1 wire TTL Serial ) のシリアルサーボを PC およびマイコンから簡単に制御することができます。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91539467-54f3a600-e954-11ea-9042-991219d77496.png" alt="gs2d-hw fig.1" width="100%">
</div>

> 図 1 kr-gs2d001 外観 (左: 正面、右: 背面)

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92860439-3650dd00-f433-11ea-86e0-7f10f30b5e35.png" alt="gs2d-hw fig.1" width="100%">
</div>

> 図 2 kr-gs2d001 ブロック図

---

### 対応シリアルサーボ

kr-gs2d001 でサポートするメーカ/規格は表 2 のとおりです。対応/動作確認が完了しているシリアルサーボの機種は<a href="https://docs.google.com/spreadsheets/d/15XlF4kySq219ICrvgJmQ_NEENOpA3_AKKTeR7gI3orM/edit?usp=sharing" target="_blank">こちら</a>で確認できます。

> 表 1 サポートするメーカ/規格

| Manufacturer                     | Series                      | Protocol                             |
| -------------------------------- | --------------------------- | ------------------------------------ |
| ロボティズ (ROBOTIS Inc.)        | Dynamixel X Series          | Protocol 2.0                         |
| 近藤科学 (Kondo Kagaku Co.,Ltd.) | B3M Serises <br> KRS Series | B3M protocol <br> ICS3.6 <br> ICS3.5 |
| 双葉電子工業 (FUTABA Corp.)      | Command Type Servo          | Command Type Protocol                |

---

### 機械的仕様

> 表 2 機械的仕様

| 項目     | 仕様              |
| -------- | ----------------- |
| 基板外形 | 54.0 mm x 74.0 mm |

#### 3D モデルデータ

<a href="./3dmodel"> ./3dmodel </a>にて提供します。形式は表 3 のとおり。

> 表 3 提供モデルデータ形式一覧

| 拡張子      | 形式名                 | 備考           |
| ----------- | ---------------------- | -------------- |
| .f3d        | Autodesk FUSIN360 形式 |                |
| .iam / .ipt | Autodesk Inventor 形式 | zip 形式で圧縮 |
| .iges       | IGES 形式              |                |
| .sat        | SAT 形式               |                |
| .step       | IGES 形式              |                |

#### コネクタ配置

> 表 4 コネクタ一覧

| 番号        | 種類                  | 用途                        |
| ----------- | --------------------- | --------------------------- |
| CN1 ~ CN4   | JST-XH 4p             | KONDO B3M (RS485)           |
| CN5 ~ CN8   | JST-EH 4p             | ROBOTIS Dynamixel X (RS485) |
| CN9 ~ CN12  | JST-EH 4p             | FUTABA RS40x (RS485)        |
| CN13 ~ CN16 | JST-ZH 3p             | KONDO KRS33xx (1 wire TTL)  |
| CN17 ~ CN20 | QI(2550) 3p           | 1 wire TTL Serial 共用      |
| CN21 ~ CN24 | JST-ADH 3p            | FUTABA RS20x (1 wire TTL)   |
| CN25 ~ CN28 | QI(2550) 6p,8p x2,10p | Arduino シールド            |
| CN29        | USB typeC             | USB2.1, PD 非対応           |
| CN30        | AMASS-XT60 2p         | 電源コネクタ                |

#### 部品配置

> 表 5 主要部品一覧

| 番号    | 用途                                                                                              |
| ------- | ------------------------------------------------------------------------------------------------- |
| SW1     | RS485 / 1 wire TTL Serial 切替え (図 3)                                                           |
| SW2     | USB シリアル入力 (USB typeC 経由) / Arduino シリアル入力 (もしくは外部シリアル入力) 切替え (図 4) |
| LED1    | USB シリアル TxLED                                                                                |
| LED2    | USB シリアル RxLED                                                                                |
| LED3    | 電源 LED                                                                                          |
| SJ1/SJ2 | Arduino ハードウェア/ソフトウェア シリアル切替え (図 5)                                           |

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92323576-d8a84380-f074-11ea-918e-21c6807d2d1a.png" alt="sw1 fig.2" width="50%">
</div>

> 図 3 SW1 によるシリアル信号の通信規格の切替え<br>
> (a) RS485, (b) 1 wire TTL Serial

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92323998-5752b000-f078-11ea-8ce8-552ecd24aad4.png" alt="sw1 fig.3" width="50%">
</div>

> 図 4 SW2 による入力シリアル信号の切替え<br>
> (a) USB シリアル入力 (USB typeC 経由), (b) Arduino シリアル入力 (もしくは外部シリアル入力)

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/92750157-c5bda800-f3c1-11ea-9488-fde1afc587f0.png" alt="GettingStarted fig.1" width="50%">
</div>

> 図 5 Arduino ハードウェア/ソフトウェア シリアル切替え(SJ1/SJ2)

---

### 電気的仕様

> 表 6 電気的仕様一覧

| パラメータ          | 値           |
| ------------------- | ------------ |
| 電源電圧            | 5.0 ～ 24.0V |
| 対応入力 I/O レベル | 3.0 ～ 5.0V  |

#### 回路図

<a href="./kr-gs2d001_schematic.pdf"> kr-gs2d001_schematic.pdf </a> に示します。

---

## ライセンス

kr-gs2d001 は Apache License 2.0 とします。詳細は LICENSE 参照。
