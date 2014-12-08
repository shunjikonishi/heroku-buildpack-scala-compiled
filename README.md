# heroku-buildpack-scala-compiled

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for Scala apps.

This buildpack uploads the compiled jars.  
So it is very faster than original [scala buildpack](https://github.com/heroku/heroku-buildpack-scala).  

If you're not using Play, then you'll also need to add the [sbt-native-packager plugin](https://github.com/sbt/sbt-native-packager).

## Usage

First time

```
sbt stage

mkdir heroku
cp -rp target/universal/stage heroku

cd heroku

git init
git add .
git commit -m "Initial commit"

heroku create -b https://github.com/shunjikonishi/heroku-buildpack-scala-compiled
git push heroku master
```

Second and subsequent

```
sbt stage

cp -rp target/universal/stage heroku

cd heroku
git commit -am "Modify"
git push heroku master
```

