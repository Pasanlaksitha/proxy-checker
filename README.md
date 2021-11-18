# Proxy Checker

Simple **HTTP/HTTPS** proxy checker written with Python and push all good proxies to MYSQL DB

# Newly Added

### you can save all good proxies to SQL DB with the MySqlDB library. import .sql file to PHPMyAdmin and start the program

# Usage

## Get started

First, you need to get rid of problems with executing permissions, so to do that, open the terminal and say:

```bash
chmod +x prox.py
```
### Setup MySQL file to phpmyadmin and setup password and user to MySqlDB

```
--
-- Table structure for table `proxy`
--

CREATE TABLE `proxy` (
  `id` int(4) NOT NULL,
  `proxy` text NOT NULL,
  `checked_time_input` timestamp NOT NULL DEFAULT current_timestamp() ON UPDATE current_timestamp()
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

```

### setup your localhost, password and user in mysql/phpmyadmin

```
mydb = MySQLdb.connect(host='localhost',
    user='',
    passwd='',
    db='proxy')
cursor = mydb.cursor()
```

### Check proxies from a file

```bash
 ./prox.py -f <FILENAME>
```

### Check only one proxy

```bash
./prox.py -p <IP:PORT>
```

