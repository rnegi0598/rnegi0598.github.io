---
title: "Setting up the Jekyll blog site"
date: 2023-02-12 18:03:00 +0530
categories: [Tutorial]
tags: [jekyll,ruby,github]
toc: true
---
---
# Step 1
Jekyll is a static site generator which you can further tweaked according to your prefrences. To make it running following packages need to be installed in ubuntu :
1. Ruby   
2. RubyGems
3. GCC and Make

```bash
sudo apt-get install ruby-full
```
This installs ruby,rubyGems and some other files needed for working of ruby applications. `ruby -v ` will give the version of ruby installed.
ruby is the interpreter and ruby-gems is the package manager for ruby packages (just like we have apt in ubuntu ).

```bash
sudo apt-get install build-essential
```
Which contains packages(like GNU/g++ compiler and debuggers) to compile software .Why do ruby needs it ? May be ruby interpreter requires it .
```bash
sudo apt-get install zlib1g-dev
 ```
which is a compression library .Again might be used by the interpreter or sometihng else .

---
# Step 2
Configuring the gem installation path to home directory (so need to use sudo  to install ruby gems packages).
```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
---
# Step 3 
Install gems jekyll and bundler in gems folder we configured above . bundler is  ruby dependency management tool which tracks the dependencies and their versions and store them in Gemfile.

```bash
gem install jekyll bundler
```

---
# Step 4.1 To create new jekyll site
```bash 
jekyll new myblog
```
This will create new site at ./myblog with default theme as Minima.
To run the site 
```bash
 bundle exec jekyll serve
```
for the first time and
```bash
jekyll serve
```
therafter.

---
# Step 4.2 To create jekyll site with new theme ( [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)){:target="_blank"}
1. Fork the repo [Chirpy Starter](https://github.com/cotes2020/chirpy-starter){:target="_blank"} and name it <GH_USERNAME>.github.io 
1. clone it to you computer
1. Install the dependencies using `bundle`
1. Running the local server `bundle exec jekyll s`
1. [How to add post](https://chirpy.cotes.page/posts/write-a-new-post/){:target="_blank"} 
1. 
```bash
git status 
git add .
git commit -m 'your message'
git push
```



