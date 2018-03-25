---
layout: page
---
### Kommentare

<hr/>

<!-- <table id="commentsTable" class="table table-striped">
 class="d-flex"
 -->
<table id="commentsTable" >
  {% for c2 in site.data.comments %}
    {% assign comment = c2[1] %}
    <tr id="comment_{{ comment.url }}">
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

<script>

// Filter for pageURL with `?q=/git-buch/`

function filterComments() {

  var searchParams, filter, tr, i;

  searchParams = new URL(document.location).searchParams;
  filter = searchParams && searchParams.get("q") ? "comment_"+searchParams.get("q") : null;

  // alert(">"+filter);

  tr = document.getElementById("commentsTable").getElementsByTagName("tr");

  for (i = 0; i < tr.length; i++)
      if ((filter != null)  && tr[i] && (tr[i].id != filter))
      {
        // alert("HIDING "+tr[i].id);
        tr[i].style.display = "none";

      }
}

filterComments();
</script>
