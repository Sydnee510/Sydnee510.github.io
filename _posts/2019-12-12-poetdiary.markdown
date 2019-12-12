---
layout: post
title:      "Poetdiary!"
date:       2019-12-12 18:45:09 +0000
permalink:  poetdiary
---


This is my first sinatra project here at Flatiron School. I can definitely say it was easier to do than my first CLI project. I say this because I was more comfortable doing this project from scratch with minimal help than I was on the first go round. I chose to do this project on creative writing. I have always liked spoken word and love to just sit at home and write poems about how I am feeling or about something that I was moved by. I created a webapp called Poetdiary where a user can signup/login/signout of their account. While logged in, they are able to create a poem that includes a title, description and some content. A user can not create a poem with NIL values so if attempted, they will be directed to an error page which tells them that a poem can not have NIL values. From there, they are able to go back to their profile and try again. Once they create a valid poem, it will be saved to their profile by it's title. Each poem that is saved to their profile, they will be able to click it to read, update and even delete their own poem. A user can view another user's poems but they can not update or delete it. Below I will show you some of the issues I had while creating this project. 
1.My first issue was that my user was not able to signup or login to my webapp. To fix this, I had to install the 'bcrypt' gem. AKA 'add it to my gemfile then run bundle install'
```
source 'http://rubygems.org'

git_source(:github) {|poetdiary| "https://github.com/Sydnee510/poetdiary" }

gem 'activerecord', '<=6.0', :require => 'active_record'
gem 'rack-test'
gem 'rake'
gem 'require_all'
gem 'rspec'
**gem 'bcrypt'**
gem 'shotgun'
gem 'sinatra'
gem 'sinatra-activerecord', :require => 'sinatra/activerecord'
gem 'sqlite3'
gem 'tux'
```
2.My second issue was that when my user creates a poem, it was creating in the database but not printing to the profile. I had to do two things... I had to use iteration in my profile.erb view where each poem created will be created into a link. Next I had to connect each poem created to the session's author and save it.
```
<% @author.poems.each do |poem| %>
    <ul>
    <li><a href="/poems/<%=poem.id %>"><%=poem.title %></a>
    <br>
    </li>
    </ul>
 <% end %>
``` 
```
post '/poems' do
        redirect_if_not_logged_in
        @poem = Poem.create(poem_params)
        @poem.author = Author.find(session[:author_id])
        if @poem.save
        erb :show
```
3.My third issue was that my user was able to create poems with nil values... To solve this I had to validate user inputs in my model
```
class Poem < ActiveRecord::Base 
    validates :title, :description, :content, presence: true
    belongs_to :author
end 
```
