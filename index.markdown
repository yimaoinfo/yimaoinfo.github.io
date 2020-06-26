---
layout: default
title: YiMao's BLOG
---

Hi there, I am YiMao(PinYin), an [Open Source][oss] enthusiast. This site is
dedicated to providing information about [me](resume.html) and [what I do](/work).

I am a screencastr at <https://yimao.info>.


<p><br /><b>My Blog:</b></p>
  <ul class="posts">
    {% for post in site.posts %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>

<p><b>Find me on:</b></p>

<ul>
<li><a href="https://github.com/yimaoinfo/">Github</a></li>
</ul>
<p><br /><b>Contact Information:</b></p>

<blockquote>
欢迎所有朋友沟通：YiMaoINFO@gmail.com
</blockquote>

[oss]:http://en.wikipedia.org/wiki/Open_source
