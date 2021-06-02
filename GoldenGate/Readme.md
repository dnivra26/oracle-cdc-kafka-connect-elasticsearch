alter credentialstore add user SYS@localhost:1521/ORCLCDB
alter credentialstore add user c##arvind@localhost:1521/ORCLCDB.localdomain

alter credentialstore add user c##arvind@localhost:1521/ORCLCDB.localdomain

alter credentialstore add user c##arvind@localhost:1521

alter credentialstore add user arvind@localhost:1521/ORCLCDB thangamani arvind alias oggadmin4 

ADD EXTRACT custext, TRANLOG, BEGIN NOW

ADD EXTTRAIL ./dirdat/in, EXTRACT custext

START EXTRACT custext

 info extract custext, detail

 edit params custext


 dblogin useridalias oggadmin2

 add schematrandata arvind ALLCOLS

 dblogin useridalias c##arvind@localhost:1521/ORCLPDB1.localdomain

EXTRACT custext
USERIDALIAS c##arvind@localhost:1521/ORCLCDB.localdomain
SOURCECATALOG CDB$ROOT
EXTTRAIL ./dirdat/in
TABLE c##arvind.*;


EXTRACT custext
USERIDALIAS c##arvind@localhost:1521/ORCLCDB.localdomain
LOGALLSUPCOLS
UPDATERECORDFORMAT COMPACT
DDL INCLUDE MAPPED SOURCECATALOG CDB$ROOT
ENCRYPTTRAIL AES192
EXTTRAIL /ggs/dirdat/lt
SOURCECATALOG CDB$ROOT
TABLE c##arvind.*;
docker run -it -p 1521:1521 store/oracle/database-enterprise:12.2.0.1

/scripts/go_sqlplus.sh /scripts/oracle_setup_docker


                                  /u01/app/ogg/BR/EMPCUST.
2021-05-27T18:21:13.807+0000  INFO    OGG-01851  Oracle GoldenGate Capture for Oracle, empcust.prm:  filecaching started: thread ID: 140650337076992.
2021-05-27T18:21:13.807+0000  INFO    OGG-01815  Oracle GoldenGate Capture for Oracle, empcust.prm:  Virtual Memory Facilities for: COM
                                  anon alloc: mmap(MAP_ANON)  anon free: munmap
                                  file alloc: mmap(MAP_SHARED)  file free: munmap
                                  target directories:
                                  /u01/app/ogg/dirtmp.

                                  
2021-05-27T18:21:13.901+0000  INFO    OGG-06604  Oracle GoldenGate Capture for Oracle, empcust.prm:  Database ORCLCDB.LOCALDOMAIN CPU info: CPU Count 6, CPU Core Count 6, CPU Socket Count 6.
2021-05-27T18:21:13.901+0000  ERROR   OGG-06220  Oracle GoldenGate Capture for Oracle, empcust.prm:  Classic Extract does not support multitenant container databases.
2021-05-27T18:21:13.901+0000  ERROR   OGG-01668  Oracle GoldenGate Capture for Oracle, empcust.prm:  PROCESS ABENDING.
^C
