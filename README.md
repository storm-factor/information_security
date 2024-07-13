# «Уязвимости и атаки на информационные системы» - Pirogov Anton

###     Задание 1 

1. Список сетевых запущеных служб:

21/tcp   open  ftp
22/tcp   open  ssh
23/tcp   open  telnet
25/tcp   open  smtp
53/tcp   open  domain
80/tcp   open  http
111/tcp  open  rpcbind
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
512/tcp  open  exec
513/tcp  open  login
514/tcp  open  shell
1099/tcp open  rmiregistry
1524/tcp open  ingreslock
2049/tcp open  nfs
2121/tcp open  ccproxy-ftp
3306/tcp open  mysql
5432/tcp open  postgresql
5900/tcp open  vnc
6000/tcp open  X11
6667/tcp open  irc
8009/tcp open  ajp13
8180/tcp open  unknown

2. Ссылки на уязвимости

[Ссылка на уязвимость для ftp](https://www.exploit-db.com/exploits/17491)
[Ссылка на уязвимость для ssh](https://www.exploit-db.com/exploits/41680) 
[Ссылка на уязвимость для telnet](https://www.exploit-db.com/exploits/16851)


###     Задание 2

* Чем отличаются эти режимы сканирования
	* При SYN сканировании отправляются только SYN пакеты без завершения трехстороннего рукопожатия TCP. 
	* В FIN сканировании отправляются только FIN пакеты.
	* Xmas сканирование аналогично FIN сканированию, но вместо закрытия всех битов в заголовке IP, он устанавливает только один бит RST. 
	* UDP сканирование использует UDP пакеты для определения открытых UDP портов. 

* Как отвечает сервер 
	* SYN: Сервер не отправляет ответные пакеты при SYN сканировании, поскольку это часть процесса установки соединения TCP, который не был завершен. 
	* FIN: При FIN сканировании сервер также не отправлял полные ответы, так как это не является полноценным TCP соед.
	* Xmas: Как и в FIN сканировании, сервер не отправляет полные ответы, так как это не является стандартным способом завершения соединения. Он отправил пустой ACK пакет.
	* UDP: При UDP сканировании сервер не ожидает установления соединения и отправлял разные данные в ответ на UDP пакеты. 
