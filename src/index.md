---
layout: default
---

<div class="home-intro">
  <p>A wiki for understanding theoretical physics with emphasis on precise mathematical foundations — from Classical Mechanics through Quantum Field Theory, the Standard Model, and General Relativity. Written for readers with a mathematical background who want to build physical intuition.</p>
</div>

## Topics

<div class="question-list">
<% collections.topics.resources.each do |topic| %>
<a href="<%= topic.relative_url %>" class="question-card">
  <span class="question-card-title"><%= topic.data.title %></span>
  <% if topic.data.tags %>
  <span class="question-card-tags"><% topic.data.tags.each do |tag| %><span class="tag-small"><%= tag %></span><% end %></span>
  <% end %>
</a>
<% end %>
</div>

