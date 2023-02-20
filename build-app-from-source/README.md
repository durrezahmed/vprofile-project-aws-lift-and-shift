## 7. Build Application from Source Code:

Now the application will be build locally and then the artifact will be uploaded to a S3 bucket. For this `jdk8` and `maven` should be installed in the system.

&nbsp;  
Clone Repository:

```bash
git clone https://github.com/durrezahmed/vprofile-project-devops.git
```

```bash
cd vprofile-project-devops/src/main/resources/
```

&nbsp;  
Change the Hostname according to the Route 53 Hosted Zone Records:

```bash
#JDBC Configutation for Database Connection
jdbc.driverClassName=com.mysql.jdbc.Driver
jdbc.url=jdbc:mysql://db01.vprofile.in:3306/accounts?useUnicode=true&characterEncoding=UTF-8&zeroDateTimeBehavior=convertToNull
jdbc.username=admin
jdbc.password=admin123

#Memcached Configuration For Active and StandBy Host
#For Active Host
memcached.active.host=mc01.vprofile.in
memcached.active.port=11211
#For StandBy Host
memcached.standBy.host=127.0.0.2
memcached.standBy.port=11211

#RabbitMq Configuration
rabbitmq.address=rmq01.vprofile.in
rabbitmq.port=5672
rabbitmq.username=test
rabbitmq.password=test

#Elasticesearch Configuration
elasticsearch.host =192.168.1.85
elasticsearch.port =9300
elasticsearch.cluster=vprofile
elasticsearch.node=vprofilenode
```

&nbsp;  
Now change the Directory to the root of the project:

```bash
cd vprofile-project-devops/
```

```bash
mvn install
```
