# 🚫 Netfilter Blocklist Firewall

> 사용자 정의 차단 목록 파일을 기반으로  
> HTTP 요청 중 `Host:` 헤더에 포함된 도메인을 **필터링 및 차단**하는 Netfilter 기반 C++ 프로그램입니다.

---

## 🧠 주요 기능

| 기능                     | 설명                                                                 |
|--------------------------|----------------------------------------------------------------------|
| ✅ 도메인 필터링          | HTTP 요청의 `Host:` 헤더를 분석하여 차단 목록에 있는 경우 패킷 DROP |
| 📂 차단 목록 파일 로드   | 텍스트 파일로부터 도메인 리스트 로드 (`blocklist.txt` 등)           |
| 📈 처리 시간 출력         | 각 패킷 처리에 걸린 시간(μs 단위) 출력                              |
| 🚀 Netfilter Queue 사용   | NFQUEUE를 활용해 커널 패킷을 사용자 공간으로 가져와 처리             |

---

## 📦 의존성

- `libnetfilter-queue`
- `g++` 또는 `clang++`
- `iptables` (패킷 경로 지정)

### 설치 (Ubuntu 기준)

```bash
sudo apt update
sudo apt install libnetfilter-queue-dev g++
