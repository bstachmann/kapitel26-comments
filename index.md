---
layout: plain
---

Filter for URL with parameter `q`, e. g. `?q=/git-buch/`

<table id="commentsTable" class="table table-striped">
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
  {% for c2 in site.data.comments | sort: 'date' | reverse %}
    {% assign comment = c2[1] %}
    <tr id="comment_{{ comment.url }}" class="d-none">
      <td class="col-sm-3">
        ({{ comment.url }})
      </td>
      <td class="col-sm-2">
        {{ comment.name }}
      </td>
      <td class="col-sm-2">
        {{ comment.client_date }}
      </td>
      <td class="col-sm-5">
        {{comment.message }}
      </td>
    </tr>
  {% endfor %}
</table>

{% include filter-script.html %}
