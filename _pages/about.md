---
permalink: /
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<h3 style="margin-top: 0; color: #7a8288;">Brief Bio</h3>

I am a Computer Science Ph.D. student at the University of Rochester and am very fortunate to be advised by [Prof. Anson Kahng](https://ansonkahng.com/). This academic year, I am also visiting [Bailey Flanigan](https://sites.google.com/mit.edu/bailey-flanigan/home) at MIT. Previously, I was a computer science and economics double major at Dartmouth College ('24).

My research lies at the intersection of computer science and economics; my interests include applying computational social choice principles to automated decision-making and using voting theory to improve LLM alignment and rationality. Outside of research, I am interested in classical music, art, card games, coffee, and have also spent time in the social activism space (if you're interested in specifics, [email me](mailto:alina.chadwick@gmail.com)).

You can find my CV [here](/files/CV.pdf), and can also reach me at [achadwic@cs.rochester.edu](mailto:achadwic@cs.rochester.edu) or [alinavc@mit.edu](mailto:alinavc@mit.edu).

<h3 style="margin-top: 3em; color: #7a8288;">Research</h3>

{% include base_path %}

{% if site.author.googlescholar %}
You can also find my papers on [my Google Scholar profile]({{ site.author.googlescholar }}).
{% endif %}

<ul>
{% for post in site.publications reversed %}
  {% assign pub_year = post.date | date: "%Y" %}
  <li style="margin-bottom: 1em;">
    <strong>{{ post.title }}</strong> &mdash; <i>{{ post.venue }}</i>{% unless post.venue contains pub_year %}, {{ pub_year }}{% endunless %}<br />
    {% if post.authors %}
      {% for author in post.authors %}{% if author contains "Chadwick" %}<em>{{ author }}</em>{% else %}{{ author }}{% endif %}{% unless forloop.last %}, {% endunless %}{% endfor %}{% if post.alphabetical %} (&alpha;&ndash;&beta;){% endif %}<br />
    {% endif %}
    {% if post.paperurl %}<a href="{{ post.paperurl }}">[pdf]</a>{% endif %}
  </li>
{% endfor %}
</ul>
