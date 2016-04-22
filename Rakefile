task default: :serve

desc 'Run the local development server'
task :serve do
  system('bundle exec jekyll serve --drafts')
end

desc 'Create a new news post'
task :new_post do
  File.open('_drafts/new-news.md', 'w') do |file|
    content = <<TXT
---
layout: post
title: "New News"
date: #{Time.now.strftime('%Y-%m-%d %H:%M:%S %z')}
---

Put your news here...
TXT

    file.write(content)
  end
end