# Twitter Profilify
A little script based on [Mispy][mispy_github]'s [bioversity][bioversity] and [kaomojify][kaomojify]. It helps your Twitter profile be a little more random, informative, and interesting.

## Emotional analyzer
Calculates your current emotional state relative to your Twitter history by downloading your tweets and running a Bayes classifier against them trained with a set of emotions. Can be used to either insert your current emotional state into your bio, or update your avatar.

## Dynamic Twitter bio
Generates a random bio based on your likes, current emotional state, and what you are listening to.

## Prerequisites
[Ruby 1.9.3+][ruby] and the [bundler gem][bundler].

## Usage
0. Clone the repository
0. Run `bundle install`
0. Rename `config.rb.sample` to `config.rb`
0. Rename the `sample-images` folder to `imgaes`
0. Edit `config.rb` with your details
0. Run `ruby profilify`

Edit `emotions.tsv` to adjust the emotions training dataset to better suit your needs.

You can run this hourly with cron or Heroku, or whatever else you prefer.

## Using the music feature
If you want to display what you were listening to when the script ran, you will need a Twitter account that tweets the stuff you're listening to.

I use [foo_twit_post][foo_twit_post] to tweet every song I listen to on a separate account. The post format setting is:

    #NowPlaying $iflonger(%title%,62,$cut(%title%,61)…,%title%)$if(%artist%, – $iflonger(%artist%,62,$cut(%artist%,61)…,%artist%))

This will produce a simple tweet that looks like this:

    #NowPlaying Some Song – Some Artist

[ruby]: https://www.ruby-lang.org
[bundler]: http://bundler.io
[bioversity]: https://github.com/mispy/bioversity
[kaomojify]: https://github.com/mispy/kaomojify
[mispy_github]: https://github.com/mispy
[foo_twit_post]: http://kitahei.cocolog-nifty.com/youyou/2007/04/foo_custominfo__6ab8.html
