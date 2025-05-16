# Tutorial de como configurar o Apache Bench e executar um teste de carga no Home da sua aplicação. 

## Etapa 1:
- primeiro você tem que ter o apache instalado em sua máquina,caso não tenha, execute o seguinte comando:

``` 
sudo apt update
sudo apt install apache2-utils

``` 
## Etapa 2:

- Logo após instalar, faça o teste de carga em sua aplicação, defina nos parâmetros: número total de requisições, Número de requisições simultâneas e o Endereço da sua aplicação React.

- Ex:

``` 
ab -n 100 -c 10 http://IP_DO_SERVIDOR/

``` 

# Onde: 
- -n 100: Número total de requisições (ex: 100);

- -c 10: Número de requisições simultâneas (ex: 10);

- http://IP_DO_SERVIDOR/: Endereço da sua aplicação React;

# Exemplo real: 

``` 
ab -n 5000 -c 55 http://localhost/home

```

# Onde o resultado foi: 

``` 
Jonas@Tsi:~$ ab -n 5000 -c 55 http://localhost/home
This is ApacheBench, Version 2.3 <$Revision: 1903618 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 500 requests
Completed 1000 requests
Completed 1500 requests
Completed 2000 requests
Completed 2500 requests
Completed 3000 requests
Completed 3500 requests
Completed 4000 requests
Completed 4500 requests
Completed 5000 requests
Finished 5000 requests


Server Software:        nginx/1.24.0
Server Hostname:        localhost
Server Port:            80

Document Path:          /home
Document Length:        162 bytes

Concurrency Level:      55
Time taken for tests:   0.363 seconds
Complete requests:      5000
Failed requests:        0
Non-2xx responses:      5000
Total transferred:      1605000 bytes
HTML transferred:       810000 bytes
Requests per second:    13759.28 [#/sec] (mean)
Time per request:       3.997 [ms] (mean)
Time per request:       0.073 [ms] (mean, across all concurrent requests)
Transfer rate:          4313.21 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    2   1.3      1      10
Processing:     0    2   1.6      2      12
Waiting:        0    2   1.5      1      11
Total:          2    4   2.0      3      14

Percentage of the requests served within a certain time (ms)
  50%      3
  66%      4
  75%      4
  80%      4
  90%      7
  95%      9
  98%     11
  99%     12
 100%     14 (longest request)
Jonas@Tsi:~$ 

```
