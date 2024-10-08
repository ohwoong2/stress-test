# stress-test
## 리눅스 하드웨어 스트레스 테스트

```bash
# 필요 소프트웨어 설치
sudo apt install stress-ng
```

### 시나리오 1: CPU 스트레스 테스트

CPU 코어에 부하를 주어 성능을 측정하고, CPU 사용량을 모니터링하는 테스트

- **목표**: CPU 사용률을 최대한 끌어올려 성능 확인
- **테스트 설정**: CPU 2개 코어에 100% 부하를 15초 동안 지속

```bash
stress-ng --cpu 2 --timeout 15s --metrics-brief
```

![image.png](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F9ddffc9b-709a-4ad6-8d21-5cafc03368f6%2Fimage.png/size/w=2000?exp=1728373222&sig=IHgfYO25rTKNRjufO3TxHrehjnZs_Ui_OrVl4MTREuM)

![image.png](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F2cd0c59f-9738-4499-bd6e-7931e999692e%2Fimage.png/size/w=2000?exp=1728373262&sig=OxUAfzVMMXPRMzE7KOrQ5RgVPUJtLvN8S7G-fHxy5Lg)

### 시나리오 2: 메모리 스트레스 테스트

메모리 사용량을 강제로 늘려 시스템 메모리가 부족한 상황에서 어떻게 동작하는지 확인

- **목표**: 시스템 메모리 사용률 극대화 및 스왑 메모리 사용 확인
- **테스트 설정**: 2개의 가상 메모리 작업에  8GB 메모리 할당, 15초 동안 실행

```bash
stress-ng --vm 2 --vm-bytes 8G --timeout 15s --metrics-brief
```

![image.png](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F6ab0c6fe-9bca-4831-a739-028926655e55%2Fimage.png/size/w=2000?exp=1728373265&sig=Nvm6OI6rdPwyHef0yJ7q0X32QLjPWyMiKV7-Fr6YTFI)

![image.png](https://img.notionusercontent.com/s3/prod-files-secure%2Fec5b0c54-e4b8-4aab-9659-c6c25e0c5f35%2F9ddffc9b-709a-4ad6-8d21-5cafc03368f6%2Fimage.png/size/w=2000?exp=1728373222&sig=IHgfYO25rTKNRjufO3TxHrehjnZs_Ui_OrVl4MTREuM)


## AapacheBench를 사용한 HTTP 부하 테스트
### ApacheBench설치
```sudo apt-get update
sudo apt-get install apache2-utils
```
### 테스트 명령어
```# 총 n번의 요청, c개의 동시 요청
ab -n 3000 -c 100 <http://localhost:80/>
```
### 결과 확인
![image](https://github.com/user-attachments/assets/30ec48f0-0bdb-4242-adcd-0c8f00d810a4)
