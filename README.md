# iris-sys-recs-2026

## Note
This branch continues from Task-4

## Resources

```
https://stackoverflow.com/questions/39663096/docker-compose-creating-multiple-instances-for-the-same-image

```

## Resources to explore

```

```

## Challenges
```
Servers kept shutting down, because of the pid error, even though there;s a pid script
Solution: write the pid to a tmp directory in the internal file system using the -P flag
this also makes the entrypoint script redundant
the -P flag was ignore by puma, so i had to create an anonymous volume for each instance, this solved the problem
Note: was not able to find any source for the problem, had to rely on gemini

the reverse proxy would boot first, try looking for app and then exit, when i added a dependency to the compose file under reverse proxy, i got a `dependency cycle detected: app -> reverse_proxy -> app` error, so i removed reverse_proxy as a dependency from the app
```

## commands

```
docker-compose down # bring down the old instances
docker compose up --build -d
docker-compose up -dx
```

## Understanding
many instances can be created using the replicate flag under deployment

## after
![woo](./Screenshots/Screenshot%202026-02-15%20at%2011.01.14 PM.png)