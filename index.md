---
layout: plain
---

Filter for URL with parameter `q`, e. g. `?q=/git-buch/`

<table id="commentsTable" class="table">
  <tr class="d-flex">
    <th class="col-sm-3">
      URL
    </th>
    <th class="col-sm-2">
      Name
    </th>
    <th class="col-sm-2">
      Date
    </th>
    <th class="col-sm-5">
      Message
    </th>
  </tr>
  {% assign sortedComments = site.data.comments | sort %}
  {% for comment in sortedComments reversed %}
    <tr id="comment_{{ comment.url }}" class="d-none">
      <td class="col-sm-3">
        {{ comment[1].url }}
      </td>
      <td class="col-sm-2">
        {{ comment[1].name }}
      </td>
      <td class="col-sm-2">
        {{ comment[1].client_date }}
      </td>
      <td class="col-sm-2">
        {{ comment[1].date }}
      </td>
      <td class="col-sm-3">
        {{comment[1].message }}
      </td>
    </tr>
  {% endfor %}
</table>

{% include filter-script.html %}
