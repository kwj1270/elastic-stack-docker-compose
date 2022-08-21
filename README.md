# ELK 도커 컴포즈로 구성하기

해당 프로젝트는 ELK를 도커 컴포즈로 간단하게 구성하기 위해 셋업 해놓았습니다.  
docker-compose 타입에 따라서 다양한 ELK 환경을 구성할 수 있습니다.  
  
1. docker-compose-origin.yml : 일반적인 ELK  
2. docker-compose-tls.yml : TLS가 적용된 ELK  
3. docker-compse.yml : TLS가 적용된 ELK  

## ElasticSearch 사용하기
```
./elasticsearch
```

엘라스틱 환경설정은 `./elasticsearch/config` 에서 `elasticsearch.yml` 을 수정하시면 됩니다.  
  
## Kibana 사용하기

```
./kibana
```

키바나 환경설정은 `./kibana/config` 에서 `kibana.yml` 을 수정하시면 됩니다.   


## Logstash 사용하기

```
./logstash
```
키바나 환경설정은 `./logstash/config` 에서 `logstash.yml` 을 수정하시면 됩니다.   
멀티 파이프라인을 사용하고 싶으시다면 `./logstash/config/pipelines.yml` 을 수정하시면 됩니다.   
참고로 `파이프라인 conf` 들은 `./logstash/pipeline` 에 들어있습니다.   
멀티 파이프라인 작성시 `input {}` 충돌이 일어나지 않도록 주의해주는 것이 좋습니다.   


## 파일비트 사용하기

```
./filebeat
```

filebeat 폴더에 도커 컴포즈로 파일비트를 구성하도록 준비해놓았습니다.   
다만, 도커의 경우 inode의 변경이 있을 때만 바인드 업데이트를 진행하기에   
inode가 없데이트가 되지 않는다면 사용이 조금 불편할 수 있습니다.  
따라서, 파일비트를 서버에서 내려받아 사용하시는 것을 권장합니다.   



