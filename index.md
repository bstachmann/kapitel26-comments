---
layout: page
---
### Kommentare

<hr/>

<table id="commentsTable">
  {% for c2 in site.data.comments %}
    {% assign comment = c2[1] %}
    <tr id="comment_{{ comment.url }}" >
      <td>
        {{comment.message }}
        <br/>
        ({{ comment.url }})
      </td>
      <td>
        {{ comment.name }}
        <br/>
        {{ comment.date }}
      </td>
    </tr>
  {% endfor %}
</table>

<script>

// Filter for pageURL with `?q=/git-buch/`

function filterComments() {

  var searchParams, filter, tr, td, i;

  searchParams = new URL(document.location).searchParams;
  filter = searchParams && searchParams.get("q") ? "comment_"+searchParams.get("q") : null;

  tr = document.getElementById("commentsTable").getElementsByTagName("tr");

  for (i = 0; i < tr.length; i++)
      tr[i].style.display = (filter == null) || (tr[i].id == filter) ?  "" : "none";
}

filterComments();
</script>
