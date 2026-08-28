[프로젝트 보고서] Voltage Divider Board Design & Simulation
1. Project Overview (프로젝트 개요)
목적: 10V DC 입력 전원을 받아 안정적인 2V DC 전압을 출력하는 전압 분배 회로 설계 및 PCB 제작 데이터 구축
주요 사양:
Input Voltage ($V_{in}$): 10V DC
Target Output Voltage ($V_{out}$): 2.0V DC
Load Resistance ($R_1, R_2$): $R_1 = 8\text{k}\Omega$, $R_2 = 2\text{k}\Omega$
사용 툴: LTspice (Simulation), KiCad 8.0 (Schematic & Layout)
2. Circuit Theory & LTspice Simulation (시뮬레이션 및 검증)
① 전압 분배 수식 검증
$$V_{out} = V_{in} \times \frac{R_2}{R_1 + R_2} = 10\text{V} \times \frac{2\text{k}\Omega}{8\text{k}\Omega + 2\text{k}\Omega} = 2.0\text{V}$$
② LTspice Transient Analysis
시뮬레이션 조건: .tran 1s (1초간 과도 응답 관찰)
결과분석: 10V DC 입력 조건에서 $V_{out}$ 노드가 오차 없이 정확히 2.0000V로 수렴함을 확인.
[첨부 1]: LTspice 회로도 및 파형 캡처 이미지 (앞서 캡처한 V(vout) = 2.0V 빨간선 그래프 이미지)
3. KiCad Schematic & PCB Layout (회로도 및 PCB 설계)
① Schematic Design
외부 전원 연결용 커넥터(J1, J2 2-Pin Header) 추가 및 ERC(Electrical Rules Check) 통과
Net Label (Vout) 설정을 통한 노드 식별성 강화
② PCB Layout Specifications
Board Dimensions: 2-Layer PCB (약 30mm x 20mm)
Component Footprints:
$R_1, R_2$: SMD 0805 Package
$J_1, J_2$: 2.54mm Pitch Pin Header
Copper Pour: Top/Bottom Layer 전체 GND Zone Fill (노이즈 방지)
DRC (Design Rules Check): 에러/미연결 패턴 0건 검수 완료
4. 3D Raytracing & Physical Verification (3D 검수 및 결과물)
[첨부 2]: KiCad 3D Viewer로 추출한 고화질 PCB 3D 렌더링 이미지 (Alt + 1 Top View, 사선 각도 뷰)
부품 배치 검수: 커넥터 및 저항 간 물리적 간섭(Clearance) 없음 확인
5. Deliverables (최종 산출물 목록)
Schematic & PCB File: KiCad 프로젝트 원본 파일
Gerber & Drill Files: 제조 공장 발주용 표준 데이터 (Gerber_VoltageDivider.zip)
Bill of Materials (BOM): 부품 목록 및 풋프린트 명세서 (CSV)
![3D Top View](docs/pcb_3d_render.png)
