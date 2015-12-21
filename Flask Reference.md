#Flask материалууд

Readme:
http://flask.pocoo.org/docs/0.10/
http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world

##Жагсаалт

* pip
* virtualenv
* virtualenvwrapper

### Pip

>pip install -r /path/to/requirements/*.txt

### Virtual Environment 
Python хэлний олон ялгаатай орчин үүсгэх<br>
>Dependencies: pip ,virtualenv <br>
><https://github.com/byam/it-articles/blob/master/virtualenvwrapper-install.md>

Virtual Environment ашиглаж байгаа үед ингэж бичихгүй.
``` 
 #!flask/bin/python
```

### Errors

route.BuildError relating to blueprint
> 
subapp = Blueprint('profile', __name__)
>
@subapp.route('/<username>')
def fetch_profile(username):
    pass
If you declared blueprint like above, you should call url_for() like below:
> 
url_for('profile.fetch_profile', username=arg)


### Migration

SQLAlchemy-migrate ашиглана.

> 
SQLALCHEMY_DATABASE_URI , SQLALCHEMY_MIGRATE_REPO тааруулах

migrate.exceptions.DatabaseAlreadyControlledError
Ийм алдаа гарч ирвэл app.db файлыг гараар устгана. Эсвэл exception зааж өгнө.

> Alembic
https://alembic.readthedocs.org/en/latest/offline.html#getting-the-start-version


//@ sourceMappingURL=jquery-1.10.2.min.map


###Auto complete
http://stackoverflow.com/questions/22449884/flask-jquery-autocomplete
http://stackoverflow.com/questions/17365821/using-jquery-autocomplete-with-flask
http://stackoverflow.com/questions/15310644/flask-ajax-autocomplete?z_ad8eb2b0f40c11e0be500800200c9a66=1429973160
