---
permalink: /search/
title: Search
description: Live search all the content on our FAQ
---

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.css">

<header class="my-5">

  <h3>Search</h3>

  <form method="get" action="/search">
    <div class="form-group">
      <input class="form-control form-control-lg" type="text" name="q" id="search-input" placeholder="Search...">
    </div>
  </form>

  <p><span id="results-count">0</span> results were found.</p>

</header>

<div class="search-results-list">
  <ul id="search-results">
  </ul>
</div>

<script>
window.store = [
  {% for post in site.posts %}
    {
      "type"     : "post",
      "title"    : "{{ post.title | escape }}",
      "category" : "{{ post.categories | join: ', ' }}",
      "tags"     : "{{ post.tags | join: ', ' }}",
      "url"      : "{{ post.url | absolute_url }}",
      "date"     : "{{ post.date }}",
      "content"  : {{ post.content | strip_html | strip_newlines | default: "" | jsonify }}
    } {% unless forloop.last %},{% endunless %}
  {% endfor %}
  ,
  {% for page in site.pages %}
   {
     {% if page.title != nil %}
        "type"     : "page",
        "title"    : "{{ page.title | escape }}",
        "category" : "{{ page.category }}",
        "tags"     : "{{ page.tags | join: ', ' }}",
        "url"      : "{{ page.url | absolute_url }}",
        "date"     : "{{ page.date }}",
        "content"  : {{ page.content | strip_html | strip_newlines | default: "" | jsonify }}
     {% endif %}
   } {% unless forloop.last %},{% endunless %}
  {% endfor %}
];
</script>

<!-- <script src="https://code.jquery.com/jquery-3.3.1.min.js" integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script> -->
<!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/lunr.js/2.1.2/lunr.min.js"></script> -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/lunr.js/1.0.0/lunr.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/clipboard@2/dist/clipboard.min.js"></script>
<script src="/js/search.js"></script>
