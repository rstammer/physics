---
layout: default
---

<p class="home-intro">A wiki for understanding theoretical physics with emphasis on precise mathematical foundations — from Classical Mechanics through Quantum Field Theory, the Standard Model, and General Relativity. Written for readers with a mathematical background who want to build physical intuition.</p>

<div class="topic-list">
<% collections.topics.resources.each do |topic| %>
  <div class="topic-list-item">
    <a href="<%= topic.relative_url %>" class="topic-list-title"><%= topic.data.title %></a>
    <% if topic.data.tags %>
    <div class="tags">
      <% topic.data.tags.each do |tag| %><span class="tag" data-tag="<%= tag.downcase.gsub(/\s+/, '-') %>"><%= tag %></span><% end %>
    </div>
    <% end %>
  </div>
<% end %>
</div>
