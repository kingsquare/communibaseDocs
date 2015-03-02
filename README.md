# Communibase documentation

Communibase documentation and Tutorials --- See it in action at [http://docs.communibase.nl/](http://docs.communibase.nl/)

## Local development

We use [docker](https://docker.io) for local development to mimic the github environment:

``` docker run --rm -ti -v $(pwd):/app -p 4000:4000 gekkie/gh-pages ```

After this just hit [localhost:4000](http://127.0.0.1.xip.io:4000) and this should match the github version 
since we're using the [github-gem](https://github.com/github/pages-gem)