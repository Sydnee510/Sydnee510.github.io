---
layout: post
title:      "QueenWorkx"
date:       2020-02-24 06:30:57 +0000
permalink:  queenworkx
---


Ruby on Rails means project number 3 for me. Whewwwww!!! It has been a journey. I can say, going and coming out of the Sinatra module a little while back has definitely made my transition into rails a lot easier. I felt sinatra was a breeze for me even though I had to build every function, form, view, model, and controller on my own. It's something about creating everything by hand and knowing exactly what each function and tag does inside of your project. Rails on the otherhand has many shortcuts and generators that do a lot for you and while it was supposed to make our life easier, it made my life a little harder.

I started off this module keeping up with the pace and not getting lost in all the cool rails tricks. But hey things can't be smooth sail forever so I knew I had to figure out a new strategy to grasp this material. Instead of breezing through this module like I did in the sinatra module, I spent a lot more time trying to understand what each lab was actually trying to teach me. I felt this strategy was working and although I fell behind on curriculum, I feel I was still grasping the material. 
...
...

Time is still ticking... 
...
...

I'm here taking my time, trying to figure things out and BOOM!!! Once I looked up, it was PROJECT TIME!!!
...
Time to plan, build, & execute!!
**RAILS PROJECT**
Title: Queenworkx
Purpose: Build an admin portal where users can keep track and modify products in a database. 
```
Basic Models w/o validations:
User
has_many :products
has_many :categories through: :products
Product
belongs_to :user
belongs_to :category
Category
has_many :products
has_many :users, through: :products
```
Main Function: Each product will be assigned to a category. Each category has many products.  

Authenticate User:
I set up my user authentication with the devise gem where users can signup, and login to an account.  
I also set up the feature where a user can login through an outside source from the omniauth gem. 
I chose github as my outside source.





