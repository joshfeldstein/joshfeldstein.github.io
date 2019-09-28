# Josh Site
9 Sep 2019

### Download Jekyll image
    docker pull jekyll/jekyll

### Launch named instance
map cwd to /srv/jekyll, map localist port 4000 to container 4000, name the site, remove after process exit, interactive batch

	docker run -v "$PWD:/srv/jekyll" -p 0.0.0.0:4000:4000 --name jf-news --rm -i -t jekyll/jekyll bash

### Create Site
jekyll puts default content in `jf-news`

    cd ..
    jekyll new jf-news

### Copy Custom Content
Copy Custom Content

    cp about.markdown jf-news
    cp Articles/* jf-news/_posts

### Build
Puts static pages are in jf-news/_site, starts server on [http://localhost:4000/](http://localhost:4000)

    cd jf-news
    jekyll serve

### Cleanup

	jekyll clean

