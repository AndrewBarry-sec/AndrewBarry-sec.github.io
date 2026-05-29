---
layout: single
author_profile: false
header:
  image: /assets/Images/banner.jpg
  caption: "Welcome to my Cybersecurity Blog"
---

*A collection for my projects, Blogs, turorials and books*


## Explore these pages
<table>
  <tr>
    <td><strong><a href="/tutorials/">Tutorials</a></strong></td>
    <td>Hand crafted and polished walkthroughs to learn IT and Cyber Security techniques</td>
  </tr>
  <tr>
    <td><strong><a href="/learning-journey/">Learning Journey</a></strong></td>
    <td>My raw learning process of IT concepts</td>
  </tr>
  <tr>
    <td><strong><a href="/about/">About</a></strong></td>
    <td>Learn more about me</td>
  </tr>
  <tr>
    <td><strong><a href="/books/">Books</a></strong></td>
    <td>My published works and reading list</td>
  </tr>
</table>

## Recent Posts
{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}