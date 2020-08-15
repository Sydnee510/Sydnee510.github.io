---
layout: post
title:      "Can you create a sort button"
date:       2020-08-15 02:55:44 +0000
permalink:  can_you_create_a_sort_button
---


I wrote this blog because for some odd reason, creating buttons and adding event listeners on them was a very challenging aspect for me to learn. Creating the actual button in html was the easy part but adding the event listener and telling your app what to do once the event is fired off, took me a while to master. Here I will show you how I managed to create a sort button while practicing my JavaScript project. This project used a Rails API backend and a Modular JavaScript frontend. The main idea of this project is that users can create posts, delete posts, comment on posts and now like posts. When a new post is created, it appends to the bottom of the page and then users are able to perform functionality. The sort button, once clicked, should sort the posts by ID from the most recent post at top. Here is how I implemented the code:
```
index.html


<button class="sort-button"> Sort Posts </button>
```

```
PostsAdapter.js

orderPosts(){
    return fetch(this.postUrl)
		.then(res => res.json())
		.then(json => json.data)
}
```
```
posts.js

//add to event listeners
initBindingsAndEventListeners(){
let postOrder = document.querySelector(".sort-button")
postOrder.addEventListener("click", (event) => this.OrderPosts(event),false)
}

//new method orderPosts()

orderPosts() {
       this.posts = []
       this.adapter.orderPosts()
       .then(posts=> {
          let sortedPosts = posts.sort((a, b) => b.id - a.id)
           .forEach(post => this.posts.push(new Post(post.id, post.attributes.content, post.attributes.state, post.attributes.country, post.attributes.likes, post.attributes.comments )))
           console.log(this.posts)
           return this.render(sortedPosts)
       })
           alert("posts sorted!")
   }

```
