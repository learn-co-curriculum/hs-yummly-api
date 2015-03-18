---
tags: kids, ruby, yummly, recipes, apis
languages: ruby
level: 1
type: Intro, Documentation
---

### Yummly

[Yummly](https://www.yummly.com/) is a great website for finding recipes.

We will be using the [Yummly Ruby gem](https://github.com/twmills/yummly) to connect to Yummly's API to search for recipes.

First, you need to install the Yummly gem on your computer. In terminal, from any directory, enter `gem install yummly`

Next, you will need to follow the instructions below to set up your app:

### Setup

Paste this into your `Gemfile`:
``` ruby
gem 'yummly'
```

Paste this into your `.env` file.

``` ruby
# these are the Flatiron School's Yummly credentials
yummly_id=4e9f2aa0
yummly_key=e54e9cfa05d58b64bab7da2301f05c0b
```

### Searching for recipes

The rest of the code below will go into one of the routes in your application controller. If you are taking in a search criteria via a form, then this code should go into that `post` route.

``` ruby
# this creates a new connection to the Yummly API
Yummly.configure do |config|
  config.app_id = ENV['yummly_id']
  config.app_key = ENV['yummly_key']
  config.use_ssl = true # Default is false
end

# this searches Yummly for a recipe and returns an array of recipe objects
results = Yummly.search('type of recipe you want') #=> an array of recipe results
```

Check out `yummly_test.rb` to see how you can pull out the name, ingredients and link to the first recipe in the array. To test the Flatiron Yummly account and see the results in that file, fork and clone this lab then run `ruby yummly_test.rb` in your terminal.

