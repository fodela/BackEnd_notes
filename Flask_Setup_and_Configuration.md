# Connect to database from flask app

1. ### Set configuration

   database path or uri format:
   ![SQLAlchemy database uri format](https://video.udacity-data.com/topher/2019/August/5d4df44e_database-connection-uri-parts/database-connection-uri-parts.png)

   NB: A database adapter can be added to the dialect.
   `postgres+psycopg2://`
   The default is psycopg2

```

app.config["SQLALCHEMY_DATABASE_URI"] = database_path
```

### Create database (database.db or model.db)

1. Start flask shell in the terminal by running `flask shell`
2. Import database from path of models or database `from src.database.models import db`
3. Create all the tables defined in your models.py or database.py.
4. run `db` to see path of newly created database.
