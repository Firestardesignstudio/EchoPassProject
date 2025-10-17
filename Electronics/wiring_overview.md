# Wiring Overview  
（配線・電源・通信システムの概要）

---

## ⚡ 電源構成 / Power System
- バッテリー：リチウムイオン 3セル（11.1V / 2200mAh）  
- レギュレーター：DC 5V / 3.3V デュアル出力  
- 保護回路：ヒューズ + TVSダイオード + 過電流保護IC  

---

## 🔌 センサー接続 / Sensor Connections
| モジュール | 通信方式 | ポート | 備考 |
|-------------|------------|---------|------|
| LiDAR センサー | I2C | SDA/SCL | 前方障害物検出（〜5m） |
| 超音波センサー | UART | TX/RX | 近距離段差（0〜2m） |
| IMU（加速度・角速度） | I2C | SDA/SCL | 姿勢補正・転倒検知 |
| 照度センサー | ADC | A0 | 夜間モード切替 |

---

## 🧠 マイコン / MCU
- ESP32 または Raspberry Pi Pico W を想定  
- 通信：BLE + UART  
- AI Core（スマホアプリ or GPT連携デバイス）とBluetooth接続  

---

## 🔊 出力系 / Outputs
- ブザー出力：GPIO → トランジスタ → 圧電スピーカー  
- 振動モーター：PWM制御（左右別）  
- LEDインジケータ：電源・警告・通信状態を表示  

---

## 🛡️ セーフティー / Failsafe
- 電源異常時：自動遮断  
- 通信途絶時：ローカル制御（センサー直結モード）へ移行  

---

## 🖼️ 図版（任意）
図を追加する場合は、  
`/Assets/wiring_overview.png` をアップロードして下のように貼り付けます：  

```markdown
![Wiring Overview](../Assets/wiring_overview.png)
