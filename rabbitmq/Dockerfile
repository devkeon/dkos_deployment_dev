# RabbitMQ 관리 플러그인이 포함된 이미지 사용
FROM rabbitmq:management

# STOMP 플러그인 활성화
RUN rabbitmq-plugins enable --offline rabbitmq_stomp

# RabbitMQ 서비스 실행
CMD ["rabbitmq-server"]
