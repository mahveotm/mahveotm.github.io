---
layout: post
title: Tweepedia
subtitle: Let's try something!
image: /img/IMG_-vlg61a.jpg
---

Can we make a change?

A couple of times on Twitter, we stumble upon a new word, a new name or something we just haven't heard before.
As a routine, what we do is exit twitter, check the word on Google, and then probably read up more on Wikipedia.


What if there was a bot that responds to mentions and gives you snippets of the subject you intend to search for from Wikipedia.
It would also provide a link should you desire to read further without you leaving Twitter!

![Dang!](/img/screenshot3_1552252418057.png)

I call it **[Tweepedia](https://twitter.com/mahveo)** (culled from Twitter and Wikipedia) and it works in an essentially simple fashion. It reads up mentions and checks the content with the REST API Wikipedia provides. It then returns a snippet of the article (in 240 words considering twitter character limit) and a continue reading link.

This I expect will save time and web resources leaving us to continue using Twitter while we get the information we desire.

![Lala!](/img/screenshot2_1552252398487.png)

Currently, only the English Wikipedia is supported, but hopefully, other features and languages will be added.

So please try it out, mention @mahveo and type out your favourite band, or that name that has been popping on your timeline, Wikipedia might just have an article about it. 

For subject without a corresponding Wikipedia article, a response is given noting that the Wikipedia article does not currently exist.

PS, please note, some subjects entry are case sensitive, so @mahveo Jon Bellion would produce an entry, while @mahveo Jon bellion may not.

For devs, the project is open source, and the repo is [here](https://github.com/mahveotm/Tweepedia). 

Comments, suggestions and pull request are very much welcomed!
