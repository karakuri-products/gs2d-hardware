# gs2d-hw: Hardware for Generic Serial-bus Servo Driver library
> gs2d(汎用シリアルサーボドライバ)ライブラリ対応ハードウェア情報


## gs2d対応済みハードウェア
### kr-SAC001 (karakuri products, Inc.)


## ハードウェアを自作する
### gs2d 対応要件
自作のハードウェアを **gs2d** に対応させるには RS485, TTL（1-wireシリアル）において以下の要件を満たしてください。
- 半二重通信のみ対応。
- ループバック禁止。
- フロー制御なし。


## License
Generic Serial-bus Servo Driver library uses Apache License 2.0.
