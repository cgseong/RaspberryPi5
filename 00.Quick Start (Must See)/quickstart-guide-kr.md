# 퀵 스타트

## 목차
- 퀵 스타트
- 시스템 확인
- 원격 접속 시스템
- 주의사항

제품을 처음 받으셨다면, 먼저 제공된 SD 카드를 설치한 후 이 튜토리얼을 따라주세요!

## 시스템 확인
Raspberry Pi 공장 시스템은 기본적으로 핫스팟을 켜놓은 상태입니다. 휴대폰이나 컴퓨터를 사용하여 주변에 Pi_Hot이라는 이름의 핫스팟이 있는지 확인할 수 있습니다.

- Pi_Hot 핫스팟이 감지되면 시스템이 정상적으로 시작된 것입니다.
- 핫스팟이 감지되지 않으면 Raspberry Pi 메인보드의 표시등 상태를 관찰하여 판단할 수 있습니다.

### LED 표시등
Raspberry Pi 5가 정상적으로 시작되면 LED 표시등이 빨간색에서 녹색으로 바뀌고, 그 후 녹색 불이 불규칙적으로 깜박입니다!

> 만약 Raspberry Pi가 부팅에 실패하거나 어떤 이유로 종료되어야 하는 경우, LED 표시등은 일반적으로 특정 횟수만큼 깜박여서 사용자에게 경고합니다!

## 원격 접속 시스템
Raspberry Pi 공장 시스템은 기본적으로 SSH, VNC 및 핫스팟이 활성화되어 있습니다. 컴퓨터로 Raspberry Pi 핫스팟에 연결한 다음 SSH 또는 Real_VNC Viewer를 통해 Raspberry Pi 시스템에 연결할 수 있습니다.

### 시스템 정보
- 사용자 이름: pi
- 사용자 비밀번호: yahboom
- 핫스팟 이름: Pi_Hot
- 핫스팟 비밀번호: 12345678
- Jupyter lab 비밀번호: yahboom

### IP 얻기
Windows 시스템을 사용하는 경우 WiFi IP 주소를 기반으로 Raspberry Pi 핫스팟 IP 네트워크 세그먼트를 찾을 수 있습니다.

1. 터미널 열기: Win+R을 누르고 cmd를 입력한 후 Enter 누르기
2. IP 보기: 터미널에서 ipconfig 입력
3. 위 정보에 따르면 현재 Raspberry Pi 핫스팟의 네트워크 세그먼트는 10.42.0.xx에 있습니다.
4. 해결된 IP 장치 보기: arp -a 입력

여기서 10.42.0.1이 Raspberry Pi IP입니다. 여러 장치가 있는 경우 VNC를 통해 다른 IP 장치에 연결하여 테스트할 수 있습니다!

> arp -a 명령은 로컬 컴퓨터의 해결된 IP 주소와 해당 MAC 주소를 나열합니다. 이 명령으로 Raspberry Pi IP를 찾을 수 없는 경우 Advanced IP Scanner를 사용하여 동일한 네트워크 세그먼트의 장치 IP 주소를 스캔할 수 있습니다!

### VNC 연결
IP 기반으로 VNC 연결하기:

1. VNC Viewer 실행
2. 사용자 이름과 비밀번호 입력:
   - 사용자 이름: pi
   - 비밀번호: yahboom

## 주의사항
IP 기반으로 VNC 연결이 여러 번 실패하는 경우 SSH를 통해 raspi-config에 들어가서 VNC 구성을 확인할 수 있습니다.

SSH를 통한 VNC 열기 단계: [Remote Access Tutorial] 참조할 수 있습니다.

### VNC 오류 보고 활성화
VNC를 열기 전에 시스템과 소프트웨어를 업데이트하세요:

```bash
sudo apt update
sudo apt full-upgrade
```