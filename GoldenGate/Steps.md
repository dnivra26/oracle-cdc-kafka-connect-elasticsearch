su oracle
add credentialstore
alter credentialstore add user C##MYUSER@localhost:1521/ORCLCDB.localdomain

dblogin useridalias C##MYUSER@localhost:1521/ORCLCDB.localdomain
EDIT PARAMS empcust

EXTRACT empcust
USERIDALIAS C##MYUSER@localhost:1521/ORCLCDB.localdomain
LOGALLSUPCOLS
UPDATERECORDFORMAT COMPACT
DDL INCLUDE MAPPED
ENCRYPTTRAIL AES192
EXTTRAIL ./dirdat/in
TABLE C##MYUSER.*;


ADD EXTRACT empcust, TRANLOG, BEGIN NOW

ADD EXTTRAIL ./dirdat/in, EXTRACT empcust

START EXTRACT empcust
info extract empcust, detail
