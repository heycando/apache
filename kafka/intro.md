# Kafka

## Messaging/ big data pipeline
* Before
  * End to end --> data integration difficulties due to different HW/OS/bugs
  * REAL TIME + DATA dramatic increase
* After
  * producer/consumer
  * message data to multiple consumers
  * high thoughput for message optimization
  * scaling out
  
## Topic & Partition
  * message/ records 차이?
  * Topic
    * 파티션 1개이상 필요; 메시지 처리 순서는 파티션이 1개면 Queue(FIFO)처럼이지만, 여러개면 순서대로 가는 것이 보장되지 않음
  * Producer
    * 레코드 생성, 브로커로 전송
  * 전송된 레코드는 파티션에 신규 오프셋과 함께 기록
  * 컨슈머
    * 브로커로부터 레코드를 요청하여 가져감 (polling 기준으로 -> 브로커가 컨슈머로 보내는 것이 아니다.? [컨슈머(Consumer)가 브로커(Broker)로부터 메시지를 직접 가져가는 PULL방식으로 동작 
    > 컨슈머는 자신의 처리능력만큼의 메시지만 가져와 최적의 성능]
    (https://programacion.tistory.com/156))
  * 저장
    * 레코드는 파일 시스템 단위로 저장 -> DB에 저장되는 것이 아님! segment는 시간/크기 기준으로 닫힘 --> 언젠가는 사라진다..
  * 파티션과 컨슈머 갯수 ( 컨슈머 하나가 처리하는 시간이 한정적임으로, thread/ process 사용 가능하도록 [동시성/병렬성](https://atin.tistory.com/567))
    * 파티션개수 >= 컨슈머 개수
    * 문제 있을 때 rebalancing 도 존재
  * 목적에 따라 컨슈머 그룹 분리 가능
    * elastiic search(실시간 로그 확인, 시간 순서 적재); hadoop (대용량 데이터 적재, 이전 데이터 확인용) 간섭 감소
    
 ##장애 데이터
* 레코드 값
  * 역할 : 실질적으로 전달하고 싶은 데이터
  * 어떤 형(type)을 보낼 수 있나요?

* String, ByteArray, Int 등 사실상 제한 없음 어떤 데이터 포맷이 좋나요?
  * 포멧을 관리하는 다른 방법?

  * JSON 사용시 
    * CSV, TSV, JSON, Object 등 서비스의 특징에 맞게 사용 권장
       * key/value형태로서 확장성이 뛰어남. 컬럼 정보(key) 포함
  * CSV 사용시
    * 콤마(,)기준으로 데이터 구분. 용량 이득
  * (참고:컨플루언트 스키마 레지스트리) [https://github.com/confluentinc/schema-registry#quickstart-api-usage-examples]
