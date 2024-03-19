
- To build and run (this will start mysql containers in background)
  `docker-compose -f mysql-multi-docker-compose.yml up -d`

- To stop it
  `docker-compose -f mysql-multi-docker-compose.yml stop`

- To connect to docker using bash
  - `docker exec -it mysql_multi_8_0 bash`
  - `docker exec -it mysql_multi_5_7 bash`

- To connect using mysql cli
  - From container bash
    - `mysql -u MYUSER -pMYPASSWORD`
  - From local bash
    - `mysql -u MYUSER -pMYPASSWORD -P MYPORT -h 127.0.0.1`
    - `mysql -u root -pQwer4321 -P 13306 -h 127.0.0.1`
    - `mysql -u root -pAsdf0987 -P 23306 -h 127.0.0.1`
