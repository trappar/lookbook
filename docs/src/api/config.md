---
layout: default
title: Configuration Options
---

{% site.data.config_options.each do |data| %}
  {%= config_option data[:name], type: data[:type], default: data[:default] do |option| %}
    {% if data[:example] %}
      {% option.example do %}
        {%= data[:example] %}
      {% end %}
    {% end %}
    {% if data[:description] %}
      {% option.description do %}{{ data[:description] }}{% end %}
    {% end %}
  {% end %}
{% end %}
