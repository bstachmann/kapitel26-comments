---
layout: plain
---

Filter for URL with parameter `q`, e. g. `?q=/git-buch/`

<table id="commentsTable" class="table">
  <tr class="d-flex">
    {% for e in site.comments_columns %}
      <th class="col-sm-{{ e.first[1] }}">
        {{e.first[0]}}
      </th>
    {% endfor %}
  </tr>
  {% assign sortedComments = site.data.comments | sort %}
  {% for comment in sortedComments reversed %}
    <tr id="comment_{{ comment[1].url }}" class="d-none">
      {% for e in site.comments_columns %}
        <td class="col-sm-{{ e.first[1] }}">
          {{ comment[1] | map: (e.first[0]) }}
        </td>
      {% endfor %}
    </tr>
  {% endfor %}
</table>

{% include filter-script.html %}
