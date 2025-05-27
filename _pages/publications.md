---
title: "VisAGI - Publications"
layout: gridlay
sitemap: false
permalink: /publications/
---


### Publications

<div class="well" style="padding: 20px; margin-bottom: 30px; box-shadow: none;">
<!-- <b>Top-tier conferences</b>: CVPR, ICCV, ECCV, NeurIPS, ICML, ICLR and AAAI are considered as high prestigious and top-tier AI conferences, which deem to have larger impacts than most SCI journals.  -->
<b>Top-tier AI conferences</b> such as <b>CVPR, ICCV, ECCV, NeurIPS, ICML, ICLR, and AAAI</b> are widely recognized as prestigious venues in the field of AI, often regarded as having greater impact than most SCI journals. According to Google scholar metrics, all these conferences are listed in the top 100 publications across all academic fields. Out of them, CVPR is the 2nd rank (Nature and Science are the 1st and 4th ranked) among all academic fields, i.e., highly competitive. 
<!-- \* indicates equal contribution. -->
</div>


{% assign year_last = 0 %}
{% for publi in site.data.publist %}


{% if year_last != publi.year %}
{% if year_last != 0 %}
</div>
</div>
{% endif %}
{% assign year_last = publi.year %}
<div class="row">
<div class="col-sm-1 clearfix"><h4>{{ publi.year }}</h4>
</div>
<div class="col-sm-11 clearfix">
{% assign div_opened = 1 %}
{% endif %}

<div class="well" style="padding-top: 5px; padding-bottom: 5px; padding-right: 10px; padding-left: 10px; margin-bottom: 3px; box-shadow: none;">
<p style="margin-bottom: 0px;">
{% if publi.link != null %}
<a href="{{ publi.link }}" target="_blank" style="color: #005EB8;">**{{ publi.title }}**</a> 
{% else %}
<a href="#" style="color: #005EB8;">**{{ publi.title }}**</a> 
{% endif %}
{% if publi.oral == 1 %}
<span style="line-height: 1; font-size: 12px; color: #FFFFFF; background-color: #004094; text-align: center; display: inline-block; border-radius: 5px 5px 5px 5px; padding: 3px 6px 3px 6px; font-weight: bold; margin-left: 5px;">oral</span>
{% endif %}
{% if publi.spotlight == 1 %}
<span style="line-height: 1; font-size: 12px; color: #FFFFFF; background-color: #004094; text-align: center; display: inline-block; border-radius: 5px 5px 5px 5px; padding: 3px 6px 3px 6px; font-weight: bold; margin-left: 5px;">spotlight</span>
{% endif %}
{% if publi.highlight == 1 %}
<span style="line-height: 1; font-size: 12px; color: #FFFFFF; background-color: #004094; text-align: center; display: inline-block; border-radius: 5px 5px 5px 5px; padding: 3px 6px 3px 6px; font-weight: bold; margin-left: 5px;">highlight</span>
{% endif %}
<br />
{{ publi.authors }}<br />
{% if publi.award != null %}
<span style="color: #730f27;">
  {{ publi.award | safe }}
  <style>
    .award-link {
      color: inherit !important;
      text-decoration: none;
    }
    .award-link:hover {
      text-decoration: underline;
    }
  </style>
</span><br />
{% endif %}
In <i>{{ publi.venue }}</i>
</p>
</div>
{% endfor %}

{% if div_opened == 1 %}
</div>
</div>
{% endif %}
