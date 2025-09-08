# Charybdis(카리브디스) 빌드/제작 가이드

이 레포에 흩어져 있던 가이드를 하나의 문서로 통합했습니다. 아래 목차에서 필요한 섹션을 찾아 읽으시면 됩니다. 원본 개별 문서는 그대로 두되, 상단에 본 README로의 안내 링크를 추가했습니다.

## 목차
- [부품 구매 리스트](#부품-구매-리스트)
- [PCB 설계도 및 출력](#pcb-설계도-및-출력)
  - [엄지/메인 PCB](#엄지메인-pcb)
  - [트랙볼 PCB](#트랙볼-pcb)
  - [C 포트 홀더(컨트롤보드 연결용)](#c-포트-홀더컨트롤보드-연결용)
  - [컨트롤보드(알리에서 구매로 대체)](#컨트롤보드알리에서-구매로-대체)
 

---

## 부품 구매 리스트

아래 표는 최근 조사/주문 기준으로 형식을 정리했습니다. 중복 항목은 제거하고, 주문 출처별로 분리했습니다.

### PCB 주문 (JLCPCB 인보이스 기준)

| 보드 | 코드 | 수량(장) | 단가(USD) | 금액(USD) |
|---|---|---:|---:|---:|
| Adapter (C 포트 홀더) | Y4 | 5 | 0.80 | 4.00 |
| Right (오른쪽 엄지) | Y10 | 5 | 0.80 | 4.00 |
| Left (왼쪽 엄지) | Y12 | 5 | 0.82 | 4.10 |
| Main (메인) | Y9 | 10 | 1.12 | 11.20 |
| Sensor SMT (트랙볼 센서) | Y3 | 5 | 4.74 | 23.68 |

- Merchandise: $46.98, Shipping: $11.74, Discount: -$9.00, Grand Total: $49.72

### AliExpress 주문 (CSV 반영)

| 부품명 | 옵션 명 | 1패키지당 부품수 | 패키지수량 | 총부품수 | 패키지가격 | 구매가격 |
|---|---|---:|---:|---:|---:|---:|
| [TTC Frozen V2 스위치 자동 선형 3 핀 39g 스위치 게임용 기계식 키보드 RGB 키보드 음소거 스위치 AULA F75 AJAZZ AK820 - AliExpress 7](https://www.aliexpress.com/item/1005008909952057.html) | 110 PCS | 110 | 1 | 110 | ₩49,990 | ₩49,990 |
| [SMD 칩 다층 세라믹 캐패시터, 1206 1UF, 50V, 100V, 200V, 105K, X7R, 10% 3216, 20 개 - AliExpress 502](https://www.aliexpress.com/item/1005007350273364.html) | 1206 1UF 50V | 20 | 3 | 60 | ₩1,546 | ₩1,546 |
| [100pcs SMD 다이오드 0805 SOD-123 1N5819 1N4007 1N4148 SOD123 SOD-323 1206 1N4148WS 1N5819WS B5819WS SOD323 쇼트키 다이오드 - AliExp](https://www.aliexpress.com/item/1005005707644429.html) | 1N4148W SOD123 | 100 | 3 | 300 | ₩1,988 | ₩1,988 |
| [10/50/100PCS 3.5mm 잭 여성용 오디오 커넥터 4 핀 DIP 헤드폰 잭 소켓 PJ-320A PJ320A 오디오 인터페이스 오디오 잭 검정색 - AliExpress 13](https://www.aliexpress.com/item/1005003111662179.html) | 100 Pcs | 100 | 1 | 100 | ₩8,260 | ₩8,260 |
| [마이크로 버튼 택트 스위치 Smd 4pin 3x4x2.5mm - 10pcs Smd 4x4x1.5 3mm 4 4 핀 촉각-Aliexpress](https://www.aliexpress.com/item/1005001291287576.html) | 4X4X1.5 Copper | 10 | 10 | 100 | ₩256 | ₩2,560 |
| [RP2040 Pro 마이크로 라즈베리 PI PICO 개발 보드 듀얼 코어는 Mciro Python을 지원합니다. - AliExpress 502](https://www.aliexpress.com/item/1005005980167753.html) | RP2040 Pro Micro 16M | 1 | 10 | 10 | ₩3,560 | ₩35,600 |
| [50pcs M1 M1.2 M1.4 M1.6 M2 M2.5 M3 M3.5 M4 GB819 미니 소형 검정색 탄소강 크로스 필립스 플랫 카운터 싱크 헤드 나사 볼트 - AliExpress 13](https://www.aliexpress.com/item/1005003205577232.html) | M3, 8mm | 50 | 10 | 500 | ₩1,155 | ₩11,550 |
| [50pcs M1 M1.2 M1.4 M1.6 M2 M2.5 M3 M3.5 M4 GB819 미니 소형 검정색 탄소강 크로스 필립스 플랫 카운터 싱크 헤드 나사 볼트 - AliExpress 13](https://www.aliexpress.com/item/1005003205577232.html) | M4, 8mm | 50 | 10 | 500 | ₩1,396 | ₩13,960 |
| [M2 M3 M4 M5 M6 M8 Brass Heat Insert Nut Double Twill Knurled Hot Melt Injection Embed Thread Inserts Nuts For 3d Printer](https://www.aliexpress.com/item/1005008666672949.html) | Length 5mm, M4 (OD6mm) 30pcs | 30 | 10 | 300 | ₩1,752 | ₩17,520 |
| [M2 M3 M4 M5 M6 M8 Brass Heat Insert Nut Double Twill Knurled Hot Melt Injection Embed Thread Inserts Nuts For 3d Printer](https://www.aliexpress.com/item/1005008666672949.html) | Length 5mm, M3 (OD5mm) 50pcs | 50 | 10 | 500 | ₩1,938 | ₩19,380 |
| [PMW3360DM-T2QU 및 LM19-LSI DIP PMW3360 PMW3360DM 센서, 렌즈 LM19 포함, 정품, 로트당 1 개 - AliExpress 502](https://www.aliexpress.com/item/4000904265601.html) | - | 1 | 5 | 5 | ₩9,900 | ₩49,500 |
| [SMD 픽셀 LED 칩, 개별 주소 지정 가능, 풀 컬러 DC 5V, SK6812 MINI-E RGB (WS2812B 유사), SK6812 3228, 100 개 - AliExpress 36](https://www.aliexpress.com/item/1005007863635868.html) | 100개 × 5 | 100 | 5 | 500 | ₩4,000 | ₩20,000 |
| [VEICHU 컨베이어 구성 요소 VCN310/311 스테인레스 스틸 라운드 내구성 황소 휠 전송 베어링 롤러 볼 - AliExpress 13](https://www.aliexpress.com/item/1005003066404497.html) | VCN310, 7.5 | 1 | 15 | 15 | ₩1,953 | ₩29,295 |
| [Perix303 트랙볼, 탈착식 마우스 트랙볼 570, 에르고 드로잉 마우스 볼, 사용자 정의 컴퓨터 게이머 액세서리 선물, 34mm - AliExpress 7](https://www.aliexpress.com/item/1005008358261130.html) | purpel Glossy | 1 | 1 | 1 | ₩28,650 | ₩28,650 |

참고: AliExpress는 옵션(변형) 선택을 URL 파라미터로 고정하려면 각 옵션 조합의 SKU ID가 필요합니다. 원하시면 각 품목별 원하는 옵션의 `sku_id`를 알려주세요. `?sku_id=...` 형태로 링크에 반영해 바로 해당 옵션이 선택되도록 설정해 드립니다.

---

## PCB 설계도 및 출력

PCB 출력 공통 옵션: 거버 파일 업로드 후 색상만 변경. 그 외 옵션은 건드리지 않는 것을 권장합니다.

### 엄지/메인 PCB

- 두께: 전부 0.8mm, 검은색. 옵션 2개만 변경.
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

- 알리 링크: [AliExpress 제품 페이지](https://ko.aliexpress.com/item/1005001304569553.html?spm=a2g0s.9042311.0.0.27424c4dDwgcp7&gatewayAdapt=glo2kor)
- 4x4x1.5 버튼 구매
- 설계도(Elite-C holder): [Releases](https://github.com/Bastardkb/Elite-C-holder/releases)  
  현재 레포 내 기준 버전: 2.1  
- 출력 옵션: 거버 파일 업로드 후 색상만 변경.

### 컨트롤보드(알리에서 구매로 대체)

- Splinky(공식 설계도, latest): [bk3.2 Releases](https://github.com/Bastardkb/Splinky/releases/tag/bk3.2)  
- 비고: JLCPCB 생산 시 일부 부품 부재로 생산이 막힐 수 있음. 호환 부품을 직접 치환할 수 있으면 위 설계도로 진행 가능하나, 비용/수고 대비 알리 완제품 구매가 가성비가 좋음.
- 알리 링크: [RP2040 Pro Micro 16M](https://ko.aliexpress.com/item/1005005980167753.html?spm=a2g0o.cart.0.0.5f9c56baA1ySYV&mp=1&pdp_npi=5%40dis%21KRW%21KRW%203560%21KRW%203560%21%21KRW%203560%21%21%21%4021015b7d17542960956188740e0739%2112000035965729680%21ct%21KR%213017032214%21%213%210&gatewayAdapt=glo2kor)

---


본 README는 참고용으로 제공됩니다. 링크/가격/버전은 수시로 변경될 수 있으며, 최신 정보는 각 링크의 공식 문서를 확인하세요.
