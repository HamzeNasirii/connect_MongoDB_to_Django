# connect_MongoDB_to_Django
The purpose of creating and publishing this project is to help you connect the MongoDB to the Django. I hope it will be useful for you.

1. Download and install mongoDBcompass from this link: https://www.mongodb.com/try/download/compass

2. going to https://www.mongodb.com/atlas/database
    2.1 singup
    2.2 create a database
    2.3 go to connect's tab and then get the link for "connect using mongoDB compass"
        2.3.1 paste the link in the mongoDbcompass application and enter your username and password then connect with your atlas cluster
            example: mongodb+srv://<username>:<password>@<atlas cluster>.mongodb.net/test
    2.4 go to connect's tab and then get the link for "connect your application"
            example: mongodb+srv://<username>:<password>@<atlas cluster>.mongodb.net/?retryWrites=true&w=majority
    
3.open the project in our IDE
4.pip install -r requirements.txt
    This file contains:
        asgiref==3.5.0
        Django==4.0.3
        djongo==1.3.6
        dnspython==2.2.1
        pykerberos==1.2.4
        pymongo==3.12.1
        python-snappy==0.6.1
        pytz==2022.1
        sqlparse==0.2.4
        
 5.django-admin startproject config .
 
 6. go to config/setting.py and change the DATABASE:
    DATABASES = {
        'default': {
            'ENGINE': 'djongo',
            'NAME': 'your-db-name',
            'ENFORCE_SCHEMA': False,
            'CLIENT': {
                'host': 'mongodb+srv://<username>:<password>@<atlas cluster>/<databasename>?retryWrites=true&w=majority'
             }  
         }
     }
7. python manage.py migrate
