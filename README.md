# iris-sys-recs-2026

## Resources Used
```
https://hub.docker.com/_/ruby
https://www.digitalocean.com/community/tutorials/containerizing-a-ruby-on-rails-application-for-development-with-docker-compose
```

## Challenges Faced

```
Could not find compatible versions

Because rails >= 7.0.10, < 7.1.0.beta1 depends on activesupport = 7.0.10
  and Gemfile depends on rails ~> 7.0.10,
  activesupport = 7.0.10 is required.
So, because Gemfile depends on activesupport >= 8.1.2, < 9.A,
  version solving has failed.
The command '/bin/sh -c bundle install' returned a non-zero code: 6
```
Had to make changes to the gemfile for it to compile/bundle, I removed the dependency pinning for activerecord and activesupport




## Things I learnt
```
Dependency Caching, i.e the order of commands in the dockerfile matters

RUN bundle config --global frozen 1

```

## Commands

```
colima start
docker build -t iris .
docker run iris -d --name instance_1 -p 80:3000
```

## Images

![Screenshot](./Screenshot%202026-02-15%20at%2014-59-28%20Action%20Controller%20Exception%20caught.png)