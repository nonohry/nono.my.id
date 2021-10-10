---
layout: post
title: Menambahkan Plugins Embed Video Youtube
date: 2021-01-01 00:00:00 +0800
category: tutorial
thumbnail: /style/image/logo.png
icon: book
---

* content
{:toc}

Plugin ini digunakan untuk [Jekyll](https://github.com/mojombo/jekyll).

## Cara Pemasangan:
Untuk memasang pluginnya, silakan letakkan saja script dibawah ini pada folder `_plugins`
```
class YouTube < Liquid::Tag
  Syntax = /^\s*([^\s]+)(\s+(\d+)\s+(\d+)\s*)?/

  def initialize(tagName, markup, tokens)
    super

    if markup =~ Syntax then
      @id = $1

      if $2.nil? then
          @width = 560
          @height = 420
      else
          @width = $2.to_i
          @height = $3.to_i
      end
    else
      raise "No YouTube ID provided in the \"youtube\" tag"
    end
  end

  def render(context)
    # "<iframe width=\"#{@width}\" height=\"#{@height}\" src=\"http://www.youtube.com/embed/#{@id}\" frameborder=\"0\"allowfullscreen></iframe>"
    "<iframe width=\"#{@width}\" height=\"#{@height}\" src=\"http://www.youtube.com/embed/#{@id}?color=white&theme=light\"></iframe>"
  end

  Liquid::Template.register_tag "youtube", self
end
```

## Cara Penggunaan
Untuk menggunakannya silakan masukkan kode berikut di postingan blog anda.

contoh:
```
{% youtube id_video %}
```
menjadi
```
{% youtube 7bi1OvfrxLs %}
```

## Hasilnya
{% youtube 7bi1OvfrxLs %}

You can also specify a height and width. If you do not, it defaults to 560 x 420.

```
{% youtube oHg5SJYRHA0 500 400 %}
```