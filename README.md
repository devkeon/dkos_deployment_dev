# DKOS 개발 서버 배포 레포지토리

## 가이드

### k8s/configs/nginx.conf
- nginx 설정 파일
- 리버스 프록시로 사용, Front & Back 또한 리버스 프록시로 같이 사용 중
- cors 설정 해제 완료
- 웹소켓 upgrade 설정

### k8s/backend.yaml
- image의 todo 부분 D2Hub image url로 전환 필요
- DATABASE_URL 또한 별도의 설정 필요, 필요에 따라 환경변수 주입 필요
- **서버 포트는 8080, /api URI 사용 중임을 확인**

### k8s/frontend.yaml
- image의 todo 부분 D2Hub image url로 전환 필요
- 3000번 포트에서 사용 중임을 확인

### k8s/mysql.yaml
- MYSQL user와 password 부분 변경 필요 (추후에 secrets 작업 예정)
- 초기 sql문 삭제 및 maria DB에 맞는 설정들 삭제 (필요 시 초기 sql문 설정 가능)
- PVC: 스토리지 50Gib, ReadWriteOnce 적용

### k8s/rabbitmq.yaml
- RabbitMQ username과 password Secret으로 변경 완료.
- 스토리지 100Gi 사용
- 서버 포트는 5672, 15672, 61613 사용 중

## 주의 사항
- 변경이 필요하면 배포 담당자에게 문의한다.
- 배포는 한 번만 진행하고, 변경된 이미지로 pod를 재실행 시킨다.

<br/>

---

<br/>

#### 작성자: 이건
#### krampoline 담당자: 임현정
#### 코드 작성자 및 수정자: 임현정
#### last update: 2024/02/11
