[AWS](https://aws.amazon.com/?nc2=h_lg)
=======================================
Client의 수 증가에 따른 구조 변경 확인

3만
--
VPC + Public ELB
-	MYSQL
-	[VPC](https://aws.amazon.com/ko/documentation/vpc/)
	- 	Amazon Virtual Private Cloud(Amazon VPC)는 Amazon Web Services(AWS) 리소스를 고객이 정의한 가상 네트워크에서 실행할 수 있는 서비스입니다. 이 가상 네트워크는 AWS의 확장 가능한 인프라를 사용한다는 이점과 함께 고객의 자체 데이터 센터에서 운영하는 기존 네트워크와 매우 유사합니다.
-	[Public ELB](https://docs.aws.amazon.com/ko_kr/elasticloadbalancing/latest/classic/elb-manage-subnets.html)
	- 	VPC에서 클래식 로드 밸런서에 대한 서브넷을 추가 또는 제거

15만
---
VPC + Public ELB + DB Replication + Jira/Wiki + Jenkins + Memcached + RabbitMQ

-	MYSQL Master + Slave
- 	[CloudWatch](https://aws.amazon.com/ko/cloudwatch/)
	-	Amazon CloudWatch는 AWS 클라우드 리소스와 AWS에서 실행되는 애플리케이션을 위한 모니터링 서비스입니다. Amazon CloudWatch를 사용하여 지표를 수집 및 추적하고, 로그 파일을 수집 및 모니터링하며, 경보를 설정하고, AWS 리소스 변경에 자동으로 대응할 수 있습니다. Amazon CloudWatch는 Amazon EC2 인스턴스, Amazon DynamoDB 테이블, Amazon RDS DB 인스턴스 같은 AWS 리소스뿐만 아니라 애플리케이션과 서비스에서 생성된 사용자 정의 지표 및 애플리케이션에서 생성된 모든 로그 파일을 모니터링할 수 있습니다. Amazon CloudWatch를 사용하여 시스템 전반의 리소스 사용률, 애플리케이션 성능, 운영 상태를 파악할 수 있습니다. 이러한 통찰력을 사용하여 문제에 적절히 대응하고 애플리케이션 실행을 원활하게 유지할 수 있습니다. 
- 	[Memcached](https://github.com/memcached/memcached) 
	- 	메모리 캐싱 시스템
	- 	![With Memcached](https://memcached.org/memcached-usage.png)

- 	[Rabbit MQ](https://www.rabbitmq.com/)
- 	[Jira](https://ko.atlassian.com/software/jira)
- 	[Wiki](https://www.mediawiki.org/wiki/MediaWiki)
- 	CMS
- 	[Jenkins](https://jenkins.io/)
	- 	로컬빌드 후 패키지 EC2에 복사하고 실행을 대신 해줌

100만
---
VPC + Public ELB + DB Replication + Jira/Wiki + Jenkins + Memcached + RabbitMQ
+ Auto Scaling + AWS RDS, DMS, SQS, ElastiCache 
+ ELK (Elastic Search + Log Stash + Kibana)
-	[Auto Scaling](https://aws.amazon.com/ko/about-aws/whats-new/2018/01/introducing-aws-auto-scaling/) Group 추가
	-	AWS Auto Scaling은 애플리케이션을 모니터링하고 용량을 자동으로 조정하여, 최저 가격으로 안정적이고 예측 가능한 성능을 유지합니다. AWS Auto Scaling을 사용하면 몇 분 안에 여러 서비스에 걸쳐 여러 리소스에 대해 조정을 설정할 수 있습니다. AWS Auto Scaling은 단순하면서도 강력한 사용자 인터페이스를 제공합니다. 그러한 사용자 인터페이스를 통해 Amazon EC2 인스턴스와 스팟 플릿, Amazon ECS 작업, Amazon DynamoDB 테이블 및 Amazon Aurora 복제본에 대해 조정 계획을 수립할 수 있습니다.   
-	MySQL 관리 불가 
	-	[`AWS RDS`](https://aws.amazon.com/ko/rds/)로 이관, [`AWS DMS`](https://aws.amazon.com/ko/dms/)를 이용한 마이그레이션
	- 	[ELK](https://www.elastic.co/kr/elk-stack) 구성
-	AWS 최대한 활용하여 관리 부담 최소화
	- 	RabbitMQ를 [`AWS SQS`](https://aws.amazon.com/ko/sqs/)로 변경
	- 	Memcached를 [`AWS ElastiCache`](https://aws.amazon.com/ko/elasticache/)로 변경

100만
---
VPC + Public ELB + DB Replication + Jira/Wiki + Jenkins + Memcached + RabbitMQ
+ Auto Scaling + AWS RDS, DMS, SQS, ElastiCache 
+ ELK (Elastic Search + Log Stash + Kibana)
