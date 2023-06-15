# WebPageTest Test Results
Automatically triggered by [WebPageTest](https://www.webpagetest.org)'s GitHub Action.

<% let first = true; %>
<% tests.forEach((test) => { -%>
<% if (first) { -%>
<% first = false; -%>
| URL | <% test.metrics.forEach((metric) => { %><%- metric.name %> | <% }); %>
| -- | <% test.metrics.forEach((metric) => { %>--- | <% }); %>
<% } -%>
| <%- test.url %> | <% test.metrics.forEach((metric) => { %><%- metric.value %> | <% }); %>
<% }); %>
