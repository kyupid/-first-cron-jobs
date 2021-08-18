리눅스의 crontab 기능을 이용하여 PHP 파일을 실행하기 위해 알아야 할 사항

1. PHP 코드에 DB 연결하는 파일 정보는 절대경로로 적어야 한다.
```php
    include "/home/httpd/db.info.php";
    include "/home/httpd/dbClass.php";
```
 

2. PHP 코드 상단에 한줄 적어줄 내용
```bash
$ whereis php
```
```php
    !#/usr/local/php/bin/php -q // php 파일의 절대 경로

    <?php

        include "/home/httpd/db.info.php";
        include "/home/httpd/dbClass.php";
 
        PHP 소스코드

     ?>
```


3. cron 작ㅇ버에서 PHP 스크립트를 실행하는 일반적인 방법은 curl 또는 wget과 같은 며영줄 프로그램을 사용하는 것이다

```
curl http://example.com/script.php
```

4. 그러나 php 명령줄 인터프리터를 사용햇 ㅓ직접 스크립트를 사용할수있다. 일반적으로 더 빠르다

```
php -q /home/username/public_html/script.php
```

-q는 HTTP 헤더를 방지 자동모드(?)를 가능하게한다? (https://projin.tistory.com/263)

