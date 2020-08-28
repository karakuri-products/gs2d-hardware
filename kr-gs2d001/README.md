# kr-gs2d001

> gs2d 対応 シリアルサーボ・ドライバ kr-gs2d001

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91548695-ba4d9400-e960-11ea-8d6d-0a661d43565c.png" alt="gs2d-hw fig.1" width="80%">
</div>

---

## 概要

kr-gs2d001 は、gs2d ライブラリに対応したシリアルサーボ・ドライバです。

本製品と gs2d ライブラリにより、 2 種類の規格 ( RS485、1 wire TTL Serial ) のシリアルサーボを PC およびマイコンから簡単に制御することができます。

<div align="center">
    <img src="https://user-images.githubusercontent.com/15685007/91539467-54f3a600-e954-11ea-9042-991219d77496.png" alt="gs2d-hw fig.1" width="100%">
</div>

> 図 1 kr-gs2d001 外観 (左: 正面、右: 背面)

### 機械的仕様

> 表 1 機械的仕様

| 項目     | 仕様              |
| -------- | ----------------- |
| 基板外形 | 54.0 mm x 74.0 mm |

#### コネクタ配置

> 表 2 コネクタ一覧

| 番号        | 種類                  | 用途                          |
| ----------- | --------------------- | ----------------------------- |
| CN1 ~ CN4   | JST-XH 4p             | KONDO B3M (RS485)             |
| CN5 ~ CN6   | JST-EH 4p             | ROBOTIS Dynamixel X (RS485)   |
| CN9 ~ CN12  | JST-EH 4p             | FUTABA RS40x (RS485)          |
| CN13 ~ CN16 | JST-ZH 3p             | KONDO KRS33xx (1 wire TTL)    |
| CN17 ~ CN20 | QI(2550) 3p           | 1 wire TTL Serial 共用        |
| CN21 ~ CN24 | JST-ADH 3p            | FUTABA RS20x (1 wire TTL)     |
| CN25 ~ CN28 | QI(2550) 6p,8p x2,10p | Arduino シールド              |
| CN29        | CX90M-16P             | USB typeC (USB2.1, PD 非対応) |
| CN30        | AMASS-XT60 2p         | 電源コネクタ                  |

#### 部品配置

> 表 3 主要部品一覧

| 番号    | 用途                                                  |
| ------- | ----------------------------------------------------- |
| SW1     | 1 wire TTL Serial / RS485 切替え                      |
| SW2     | Arduino (もしくは外部シリアル入力) / USB-typeC 切替え |
| LED1    | USB シリアル TxLED                                    |
| LED2    | USB シリアル RxLED                                    |
| LED3    | 電源 LED                                              |
| SJ1/SJ2 | Arduino ハードウェア/ソフトウェア シリアル切替え      |

### 電気的仕様

| パラメータ | 値           |
| ---------- | ------------ |
| 電源電圧   | 5 ～ 24V |
| 対応IOレベル | 3.0 ～ 5V |

---

## ライセンス

kr-gs2d001 は Apache License 2.0 とします。詳細は LICENSE 参照。
