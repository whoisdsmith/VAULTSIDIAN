---
Date: <% tp.date.now() %>
Author: Dustin Smith <whoisdsmith@gmail.com>
Alias: []
---

Tags:: [[+Daily Notes]]

<< [[<% tp.date.now("YYYY-MM-DD-dddd", -1, tp.file.title, "YYYY-MM-DD-dddd") %>]] | [[<% tp.date.now("YYYY-MM-DD-dddd", 1, tp.file.title, "YYYY-MM-DD-dddd") %>]]>>

# <% moment(tp.file.title,'YYYY-MM-DD').format("dddd, MMMM DD, YYYY") %>

---

## Day Planner

---

## Agendas

---

## Notes

---

### Notes Created Today:

```dataview
List FROM "" WHERE file.cday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.ctime asc
```

---

### Notes Modified Today:

```dataview
List FROM "" WHERE file.mday = date("<%tp.date.now("YYYY-MM-DD")%>") SORT file.mtime asc
```

***

## Appendix: Links and References

- [[Templates/Template Hub/Templates/Template-Vault/2-AREAS/Daily-Notes/_README|Daily Notes](Template%20Hub/Templates/Template-Vault/2-AREAS/Daily-Notes/_README.md)aily Notes]]

***

Dustin Smith <whoisdsmith@gmail.com> | <% tp.date.now("YYYY") %>
