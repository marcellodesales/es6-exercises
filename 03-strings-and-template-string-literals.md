# Strings and Template String Literals

1. Write a template tag function that escapes HTML.
   For example, if you call it like this, it should convert a string:

        escapeHTML `<script>alert('hello');</script>`

   to:

        "&lt;script&gt;alert(&#039;hello&#039;);&lt;/script&gt;"

   You can use this function to help out:

        function escapeHtml(text) {
          const map = {
            '&': '&amp;',
            '<': '&lt;',
            '>': '&gt;',
            '"': '&quot;',
            "'": '&#039;'
          };

          return text.replace(/[&<>"']/g, function(m) { return map[m]; });
        }


Solution

```javascript

function escapeHTML(literals, ...substitutions) {
  let result = '';
  for (let i = 0; i < substitutions.length; i++) {
    result += escapeHtml(literals[i]) + escapeHtml(substitutions[i]);
  }
  result += escapeHtml(literals[literals.length - 1]);
  return result;
}

function escapeHtml(text) {
   const map = {
     '&': '&amp;',
     '<': '&lt;',
     '>': '&gt;',
     '"': '&quot;',
     "'": '&#039;'
   };

   return text.replace(/[&<>"']/g, function(m) { return map[m]; });
}

console.log(escapeHTML `<script>alert('hello');</script>`);
```
