<%*
fileName = tp.file.title;
if (fileName.endsWith(".md")) fileName = fileName.slice(0, -3);

if(fileName === "index") { // if name is index, consider parent folder name
  fileName = tp.file.folder();
}

// I used underscores for note.md names, but they make bad URLs,
// so I switched to using hypens. Example: '1_React_Lists' to '1-React-Lists'
// adding a separator token here, fallback value is underscore
separator = [...fileName].find(letter => letter === '_' || letter === '-');
completeTitle = fileName.replaceAll(separator, " ");
potentialNumber = completeTitle.split(" ").at(0);
hasNumber = !Number.isNaN(parseFloat(potentialNumber));
titleWithoutNumber = completeTitle.slice(potentialNumber.length + 1);

newTitle = hasNumber
  ? `${potentialNumber}. ${titleWithoutNumber}`
  : completeTitle;
%># <% newTitle %>
<% tp.date.now("[Created] ddd ll [at] LT") %>

<% tp.file.cursor() %>
