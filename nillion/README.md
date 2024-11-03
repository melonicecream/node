> linux 를 기준으로 작성함

1. [공식 가이드](https://verifier.nillion.com/verifier)
2. [NIL faucet](https://faucet.testnet.nillion.com/) * 24시간 마다
3. docker 설치 - `curl -fsSL get.docker.com -o get-docker.sh && sh get-docker.sh`
4. `docker container run --rm hello-world` * 매우 작은 이미지이고 실행 성공후 제거됨
5. `docker pull nillion/verifier:v1.0.1` * verifier 이미지 가져오기
6. `mkdir -p nillion/verifier` * 로컬 볼륨 생성
7. `docker run -v ./nillion/verifier:/var/tmp nillion/verifier:v1.0.1 initialise`
    - 여기서 나온 pub, account 키를 1번 페이지에서 입력
8. 7번에서 나온 account 키로 파우셋 다시 받기(2번 이용)
    - [explorer](https://testnet.nillion.explorers.guru/)
9. `docker run -d -v ./nillion/verifier:/var/tmp nillion/verifier:v1.0.1 verify --rpc-endpoint "https://testnet-nillion-rpc.lavenderfive.com"`
10. `docker logs -f <container>`
11. ` nillion/verifier/credentials.json` 백업

## 한방 구동팩
TBD

## 관련 페이지
- https://verifier.nillion.com/verifier
- https://faucet.testnet.nillion.com
- https://testnet.nillion.explorers.guru/