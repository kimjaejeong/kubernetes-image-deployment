### 실행순서
- my-deployment.yaml
- my-service.yaml
- my-virtualservice.yaml
- my-gateway.yaml

실행 후, 
while true; do curl http://[istio gateway ip]:80/; echo; sleep 0.5; done
500에러가 계속 나오는 것을 확인 후
- my-circuitbreaking.yaml 실행
결과는 500에러가 나오다가 일정 값 이후 나오지 않을 것임
