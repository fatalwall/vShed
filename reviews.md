---
layout: default
---

<link rel="stylesheet" type="text/css" href="assets/css/reviews.css">

{%- for collection in site.collections | where: "label", "reviews" -%}
  {%- assign sorted = collection.docs | sort: 'title' -%}
  {%- for review in sorted -%} 
  
<article class='review-artical' id='{{review.title}}'>
  <div class='review-content'>
    <div class='review-body'>
      <div class="review-header">
        <div class="review-title">
          <h1>
            <a href="{{site.baseurl}}{{review.url}}">{{review.title}}</a>
          </h1>
        </div>
      </div>		
      <div class='review-excerpt'>
        <p class="excerpt">{{review.excerpt | strip_html}}</p>
      </div>
      <div class="review-action">
        <a class="read-more" href="{{site.baseurl}}{{review.url}}">Read More</a>
      </div>
    </div>
  </div>
</article>

  {%- endfor -%}
{%- endfor -%}