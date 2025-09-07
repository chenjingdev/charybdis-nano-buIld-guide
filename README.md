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

아래는 제작에 필요한 주요 부품을 표로 정리했습니다. 부품명(링크)을 클릭하면 구매/참고 페이지로 이동합니다. 가격/재고는 변동될 수 있으니 구매 전 다시 확인하세요.

| 부품명 | 가격(패키지) | 패키지 수량 | 1대 필요 수량 | 1대 비용 |
|---|---:|---:|---:|---:|
| [나사 (규격 선택)](https://ko.aliexpress.com/item/1005006815826506.html?spm=a2g0o.cart.0.0.5f9c56baA1ySYV&mp=1&pdp_npi=5%40dis%21KRW%21KRW%201503%21KRW%20978%21%21KRW%20829%21%21%21%4021015b7d17542960956188740e0739%2112000038395985085%21ct%21KR%213017032214%21%215%210&gatewayAdapt=glo2kor) | - | - | - |  |
| 히트 인서트 M4 5mm OD6mm (30pcs) | 1,752원 | 30 | - |  |
| 히트 인서트 M3 5mm OD5mm (50pcs) | 1,938원 | 50 | - |  |
| [베어링](https://ko.aliexpress.com/item/1005003066404497.html?spm=a2g0o.cart.0.0.5f9c56baA1ySYV&mp=1&pdp_npi=5%40dis%21KRW%21KRW%202171%21KRW%201953%21%21KRW%201933%21%21%21%4021015b7d17542960956188740e0739%2112000023742247065%21ct%21KR%213017032214%21%213%210&gatewayAdapt=glo2kor) | - | - | 3 |  |
| [SMD 다이오드 (1N4148 SOD-123)](https://ko.aliexpress.com/item/1005003194674618.html?spm=a2g0o.productlist.main.3.96101Dr01Dr0ow&algo_pvid=b5cfc52d-412c-4784-94c4-21f35d6dd5e2&algo_exp_id=b5cfc52d-412c-4784-94c4-21f35d6dd5e2-2&pdp_ext_f=%7B%22order%22%3A%22199%22%2C%22eval%22%3A%221%22%7D&pdp_npi=4%40dis%21KRW%21513%21513%21%21%210.36%210.36%21%40212e520d17543139952171048eba45%2112000024602962919%21sea%21KR%213017032214%21X&curPageLogUid=RfdoxE136ZaO&utparam-url=scene%3Asearch%7Cquery_from%3A) | 예: 513원 | - | 40 |  |
| [케페시터 50V (60개)](https://ko.aliexpress.com/item/1005007350273364.html?spm=a2g0o.order_detail.order_detail_item.3.43675ccdiuI7qY&gatewayAdapt=glo2kor) | 4,157원 | 60 | - |  |
| [리본 케이블 (네이버 스토어)](https://smartstore.naver.com/spec/products/5320955211?NaPm=ct%3Dmf9oxihc%7Cci%3Dcheckout%7Ctr%3Dppc%7Ctrx%3Dnull%7Chk%3D50c081cdf807c9175ef8d4ae90eb14b9ea825efe) | - | - | 1 |  |
| [스페이서 M4 OD6mm 5mm (300pcs)](https://ko.aliexpress.com/item/1005008666672949.html?spm=a2g0o.order_detail.order_detail_item.3.2bce5ccdzeoPn8&gatewayAdapt=glo2kor) | 17,500원 | 300 | 8 |  |
| [스페이서 M3 OD5mm 5mm (500pcs)](https://ko.aliexpress.com/item/1005008666672949.html?spm=a2g0o.order_detail.order_detail_item.3.2bce5ccdzeoPn8&gatewayAdapt=glo2kor) | 19,380원 | 500 | 8 |  |
| [오디오 커넥터 (100pcs)](https://ko.aliexpress.com/item/1005003111662179.html?spm=a2g0o.order_list.order_list_main.15.21ef140fA7MsY6&gatewayAdapt=glo2kor) | 8,260원 | 100 | 2 |  |
| [M3 나사 8mm (500pcs)](https://ko.aliexpress.com/item/1005003205577232.html?spm=a2g0o.order_list.order_list_main.25.21ef140fA7MsY6&gatewayAdapt=glo2kor) | 10,352원 | 500 | 20 |  |
| [M4 나사 8mm (500pcs)](https://ko.aliexpress.com/item/1005003205577232.html?spm=a2g0o.order_list.order_list_main.30.21ef140fA7MsY6&gatewayAdapt=glo2kor) | 12,512원 | 500 | 12 |  |
| [PMW3360 센서/렌즈 (5개)](https://ko.aliexpress.com/item/4000904265601.html?spm=a2g0o.order_list.order_list_main.35.21ef140fA7MsY6&gatewayAdapt=glo2kor) | 44,364원 | 5 | 1 |  |
| [스위치 (10개)](https://ko.aliexpress.com/item/1005001291287576.html?spm=a2g0o.order_list.order_list_main.40.21ef140fA7MsY6&gatewayAdapt=glo2kor) | 7,710원 | 10 | 40 |  |
| [SK6812 MINI-E RGB LED](https://ko.aliexpress.com/item/1005007863635868.html?spm=a2g0o.order_list.order_list_main.45.21ef140fA7MsY6&gatewayAdapt=glo2kor) | 4,000원 | - | - |  |
| SMD 택트 스위치 4x4x1.5 (10pcs) | 256원 | 10 | - |  |
| SMD 저항 330Ω 1206 (pack) | 529원 | - | - |  |
| MJ310 볼 베어링 7.5mm (1pcs) | 2,360원 | 1 | 3 |  |
| Perix303 트랙볼 볼 (Purple Glossy) | 28,650원 | 1 | 1 |  |
| [RP2040 Pro Micro 16M (10개)](https://ko.aliexpress.com/item/1005005980167753.html?spm=a2g0o.order_list.order_list_main.50.21ef140fA7MsY6&gatewayAdapt=glo2kor) | 35,600원 | 10 | 2 |  |
| [왼쪽 엄지 PCB (2.1)](https://github.com/Bastardkb/TBK-Mini-PCB-thumb-cluster) | 약 $4.1 | 5장 | 1 |  |
| [오른쪽 엄지 PCB (2.01)](https://github.com/Bastardkb/Charybdis-PCB-thumbs) | 약 $4.0 | 5장 | 1 |  |
| [메인 PCB (1.3)](https://github.com/Bastardkb/Skeletyl-PCB-plate) | 약 $11.2 | 10장 | 2 |  |
| [트랙볼 센서 PCB](https://github.com/Bastardkb/charybdis-pmw-3360-sensor-pcb/releases) | 약 $23.68 | 5장 | 1 |  |
| [C 포트 홀더 PCB](https://github.com/Bastardkb/Elite-C-holder/releases) | - | - | 2 |  |
| 합계(원) |  |  |  | - |
| 합계(USD) |  |  |  | - |

---

## PCB 설계도 및 출력

PCB 출력 공통 옵션: 거버 파일 업로드 후 색상만 변경. 그 외 옵션은 건드리지 않는 것을 권장합니다.

### 엄지/메인 PCB

- 두께: 전부 0.8mm, 검은색. 옵션 2개만 변경.
- 왼쪽(2.1 버전): [TBK-Mini-PCB-thumb-cluster](https://github.com/Bastardkb/TBK-Mini-PCB-thumb-cluster)  
  예상가: 약 $4.1 / 5장
- 오른쪽(2.01 버전): [Charybdis-PCB-thumbs](https://github.com/Bastardkb/Charybdis-PCB-thumbs)  
  예상가: 약 $4 / 5장
- 메인(1.3 버전): [Skeletyl-PCB-plate](https://github.com/Bastardkb/Skeletyl-PCB-plate)  
  예상가: 약 $11.2 / 10장
- 특이사항: 5장/10장 가격차가 크지 않음. 부품 확정 후 한 번에 여러 장 출력해 두고두고 사용하는 것을 권장.

### 트랙볼 PCB

- 설계도: [charybdis-pmw-3360-sensor-pcb Releases](https://github.com/Bastardkb/charybdis-pmw-3360-sensor-pcb/releases)  
- 카리브디스 공식 홈페이지 제공 설계도 latest 버전.
- 주의사항:  
  - bom.csv에 마우스 센서(U1001)와 커넥터(J1001) 부품 목록이 있으나, 실제 PCB 뽑을 때는 필요 없으므로 업로드 전 삭제(미삭제 시 오류).  
  - position.csv는 파일명을 cpl.csv로 변경 후 업로드해야 오류가 나지 않음.  
  - 출력 옵션은 거버 파일 업로드 후 색상만 변경.  
  - 가격: 약 $23.68 / 5장. BOM 실장 포함된 제품 구성이라 상대적으로 고가.

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
