# iris-sys-recs-2026

## Note
This branch continues from Task-2

## Resources

```
https://admatbandara.medium.com/nginx-reverse-proxy-for-a-rails-app-with-docker-71859ec6a70c
https://www.geeksforgeeks.org/devops/configure-nginx-in-docker-compose/ # same as the last one tbh
https://www.cyberciti.biz/faq/nginx-ipv6-configuration/ # for that ipv6 thingy
```

## Resources to explore

```
https://www.cyberciti.biz/faq/nginx-ipv6-configuration/
https://guides.rubyonrails.org/configuring.html#actiondispatch-hostauthorization
```

## Challenges
```
https://guides.rubyonrails.org/configuring.html#actiondispatch-hostauthorization
```


## Commands

```
config.hosts << "app:3000" # add app:3000 to ruby's config/environments file
i've manually added the statement to all the 3 files, ideally an environment variable containing the domains must be passed to the rails application.
```

## Understanding

all the traffics hits nginx and then hits the rails server, this hides the ip address of the real rails server, which can be quite useful sometimes

# after

![1](Screenshot%202026-02-15%20at%209.57.57 PM.png)
![2](Screenshot%202026-02-15%20at%209.58.05 PM.png)
![3](Screenshot%202026-02-15%20at%2010.05.59 PM.png)