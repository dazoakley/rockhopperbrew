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
author: Daz
excerpt_separator: <!--more-->
---

Put your news here...
TXT

    file.write(content)
  end
end

desc 'Build the site (into _site/)'
task :build do
  system('rm -rf _site/*')
  system('bundle exec jekyll build')
end

desc 'Deploy the site'
task :deploy => :build do
  system("rsync -e ssh -avr --delete-after --delete-excluded _site/ admin@rockhopperbrew.co:/srv/rockhopperbrew.co/public/htdocs/")
end
