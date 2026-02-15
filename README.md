# iris-sys-recs-2026

## Note
This branch continues from Task-1

## Resources

```
https://docs.docker.com/compose/intro/compose-application-model/
https://docs.docker.com/compose/gettingstarted
```

## Resources to explore

```
https://github.com/docker/awesome-compose
https://www.geeksforgeeks.org/devops/docker-compose/
https://www.glukhov.org/post/2025/07/docker-compose-cheatsheet/
https://medium.com/@rosgluk/docker-compose-cheatsheet-most-useful-commands-with-examples-4fbc3d2b5deb
```

## Challenges

The sql instances and the rails instances refused to connect ;(, so i had to edit the database.yml, specifically remove the socket line, i wasn't able to find much oh that, but from what i was able to find, it was a socketfile and the rails deployment was looking for it on it';s file system and was not able to find it and kept throwing errors.
we had to replace the socket line with a host line
the then application complained of not having databases, so we had to create databases

## Commands

```
docker-compose up --build
docker-compose exec app bin/rails db:prepare
```

## Understanding

Previosuly when i'd used docker, i'd used network to let containers 'talk' to each other, even back then it was kinda confusing, but now it's really abstract with docker compose, it just magically happens.

## Part a
To make the sqldb internal only , we just need to remove the ports parameter in the compose file. we can document this port as internal only using expose parameter, this however does not publish the port to the host.

before 
![Before](Screenshot%202026-02-15%20at%204.45.29 PM.png)

after
![After](Screenshot%202026-02-15%20at%205.03.51 PM.png)

## Part b
We'd previosuly exposed and published the rails application to port 80 to save writing the 8000/8080,etc.
To change the port, we go to the compose and change the port parameter

![8080](Screenshot%202026-02-15%20at%209.21.57 PM.png)

