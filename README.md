# Steps to Deploy Node.js Application to Heroku using MongoDB and MLab

### Heroku Setup

1. First create a Heroku Account

2. Read Heroku's documentation thoroughly. Check it out [here](https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up)

2. Setup Heroku CLI as instructed in the above link

3. Create and deploy the app as instructed [here](https://devcenter.heroku.com/articles/getting-started-with-nodejs#deploy-the-app)

4. Push your project folder to Heroku server

### Before checking out your app, follow the instructions below to set up [mlab](https://mlab.com/)

1. Setup an mlab account

2. Go to ```MongoDB Deployments``` and ```Create a new deployment```

3. Choose a required plan and select that database

4. Create a ```collection``` and give it a name of your choice, for that collection, create a user and give it ```username``` and ```password```

5. In ```server/index/app```  configure port:
```javascript
port: const PORT = process.env.PORT || 5000;
```

6. In ```db.js```, ```MONGODB_URI``` set up: 
```javascript
const CONNECTION_URI = process.env.MONGODB_URI || 'mongodb://localhost:<your_id>/<name_of_your_db_folder>' 
```
(```MONGODB_URI``` is available only in production environment, to set it up, follow the next step)

7. Then in Heroku CLI, setup MongoDB URI by running the command:
(```ds ID``` and ```port``` might change, please use the URI provided to you)

```sh
heroku config:set MONGODB_URI= 'mongodb://<your_username>:<your_password>@ds223653.mlab.com:23653/rsvp_data'
```

8. If ```MONGODB_URI``` is not supported, then use ```MONGOLAB_URI```


