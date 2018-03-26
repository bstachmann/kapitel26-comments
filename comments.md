---
layout: plain
---
<table id="commentsTable" class="table table-striped">
  {% for c2 in site.data.comments %}
    {% assign comment = c2[1] %}
    <tr id="comment_{{ comment.url }}" class="d-none">
      <td class="col-sm-9">
        {{comment.message }}
        <br/>
        ({{ comment.url }})
      </td>
      <td class="col-sm-3">
        {{ comment.name }}
        <br/>
        {{ comment.client_date }}
      </td>
    </tr>
  {% endfor %}
</table>

{% include filter-script.html %}
