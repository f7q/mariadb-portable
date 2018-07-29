# mariadb-portable
インストールなしで MariaDB開発環境を準備する方法。

## 環境
- windows 10
- mariadb-10.3.8 [download](https://downloads.mariadb.org/interstitial/mariadb-10.3.8/win32-packages/mariadb-10.3.8-win32.zip)

`cd C:\mariadb-10.3.8-win32\bin`  
`bin> mysql_install_db.exe -d data_01 -p root -D`  
`mv C:\mariadb-10.3.8-win32\bin\data_01 C:\mariadb-10.3.8-win32\data_01`  
`vim C:\mariadb-10.3.8-win32\data_01\my.ini`  
```diff
[mysqld]
- datadir=C:/mariadb-10.3.8-win32/bin/data_01
+ datadir=C:/mariadb-10.3.8-win32/data_01
+ character_set_server = utf8
[client]
plugin-dir=C:/mariadb-10.3.8-win32/lib/plugin
```  
`bin> mysqld.exe --datadir=data_01 --console --skip-grant-tables`  

- 参考  
  - [だってプロジェクトマネージャーだもん - MariaDB](https://ameblo.jp/mandt132/entry-11741490070.html)
  - [MySQLサーバにログインできないとき](https://qiita.com/ferretdayo/items/98b615abf5ade60dac77)

