Project: Microblog Microservices
Author: Brandon Le
Email: le.brandon350@gmail.com

NOTE:   *You may need to pip install flask_basicauth to run the apps.
        *COULD NOT GET FOREMAN AND PROCFILE TO WORK

Command to initate Database:
FLASK_APP=user flask init
OR
FLASK_APP=timeline flask init

Command to run User flask app:
FLASK_APP=user flask run

Command to run Timeline flask app:
FLASK_APP=timeline flask run

API to view all users
curl http://127.0.0.1:5000/users 

API to create a new user
curl -d '{"username":"Brandon5", "password":"password5", "email":"brandon5@gmail.com"}' -H "Content-Type: application/json" -X POST http://127.0.0.1:5000/create

API to authenticate user information
curl -d '{"username":"Brandon1", "password":"password1"}' -H "Content-Type: application/json" -X GET http://127.0.0.1:5000/auth

API to view all User Followers
curl http://127.0.0.1:5000/userfollows/Brandon2

API to follow a user
curl -d '{"follower":"Brandon4", "followed":"Brandon3"}' -H "Content-Type: application/json" -X POST http://127.0.0.1:5000/addfollower

API to unfollow a user
curl -d '{"username":"Brandon2", "followed":"Brandon1"}' -H "Content-Type: application/json" -X DELETE http://127.0.0.1:5000/removefollower

API to view user timeline
curl http://127.0.0.1:5000/timeline/Brandon1

API to view all user's following timeline
curl http://127.0.0.1:5000/timeline/all

API to post tweet
curl -d '{"username":"Brandon4",  "text":"Hello World"}' -H "Content-Type: application/json" -X POST http://127.0.0.1:5000/timeline/post
