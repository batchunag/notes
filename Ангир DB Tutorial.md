Database өөрчлөх
------

Одоо ашиглаж байгаа -> http://tecadmin.net/python-script-for-mysql-database-backup/

<br>
Alembic (https://alembic.readthedocs.org/en/latest/)

Суулгах

```
$ pip install alembic
```

Ашиглах
```
$ cd yourproject
$ alembic init alembic
```

Editing the .ini File

Edit: file_template
Edit : sqlalchemy.url

Create Migration Script
$ alembic revision -m "create account table"

--> Түр болив. Code First migration юм шиг байна. Эхнээсээ SQLalchemy ашиглаад model.ээ үүсгээд явбал хэрэглэж болох юм.
Гэхдээ бас data -> sql хадгалж болох эсэх нь эргэлзээтэй.

> Useful links
http://stackoverflow.com/questions/22698478/what-is-the-difference-between-the-declarative-base-and-db-model
<br>

Migrate

> 
Create model using sqlacodegen.
* Add missing 's' manually

Changes

> ApplyStatus :
	* User_id, Job_Offer_id : unique=True --> removed
	* job_offeringing -> job_offering

Comments
> 
mysql://ants:angirmaa@localhost/angir?charset=utf8
>
env.py
import os,sys
sys.path.append(os.getcwd())
>
for t in db.metadata.sorted_tables:
    print t.name

Manage.py
> 
import datetime 
datetime.date(2015, 7, 1)
*
schools = [u'東京大学', u'東京工業大学', u'電気通信大学', u'Hitotsubashi University']