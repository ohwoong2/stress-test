# 🔬 stress-test

## 🐧 리눅스 하드웨어 스트레스 테스트

먼저 필요한 소프트웨어를 설치합니다:

```bash
# 필요 소프트웨어 설치
sudo apt install stress-ng
```

### 시나리오 1: CPU 스트레스 테스트 🔥

CPU 코어에 부하를 주어 성능을 측정하고, CPU 사용량을 모니터링하는 테스트입니다.

- **목표**: CPU 사용률을 최대한 끌어올려 성능 확인
- **테스트 설정**: CPU 2개 코어에 100% 부하를 15초 동안 지속

```bash
stress-ng --cpu 2 --timeout 15s --metrics-brief
```

![CPU 스트레스 테스트 결과](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F9ddffc9b-709a-4ad6-8d21-5cafc03368f6%2Fimage.png/size/w=2000?exp=1728373222&sig=IHgfYO25rTKNRjufO3TxHrehjnZs_Ui_OrVl4MTREuM)

![CPU 사용량 모니터링](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F2cd0c59f-9738-4499-bd6e-7931e999692e%2Fimage.png/size/w=2000?exp=1728373262&sig=OxUAfzVMMXPRMzE7KOrQ5RgVPUJtLvN8S7G-fHxy5Lg)

이 테스트를 통해 CPU의 최대 성능과 안정성을 확인할 수 있습니다. 결과를 분석하여 시스템의 CPU 성능과 열 관리 능력을 평가할 수 있습니다.

### 시나리오 2: 메모리 스트레스 테스트 💾

메모리 사용량을 강제로 늘려 시스템 메모리가 부족한 상황에서 어떻게 동작하는지 확인합니다.

- **목표**: 시스템 메모리 사용률 극대화 및 스왑 메모리 사용 확인
- **테스트 설정**: 2개의 가상 메모리 작업에 8GB 메모리 할당, 15초 동안 실행

```bash
stress-ng --vm 2 --vm-bytes 8G --timeout 15s --metrics-brief
```

![메모리 스트레스 테스트 결과](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F6ab0c6fe-9bca-4831-a739-028926655e55%2Fimage.png/size/w=2000?exp=1728373265&sig=Nvm6OI6rdPwyHef0yJ7q0X32QLjPWyMiKV7-Fr6YTFI)

![메모리 사용량 모니터링](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F9ddffc9b-709a-4ad6-8d21-5cafc03368f6%2Fimage.png/size/w=2000?exp=1728373222&sig=IHgfYO25rTKNRjufO3TxHrehjnZs_Ui_OrVl4MTREuM)

이 테스트를 통해 시스템의 메모리 관리 능력과 스왑 사용 패턴을 관찰할 수 있습니다. 결과를 분석하여 메모리 부족 상황에서의 시스템 안정성과 성능을 평가할 수 있습니다.

## 🌐 ApacheBench를 사용한 HTTP 부하 테스트

### ApacheBench 설치 🛠️

```bash
sudo apt-get update
sudo apt-get install apache2-utils
```

### 테스트 명령어 🚀

```bash
# 총 n번의 요청, c개의 동시 요청
ab -n 3000 -c 100 http://localhost:80/
```

### 결과 확인 📊

![ApacheBench 테스트 결과](https://github.com/user-attachments/assets/30ec48f0-0bdb-4242-adcd-0c8f00d810a4)

이 HTTP 부하 테스트를 통해 웹 서버의 성능과 안정성을 평가할 수 있습니다. 결과를 분석하여 서버의 응답 시간, 초당 처리 가능한 요청 수, 그리고 동시 접속자 처리 능력 등을 확인할 수 있습니다. 이는 실제 운영 환경에서 예상되는 트래픽을 시뮬레이션하고 서버의 성능을 최적화하는 데 도움이 됩니다.
