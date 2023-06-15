# WebPageTest Test Results
Automatically triggered by [WebPageTest](https://www.webpagetest.org)'s GitHub Action.

<% let first = true; %>
<% tests.forEach((test) => { -%>
<% if (first) { -%>
<% first = false; -%>
| URL | Test |<% test.metrics.forEach((metric) => { %><%- metric.name %> | <% }); %>
| -- | -- | <% test.metrics.forEach((metric) => { %>--- | <% }); %>
<% } -%>
| [<%- (new URL(test.url)).pathname %>](<%- test.url %>) | [result](<%- test.testLink %>) | <% test.metrics.forEach((metric) => { %><%- metric.value %> | <% }); %>
<% }); %>
