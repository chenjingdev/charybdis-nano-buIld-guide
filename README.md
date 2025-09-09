# Charybdis(카리브디스) 빌드/제작 가이드

이 레포에 흩어져 있던 가이드를 하나의 문서로 통합했습니다. 아래 목차에서 필요한 섹션을 찾아 읽으시면 됩니다. 원본 개별 문서는 그대로 두되, 상단에 본 README로의 안내 링크를 추가했습니다.

## 목차
- [부품 구매 리스트](#부품-구매-리스트)
- [PCB 설계도 및 출력](#pcb-설계도-및-출력)
  - [엄지/메인 PCB](#엄지메인-pcb)
  - [트랙볼 PCB](#트랙볼-pcb)
  - [C 포트 홀더(컨트롤보드 연결용)](#c-포트-홀더컨트롤보드-연결용)
  - [컨트롤보드(설계 참고)](#컨트롤보드설계-참고)
 

---

## 부품 구매 리스트

### PCB 주문 (JLCPCB 인보이스 기준)

| 보드 | 버전 | 수량(장) | 단가(USD) | 금액(USD) | 나노 1대 필요(장) |
|---|---|---:|---:|---:|---:|
| [Adapter (C 포트 홀더, 좌/우 세트)](https://github.com/Bastardkb/Elite-C-holder) | v2.1 | 5 | 0.80 | 4.00 | 1 |
| [Right (오른쪽 엄지)](https://github.com/Bastardkb/Charybdis-PCB-thumbs) | v2.01 | 5 | 0.80 | 4.00 | 1 |
| [Left (왼쪽 엄지)](https://github.com/Bastardkb/TBK-Mini-PCB-thumb-cluster) | v2.1 | 5 | 0.82 | 4.10 | 1 |
| [Main (메인)](https://github.com/Bastardkb/Skeletyl-PCB-plate) | v1.3 | 10 | 1.12 | 11.20 | 2 |
| [Sensor SMT (트랙볼 센서)](https://github.com/Bastardkb/charybdis-pmw-3360-sensor-pcb) | - | 5 | 4.74 | 23.68 | 1 |

- Merchandise: $46.98, Shipping: $11.74, Discount: -$9.00, Grand Total: $49.72

#### 출력 두께(주문 기준)
- Main(Y9): 0.8mm
- Left(Y12): 0.8mm
- Right(Y10): 0.8mm
- Adapter(Y4): 1.6mm
- Sensor PCBA(Y3): 1.6mm

### AliExpress 주문

| 부품명 | 옵션 명 | 1패키지당 부품수 | 패키지수량 | 총부품수 | 패키지가격 | 구매가격 | 나노 1대 필요 수량 |
|---|---|---:|---:|---:|---:|---:|---:|
| [SMD 칩 다층 세라믹 캐패시터, 1206 1UF, 50V, 100V, 200V, 105K, X7R, 10% 3216, 20 개 - AliExpress 502](https://www.aliexpress.com/item/1005007350273364.html) | 1206 1UF 50V | 20 | 3 | 60 | ₩1,546 | ₩1,546 | 2 |
| [100pcs SMD 다이오드 0805 SOD-123 1N5819 1N4007 1N4148 SOD123 SOD-323 1206 1N4148WS 1N5819WS B5819WS SOD323 쇼트키 다이오드 - AliExp](https://www.aliexpress.com/item/1005005707644429.html) | 1N4148W SOD123 | 100 | 3 | 300 | ₩1,988 | ₩1,988 | 40 |
| [10/50/100PCS 3.5mm 잭 여성용 오디오 커넥터 4 핀 DIP 헤드폰 잭 소켓 PJ-320A PJ320A 오디오 인터페이스 오디오 잭 검정색 - AliExpress 13](https://www.aliexpress.com/item/1005003111662179.html) | 100 Pcs | 100 | 1 | 100 | ₩8,260 | ₩8,260 | 2 |
| [마이크로 버튼 택트 스위치 Smd 4pin 3x4x2.5mm - 10pcs Smd 4x4x1.5 3mm 4 4 핀 촉각-Aliexpress](https://www.aliexpress.com/item/1005001291287576.html) | 4X4X1.5 Copper | 10 | 10 | 100 | ₩256 | ₩2,560 | 2 |
| [RP2040 Pro 마이크로 라즈베리 PI PICO 개발 보드 듀얼 코어는 Mciro Python을 지원합니다. - AliExpress 502](https://www.aliexpress.com/item/1005005980167753.html) | RP2040 Pro Micro 16M | 1 | 10 | 10 | ₩3,560 | ₩35,600 | 2 |
| [50pcs M1 M1.2 M1.4 M1.6 M2 M2.5 M3 M3.5 M4 GB819 미니 소형 검정색 탄소강 크로스 필립스 플랫 카운터 싱크 헤드 나사 볼트 - AliExpress 13](https://www.aliexpress.com/item/1005003205577232.html) | M3, 8mm | 50 | 10 | 500 | ₩1,155 | ₩11,550 | 3 |
| [50pcs M1 M1.2 M1.4 M1.6 M2 M2.5 M3 M3.5 M4 GB819 미니 소형 검정색 탄소강 크로스 필립스 플랫 카운터 싱크 헤드 나사 볼트 - AliExpress 13](https://www.aliexpress.com/item/1005003205577232.html) | M4, 8mm | 50 | 10 | 500 | ₩1,396 | ₩13,960 | 6 |
| [M2 M3 M4 M5 M6 M8 Brass Heat Insert Nut Double Twill Knurled Hot Melt Injection Embed Thread Inserts Nuts For 3d Printer](https://www.aliexpress.com/item/1005008666672949.html) | Length 5mm, M4 (OD6mm) 30pcs | 30 | 10 | 300 | ₩1,752 | ₩17,520 | 8 |
| [M2 M3 M4 M5 M6 M8 Brass Heat Insert Nut Double Twill Knurled Hot Melt Injection Embed Thread Inserts Nuts For 3d Printer](https://www.aliexpress.com/item/1005008666672949.html) | Length 5mm, M3 (OD5mm) 50pcs | 50 | 10 | 500 | ₩1,938 | ₩19,380 | 8 |
| [PMW3360DM-T2QU 및 LM19-LSI DIP PMW3360 PMW3360DM 센서, 렌즈 LM19 포함, 정품, 로트당 1 개 - AliExpress 502](https://www.aliexpress.com/item/4000904265601.html) | - | 1 | 5 | 5 | ₩9,900 | ₩49,500 | 1 |
| [SMD 픽셀 LED 칩, 개별 주소 지정 가능, 풀 컬러 DC 5V, SK6812 MINI-E RGB (WS2812B 유사), SK6812 3228, 100 개 - AliExpress 36](https://www.aliexpress.com/item/1005007863635868.html) | 100개 × 5 | 100 | 5 | 500 | ₩4,000 | ₩20,000 | 40 |
| [VEICHU 컨베이어 구성 요소 VCN310/311 스테인레스 스틸 라운드 내구성 황소 휠 전송 베어링 롤러 볼 - AliExpress 13](https://www.aliexpress.com/item/1005003066404497.html) | VCN310, 7.5 | 1 | 15 | 15 | ₩1,953 | ₩29,295 | 3 |
| [Perix303 트랙볼, 탈착식 마우스 트랙볼 570, 에르고 드로잉 마우스 볼, 사용자 정의 컴퓨터 게이머 액세서리 선물, 34mm - AliExpress 7](https://www.aliexpress.com/item/1005008358261130.html) | purpel Glossy | 1 | 1 | 1 | ₩28,650 | ₩28,650 | 1 |

### 네이버 주문 (케이블/소모품)

| 품목 | 옵션 명 | 패키지 단위 | 패키지가격 | 배송비 | 1대 필요량 | 1대 비용 |
|---|---|---:|---:|---:|---:|---:|
| [테프론 와이어 AWG26 (네이버 스토어)](https://smartstore.naver.com/spec/products/5320955211) | 단선, 100m, 검정 | 100m | ₩32,000 | ₩3,000 | 4m | ₩1,400 |
| [LT소재 희성납 유연납 RS60](https://smartstore.naver.com/scpmc/products/8570030651?NaPm=ct%3Dmfb6q570%7Cci%3Dcheckout%7Ctr%3Dppc%7Ctrx%3Dnull%7Chk%3Dd363e59191ac8718c037e042832b4f84b61e113b) | 0.6mm, 500g 롤 | 500g | ₩24,000 | ₩3,000 | - | - |
| 필라멘트 (예: PLA) | 1kg 스풀 | 1kg | ₩30,000 | - | 0.33kg | ₩10,000 |

참고: 공식 설명서에서는 리본 케이블을 안내하지만 국내 조달이 어려워 위 테프론 AWG26 단선 케이블로 대체했습니다. 단선은 연선 대비 내구성이 높고 납땜이 쉬워 제작/유지보수에 유리했습니다.

### 스위치(선택 품목)

| 모델/링크 | 패키지 구성 | 패키지가격 | 나노 1대 필요 수량 | 1대 환산(참고) |
|---|---:|---:|---:|---:|
| [TTC Frozen V2 Linear 39g (110pcs)](https://www.aliexpress.com/item/1005008909952057.html) | 110개 | ₩49,990 | 40 | ₩18,178 |

---

### 나노 1대 예상 비용

- 부품 소계(KRW, 스위치 제외): ₩55,309  
  - LED 40개, RP2040 2개, 다이오드 40개, TRRS 커넥터 2개, 베어링/트랙볼 볼, 센서, 나사/인서트 등 포함  
  - 계산식: 각 행의 `(패키지가격 ÷ 1패키지당 부품수) × 나노 1대 필요 수량`
- 케이블 환산(KRW): ₩1,400 (100m/₩35,000 기준, 사용 4m)
- 필라멘트 환산(KRW): ₩10,000 (₩30,000/1kg 기준, 사용 0.33kg)
- 부품+케이블+필라멘트 소계(KRW, 스위치 제외): ₩66,709
- 스위치 환산(참고): ₩18,178 (위 선택 표 기준)
- 스위치 포함시 합계(KRW): ₩84,887
- PCB 소계(USD): $9.40  
  - Adapter $0.80 ×1, Right $0.80 ×1, Left $0.82 ×1, Main $1.12 ×2, Sensor $4.74 ×1

## PCB 설계도 및 출력

PCB 출력 공통 옵션: 거버 파일 업로드 후 색상만 변경. 그 외 옵션은 건드리지 않는 것을 권장합니다.

### 엄지/메인 PCB

- 두께(주문 기준): 메인/엄지 0.8mm, 어댑터/센서 1.6mm. 색상: 검정. 기타 설정은 기본값에서 필수 옵션 2개만 변경.
- 왼쪽(2.1 버전): [TBK-Mini-PCB-thumb-cluster](https://github.com/Bastardkb/TBK-Mini-PCB-thumb-cluster)  
  JLCPCB 청구 기준: $4.10 / 5장
- 오른쪽(2.01 버전): [Charybdis-PCB-thumbs](https://github.com/Bastardkb/Charybdis-PCB-thumbs)  
  JLCPCB 청구 기준: $4.00 / 5장
- 메인(1.3 버전): [Skeletyl-PCB-plate](https://github.com/Bastardkb/Skeletyl-PCB-plate)  
  JLCPCB 청구 기준: $11.20 / 10장
- 특이사항: 5장/10장 가격차가 크지 않음. 부품 확정 후 한 번에 여러 장 출력해 두고두고 사용하는 것을 권장.

### 트랙볼 PCB

- 설계도: [charybdis-pmw-3360-sensor-pcb Releases](https://github.com/Bastardkb/charybdis-pmw-3360-sensor-pcb/releases)  
- 카리브디스 공식 홈페이지 제공 설계도 latest 버전.
- 주의사항:  
  - bom.csv에 마우스 센서(U1001)와 커넥터(J1001) 부품 목록이 있으나, 실제 PCB 뽑을 때는 필요 없으므로 업로드 전 삭제(미삭제 시 오류).  
  - position.csv는 파일명을 cpl.csv로 변경 후 업로드해야 오류가 나지 않음.  
  - 출력 옵션은 거버 파일 업로드 후 색상만 변경.  
- 가격: $23.68 / 5장 (JLCPCB 청구서). BOM 실장 포함된 제품 구성이라 상대적으로 고가.

### C 포트 홀더(컨트롤보드 연결용)

- 설계도(Elite-C holder): [Releases](https://github.com/Bastardkb/Elite-C-holder/releases)  
  현재 레포 내 기준 버전: 2.1  
- 출력 옵션: 거버 파일 업로드 후 색상만 변경.

참고: 제공되는 거버는 좌/우 홀더가 한 장(패널)으로 합쳐진 형태입니다. 즉, 한 장 주문으로 좌/우 한 세트를 구성할 수 있습니다.

### 컨트롤보드(설계 참고)(알리구매로대체함)

- Splinky(공식 설계도, latest): [bk3.2 Releases](https://github.com/Bastardkb/Splinky/releases/tag/bk3.2)  
- 비고: JLCPCB 생산 시 일부 부품 부재로 생산이 막힐 수 있음(부품 없어서 알리 완제품으로 구매).

---


본 README는 참고용으로 제공됩니다. 링크/가격/버전은 수시로 변경될 수 있으며, 최신 정보는 각 링크의 공식 문서를 확인하세요.

---

### 완성품 사진

![완성품 1](assets/images/final_01.png)
![완성품 2](assets/images/final_02.png)
![완성품 3](assets/images/final_03.png)
![완성품 4](assets/images/final_04.png)
