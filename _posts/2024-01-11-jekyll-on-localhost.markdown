---
layout: post
title:  "Running a Jekyll site locally"
date:   2024-01-09 20:31:51 -0500
categories: jekyll hak42
---
So, if I followed the [Github instructions](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/testing-your-github-pages-site-locally-with-jekyll) properly, I would have figured out how to run my Github pages site locally on the first night. Minor details!

Since I originally installed Ruby and Jekyll using Homebrew on the Mac, I needed to trial and error a couple of things. From the folder my site is in on my computer, I ran `bundle exec jekyll serve` and got the error, "bundler: failed to load command: jekyll (/Users/hak42/.asdf/installs/ruby/3.1.2/bin/jekyll)". Not a problem as the instructions on Github warned that that might be a problem and I needed to install webrick. After a couple of tries, I discovered that I needed to do it via Homebrew by typing:

`% brew install webpack`

First problem solved! Next up was the note, "To use retry middleware with Faraday v2.0+, install 'faraday-retry' gem". So, first off I needed to discover what Faraday Retry is! The [Github ReadMe](https://github.com/lostisland/faraday-retry) for the gem was kind enough to tell me that it is a middleware that automatically catches exceptions and retries requests that fail. Sounds useful. Now, I had to figure out how to install it. Well, it turns out I actually installed [Minfrin's Retry](https://github.com/minfrin/retry). It cleared the warning though!

`% brew install retry`

With all of that out of the way, I did `% bundle exec jekyll serve` again and everything looked good in Terminal. I switched over to my browser and navigated to http://localhost:4000 with great success.  

My site is still super ugly, but it is now a bit more functional and it is much easier to test my edits.
