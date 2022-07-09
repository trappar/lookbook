---
layout: default
title: Configuration
---

Lookbook uses your ViewComponent config so it normally doesn't need any additional configuration to know where to look for your components and preview classes etc. However there are a number of Lookbook-specific configuration options that you may want to use.

{{ toc }}

## Configuring Lookbook

You can add Lookbook configuration in your `config/application.rb` file, an initializer or anywhere else you handle your Rails app configuration.

```ruby
# config/application.rb
module MyApp
  class Application < Rails::Application
    # other app config...
    config.lookbook.project_name = "Lookbook Demo"
  end
end
```

## Available Options

Below are some of the most commonly used configuration options. For a full list check out the [configuration API docs](/api/config).

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
