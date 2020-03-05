# Basic CRUD: Flask & PostgreSQL

1. Activate __PostgreSQL__ server:
    
    ```bash
    $ cd /Library/PostgreSQL/12/bin
    $ psql -U postgres
      Password for user postgres: <insert password here>
    ```

#

2. Create a database on PostgreSQL, my database name is __"my_flask"__:
    
    ```bash
    postgres=#  CREATE DATABASE my_flask;
    postgres=#  \l 
    postgres=#  \c my_flask
    ``` 

#

3. Create a __"users"__ table on __"my_flask"__ database:
    
    ```bash
    lin_flask=#  CREATE TABLE users(
                 id SERIAL PRIMARY KEY,
                 name VARCHAR(255),
                 age VARCAR(255)
                 );
    lin_flask=#  \d
    ``` 

#

4. Clone this repo. Insert your database URI to __database.yaml__ file, then install all the packages needed. In this project I'm using __flask__, __flask_cors__, __flask_mysqldb__, __Flask-SQLAlchemy__ & __psycopg2__:
    ```bash
    $ git clone xxxxx
    $ cd CRUD_Flask_PostgreSQL
    $ pip install flask flask_cors Flask-SQLAlchemy psycopg2
    ```

#

5. Run the server file. Make sure your PostgreSQL server is still running. Your application server will run locally at __*http://localhost:5000/*__ :
    ```bash
    $ python app.py
    ```

#

6. Give a request to the server. You can use __Postman__ app:
    
    __See the opening screen (*home.html*)__
    ```bash
    GET /
    ```

    __Post a data to database:__ 
    ```bash
    POST /data
    body request: {"country_lv": "us",
            "state_lv": "",
            "city_lv": "",
            "subdiv_lv": "",
            "postcode_lv": "",
            "street_lv": ""}
    ```
    __Get all data & specific data by id:__
    ```bash
    GET /data
    GET /data/{:id} (i.e: /1)
    ```
    __Update a data by id__:
    ```bash
    PUT /data/{:id}
    body request: {"country_lv": "us",
            "state_lv": "",
            "city_lv": "",
            "subdiv_lv": "",
            "postcode_lv": "",
            "street_lv": ""}
    ```
    __Delete a data by id:__
    ```bash
    DELETE /data/{:id}
    ```

#
