---
layout: default
title: "آنتو | فرهنگ واژگان"
permalink: glossary/
---
<h2>فرهنگِ واژگان آنتو</h2>
<br />

{% for concept in site.data.glossary %}
  <table class='post-list'>
  <tr>
	<td style="width:1%; margin: 5px;"><strong>{{ concept.label_fa }}</strong> ({{ concept.label}})</td>
  </tr>
  <tr>
	<td style="border-right:solid 1px white;padding-right:5px;">
	  <small class="small">{{ concept.description }}</small>
	  <br />
	  <small class="small">
	  	<a href="{{ concept.more_info }}" class="small" target="_blank" rel="bookmark">اطلاعات بیشتر...</a>
	  </small>
	</td>
  </tr>
  </table>
  <hr />
{% endfor %}

<small class="muted">
برای سازماندهی‌ این فرهنگِ واژگان از آنتولوژی SKOS استفاده شده است. برای دسترسی به آنتولوژیِ این فرهنگ لغات با پشتیبانی آنتو تماس بگیرید.
</small>