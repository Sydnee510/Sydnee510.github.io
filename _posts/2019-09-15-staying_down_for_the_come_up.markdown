---
layout: post
title:      "Staying Down For The Come Up"
date:       2019-09-16 02:57:42 +0000
permalink:  staying_down_for_the_come_up
---


The beginning of this Object Orienated Programming section started out great. I  learned about defining classes and how to create an instance of a class. A **Dog**  class would be defined with the keyword **class**, followed by the class name and closed with an **end**. The body of this class would go between the **class** and **end** keywords. 
**Example 1**
```
class Dog
# the body of this class goes here
end
```
As I was going through this section I was feeling very confident about my ability to understand the content and complete the labs. However, things started to get a little more difficult once I had to start defining **initialize** methods. An **initialize** method is used when we want each instance of our **class** to be created with certain attributes and is called automatically whenever **new** is used.
**Example 2**
```
class Dog
  def initialize(breed)
    @breed = breed
  end
 
  def breed=(breed)
    @breed = breed
  end
 
  def breed
    @breed
  end
end
```
Now we can call **new** like this :
```
lassie = Dog.new("Collie")
 
lassie.breed #=> "Collie"
```
I now understand how and when to use an **initialize** method and am much more comfortable using them than I did before. The **Object Initialization Lab** asked me to create a **Dog** **class** that:
```
Dog
  #initialize
    sets the name of the dog in an instance variable @name
    sets the breed of the dog in an instance variable @breed
    defaults the breed argument to "Mutt" in an instance variable @breed
```
**Example 3**
```
class Dog 
  def initialize(name,breed = "Mutt")
    @name = name 
    @breed = breed 
 end
 end
```

