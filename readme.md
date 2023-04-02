## How to setup environment

### setup db
```
docker run -d -p 50000:5432 -e POSTGRES_PASSWORD=qwe123QWE -e POSTGRES_DB=db postgres:14.1
```

### execute migration
```
python manage.py makemigrations cve

python manage.py migrate
```

### setup service
```
python manage.py runserver
```


Issue 1: 

Reproduction: CVE-2022-28346: field=count" from cve_user group by cve_user.id;DROP TABLE cve_user;--     

Fix: https://github.com/django/django/commit/93cae5cb2f9a4ef1514cf1a41f714fef08005200 

 

 

Issue 2: 

Reproduction: CVE-2022-28347 same as above 

 

Issue 3: 

CVE-2022-34265  https://github.com/aeyesec/CVE-2022-34265 

Fix: https://github.com/django/django/commit/54eb8a374d5d98594b264e8ec22337819b37443c  

 

Issue 4: 

CVE-2021-35042  

Reproduction: order_by=cve_user.id);drop table cve_user; -- 

Fix: https://github.com/django/django/commit/a34a5f724c5d5adb2109374ba3989ebb7b11f81f#diff-fd2300283d1546e36141373b0621f142ed871e3e8856e07efe5a22ecc38ad620  