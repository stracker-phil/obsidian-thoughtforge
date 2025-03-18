<%*
// Prepare template variables.
const theName = tp.file.title;
const currentDate = moment(theName, 'YYYY-MM-DD');
const today = currentDate.format("YYYY-MM-DD");
const todayLong = currentDate.format("dddd, DD MMM YYYY");
_%>

<%*
// Front-matter properties.
tR += "---\n"
tR += "focus: \n"
// Todo: Add more frontmatter properties if you need them.
tR += "---\n\n"

// Note contents start here.
_%>

# <% todayLong %>
## 🧭 Plan for Today

- [ ] ☕️ _Morning Routine_ (planning & meetings)
- [ ] 🛋️️ _Evening Routine_ (time recording, recap & consolidate)

## 📓 Notes
