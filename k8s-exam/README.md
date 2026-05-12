# k8s-exam

## 프로젝트 구조

```
k8s-exam/
├── docker-compose/
│   ├── docker-compose.yml
│   └── app/
│       ├── Dockerfile
│       ├── build.gradle
│       ├── settings.gradle
│       └── src/main/
│           ├── java/com/exam/App.java
│           └── resources/application.properties
├── k8s/
│   └── nginx-deployment.yaml
├── screenshots/
└── README.md
```

## 문항 1 - docker-compose 실행

```bash
cd docker-compose
docker-compose up --build
```

헬스 체크:
```bash
curl http://localhost:8080/health
# 응답: OK
```

종료:
```bash
docker-compose down
```

## 문항 2 - nginx-deployment 실행

```bash
# YAML 문법 검증
kubectl apply --dry-run=client -f k8s/nginx-deployment.yaml

# 적용
kubectl apply -f k8s/nginx-deployment.yaml

# 확인
kubectl get deployment nginx-deployment
kubectl get pods -l app=nginx
```
