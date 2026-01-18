#  SMART_CAR_SYSTEM: 차량 원격 스마트 제어 플랫폼

SMART_CAR_SYSTEM은 차량의 AI 기반 자동 및 수동 와이퍼 제어 및 운전 및 주차 제어 기능, 온도에 따른 냉공조 시스템
웹을 통해 차량의 다양한 기능을 제어할 수 있어 사용자에게 편리한 환경을 제공합니다.

## 📌 주요 기능

### 🚗 차량 제어 기능
웹을 통해 차량을 원격으로 제어할 수 있습니다.
- **차량 시동**: On/Off
- **워셔액**: on/off
- **차량 와이퍼**: AI 카레라 및 온습도 센서를 통한 자동 제어 및 수동제어
- **차량 냉공조 시스템**: On/Off(온도 및 습도에 따라 자동 제어 기능 제공)
- **차량 주행**: 정밀 주행 기능

### 📊 차량 조작 기능
차량의 상태를 실시간으로 모니터링할 수 있습니다.
- **차량 속도**: 차량 속도 제어
- **차량 와이퍼**: AI모드 및 단계 조절
- **워셔액**: on/off 제어

## 🎥 시연 영상

아직 없음,

## 🛠 하드웨어 구성

### Sensor Side

#### Arduino Water Pump
- 워셔액 분사 펌프
#### DHT11
- 온도 및 습도:
#### SW-420
- 진동 감지 센서 모듈
#### SZH-SSBH-022]
- 빗물 감지 센서 모

### P298P
- 차량 움직임 제어 모터 쉴드
#### sh02-DC Motor
- 차량 움직임 제어
#### 360° Servo Motor
- 차량 와이퍼 제어
#### Nucelo-L073RZ
- 센서 데이터 수신 및 차량 상태 관리
- ESP32와 통신하여 데이터를 웹 서버로 전송
- 웹에서 수신한 제어 명령에 따라서 출력 액추에이터 제어

### ESP32-WROOM-32D
- Master로부터 받은 차량 상태 데이터를 웹 서버로 전송
- 웹에서 받은 제어 명령을 Master로 전달

## 💻 소프트웨어 구성

### 🔧 임베디드 시스템
- **개발 언어**: C
- **IDE**: stm32CubeIde
- **통신 프로토콜**: UART, Wi-Fi
  
### 🌐 웹 서비스
- **개발 언어**: JavaScript
- **프레임워크**: Node.js, HTML, css

## 📝 시스템 개발 설계서
아직 안함

### 센서 통신 데이터 포맷
- uint8_t 15Byte
- 000(온도) 000(습도) 000(조도) 000(진동감지) 000(가변저항, 속도)

### 차량 상태 통신 데이터 포맷
- uint8_t 31Byte
- 0(차량상태변화여부) 000(온도) 000(습도) 000(조도) 000(진동감지) 000(가변저항) 000(문) 000(에어컨) 000(선루프) 000(시동) 000(주행여부)

### 차량 제어 신호 통신 데이터 포맷
- uint8_t 1Byte
- 차량시동: 0(OFF), 1(ON)
- 선루프: 2(닫힘), 3(열림)
- 에어컨: 4(OFF), 5(ON)
- 차량주행: 6(정지), 7(출발)
- 차량문: 8(닫힘), 9(열림)

## 📝 네트워크 아키텍처
![Image](https://github.com/user-attachments/assets/119b2d35-065a-4dc8-aee6-edbe255dfb72)

## 🏗️ Diagram & Flow Chart

<details>
  <summary>Master Module Diagram</summary>
  
  ![Master Module Diagram](https://github.com/user-attachments/assets/309f9c15-96fc-469d-b278-12c671c6e387)
  
</details>

<details>
  <summary>Master Module Flow Chart</summary>
  
  ![Master Module Flow Chart](https://github.com/user-attachments/assets/d94fef61-37fb-48cc-89ea-5dd366291ff3)
  
</details>

<details>
  <summary>Motor Diagram</summary>
  
  ![Motor Diagram](https://github.com/user-attachments/assets/807776d4-246f-493d-b008-205df00c5da6)
  
</details>

<details>
  <summary>Motor Flow Chart</summary>
  
  ![Motor Flow Chart](https://github.com/user-attachments/assets/04972059-63fa-4cfe-b032-dc8be511e854)
  
</details>

<details>
  <summary>Speaker Diagram</summary>
  
  ![Speaker Diagram](https://github.com/user-attachments/assets/9d0cb3d9-9f90-4ba3-bee1-cda989d74c4c)
  
</details>

<details>
  <summary>Speaker Flow Chart</summary>
  
  ![Speaker Flow Chart](https://github.com/user-attachments/assets/0e1576d3-f61a-4670-9eb7-c7cdee1cb51c)
  
</details>

<details>
  <summary>Fan Diagram</summary>
  
  ![Fan Diagram](https://github.com/user-attachments/assets/bb50f7b3-042c-4f9c-9e5c-d20421285946)
  
</details>

<details>
  <summary>Fan Flow Chart</summary>
  
  ![Fan Flow Chart](https://github.com/user-attachments/assets/6564d808-7397-4785-8f13-6193738c2173)
  
</details>

<details>
  <summary>Sensor Module Diagram</summary>
  
  ![Sensor Module Diagram](https://github.com/user-attachments/assets/d7176046-fcf0-4899-8b1f-f603b8ba44e5)
  
</details>

<details>
  <summary>Sensor Module Flow Chart</summary>
  
  ![Sensor Module Flow Chart](https://github.com/user-attachments/assets/fd4d89c6-145b-4a3e-90c2-6036b7739eb6)
  
</details>

<details>
  <summary>LCD Module Diagram</summary>
  
  ![LCD Module Diagram](https://github.com/user-attachments/assets/3e43e31a-51d9-4665-a4e4-fb9c08b584c1)
  
</details>

<details>
  <summary>LCD Module Flow Chart</summary>
  
  ![LCD Module Flow Chart](https://github.com/user-attachments/assets/e328ec43-b0e0-4b6a-829f-d42af1b9bbaf)
  
</details>

<details>
  <summary>ESP32 Module Diagram</summary>
  
  ![ESP32 Module Diagram](https://github.com/user-attachments/assets/ff6f4926-d3c5-4b63-8aa1-907b31ce2cd4)
  
</details>

<details>
  <summary>ESP32 Module Flow Chart</summary>
  
  ![ESP32 Module Flow Chart](https://github.com/user-attachments/assets/44c073f0-d86c-47a0-b99c-3991eef1fc7c)
  
</details>


## 📌 프로젝트 구조
```
Hyundai-embedded-project/
│── ESP32/          # ESP32 코드
│── lcd/            # LCD 코드
│── master/         # Master 코드
│── sensor/         # Sensor 코드
└── README.md       # 프로젝트 설명 파일
```

## 팀 구성원

| 이름 | GitHub |
|------|--------|
| 이상빈 | [@ideal402](https://github.com/ideal402) |
| 옥창희 | [@okchangheeok](https://github.com/okchangheeok) |
| 류우경 | [@lolololoop](https://github.com/lolololoop) |
| 김우성 | [@woosmile](https://github.com/woosmile) |
