# Camunda BPM Team Blog

Generated by [Hugo][hugo] and styled with some fancy [node.js][nodejs] tools like [Grunt][grunt], [less][less].

## Redaction

```sh
hugo -w server
```

## Themeing

```sh
grunt
```

and in a other terminal

```sh
hugo -w server
```

# Deploying to GitHub pages

Stop the `grunt` or `hugo` processes.

First time (if you don't have the `gh-pages-blog` aside of this cloned repository):

```sh
cd ../
git clone git@github.com:camunda/blog.camunda.org.git gh-pages-blog
cd gh-pages-blog/
git checkout gh-pages
```

And then (considering this repository was cloned in `blog.camunda.org`):

```sh
cd ../gh-pages-blog/
git rm -rf --cached .
git commit -m "cleanup"
git clean -df

cd ../blog.camunda.org/
rm -rf public
grunt build optimize
hugo --baseUrl=http://camunda.github.io/blog.camunda.org/
cp -r public/* ../gh-pages-blog/

cd ../gh-pages-blog/
git add .
git commit -m "update gh-pages"
git push origin gh-pages

cd ../blog.camunda.org/
```


## License

The project is licensed under [Apache 2.0](./LICENSE)

The content (content of the `content` directory) is licensed under ???


[hugo]: http://gohugo.io
[nodejs]: http://nodejs.org
[grunt]: http://gruntjs.org
[less]: http://lesscss.org