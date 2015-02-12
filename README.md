# communibase documentation

Communibase Documentation and Tutorials --- See it in action at [http://docs.communibase.nl/](http://docs.communibase.nl/)

# building
```
docker build -t communibase/docs $(pwd)/.docker/
docker run --rm -ti -v $(pwd):/app -p 4000:4000 communibase/docs
```
After this just hit localhost:4000 and this should match the github version since we're using the [github-gem](https://github.com/github/pages-gem)