### 실행순서
- my-deployment.yaml
- my-service.yaml
- my-virtualservice.yaml
- my-gateway.yaml

실행 후, 
while true; do curl http://[istio gateway ip]:80/; echo; sleep 0.5; done
500에러가 계속 나오는 것을 확인 후
- my-circuitbreaking.yaml 실행
  - 결과는 500에러가 나오다가 일정 값 이후 나오지 않을 것임
  - 주의사항은 적용 시 반드시 적용 전 DestinationRule과 적용 후 DestinationRule이 같아야 한다.

문제 발생 후 조치 사항으로는 rollback을 수행하거나 또는 subset을 적용한 v01에 가중치를 100으로 설정하여 문제를 해결
