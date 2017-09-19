---
layout: post
title: "rake命令生成jekyll文章 "
category: jekyll
tags: []
---


当使用Jekyll写文章的时候，一般需要手动的创建文章，修改文本后缀名，再加文本头加上yml语法开头,步骤繁琐。本文通过一个rake脚本来简化操作

# Rake

Rake，即Ruby Make, 使用ruby开发代码构建工具。

>1. 安装rake gem install rake,可以先查看gem list rake 是否已经安装rake？
2. 编写Rakefile, 放入jekyll的根目录下


rakefile写入如下代码:
{% highlight ruby linenos %}
require 'rake'
require 'yaml'
SOURCE = "."
CONFIG = {
  'posts' => File.join(SOURCE, "_posts"),
  'post_ext' => "md",
}

# Usage: rake post title="A Title"
desc "Begin a new post in #{CONFIG['posts']}"
task :post do
  abort("rake aborted: '#{CONFIG['posts']}' directory not found.") unless FileTest.directory?(CONFIG['posts'])
  title = ENV["title"] || "new-post"
  slug = title.downcase.strip.gsub(' ', '-').gsub(/[^\w-]/, '')
  filename = File.join(CONFIG['posts'], "#{Time.now.strftime('%Y-%m-%d')}-#{slug}.#{CONFIG['post_ext']}")
  if File.exist?(filename)
    abort("rake aborted!") if ask("#{filename} already exists. Do you want to overwrite?", ['y', 'n']) == 'n'
  end

  puts "Creating new post: #{filename}"
  open(filename, 'w') do |post|
    post.puts "---"
    post.puts "layout: post"
    post.puts "title: \"#{title.gsub(/-/,' ')}\""
    post.puts "category: "
    post.puts "tags: []"
    post.puts "---"
  end
end # task :post

{% endhighlight %}



这是一个简洁的版本，你也可以自行添加你的description，categories，tag等。

命令行输入 rake post title="article name"。 马上会在_post创建年-月-日-hello-world.md文章。 
