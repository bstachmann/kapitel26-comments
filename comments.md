---
layout: plain
---
<table id="commentsTable" class="table">
  {% assign sortedComments = site.data.comments | sort %}
  {% for comment in sortedComments reversed %}
    <tr id="comment_{{ comment[1].url }}" class="d-none">
      <td class="col-sm-9">
        {{comment[1].message }}
      </td>
      <td class="col-sm-3">
          {{ comment[1].name }}
          <br/>
          <small>
            {{ comment[1].date | date: site.comments_date_format }}
          </small>
      </td>
    </tr>
  {% endfor %}
</table>

{% include filter-script.html %}
