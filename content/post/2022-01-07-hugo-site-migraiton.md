---
title: 'Running my dev.to blog using Hugo on Netlify'
date: '2022-01-07'
tags: [ blog, Netlify, Hugo]
---

### Running my dev.to blog using Hugo on Netlify

I am a big fan of dev.to, and the work that the team are doing to foster a great community of builders is something that keeps me here. However, I have always maintained another blog (running on Netlify, which is also super awesome), kind of like a mirror, which has the same content, but runs on a different stack.

>**workflow**

> [Write content locally in markdown] ---> [Publish on dev.to] ---> [Sync to mirror on Netlify]

Up until last year, I was able to publish to dev.to and it would take care of publishing to that mirror. It was super easy - I write in markdown locally using Macdown, so I would create my posts, publish to dev.to and it would automagically sync up to my mirror. Nothing lasts for ever as they say, and I was sad (but completely understood) when dev.to made some changes that caused this to stop working.

Over the Christmas break, I took some time to rethink how to do this. All my existing blog posts were on my macbook in markdown files, so I wanted an easy way to be able to publish these to a new blog.

I ended up looking at Hugo, given that is what had been driving the sync between dev.to and Netlify. I downloaded the tool, worked through the quick start and very soon I had a simple blog up and running. Some great documentation and tutorials, so this made it super easy. I liked what I saw, and the amazing number of available themes so decided that this looked like a good option.

There were a number of things however that I needed to do, so wanted to share how I approached this in this blog post.

**Hugo Themes**

With so many themes, and all of them very nice, how do you know which one to go with? In the end I went with a super simple one, which was optimised for accessibility. I hope this makes it accessible to all, as I am not sure the previous theme supported screen readers very well.

One thing I learned was that you needed to fork the theme you wanted to use, before adding it as a submodule to your repository. The reason for this is in case you wanted to make any changes to the theme and not have them over written. So I forked the [cupper-hugo-theme](https://github.com/094459/cupper-hugo-theme) made my changes (which was just a couple of minor changes to support the layout I wanted to use).

**Hugo metadata**

Whilst my content was all in markdown, and I could simply use copy/paste to publish in dev.to, in Hugo I needed to add some metadata so that Hugo could identify what the name of the post was, the date, tags and that sort of thing.

I needed to add the following to each post.

```
---
title: 'Innovate Machine Learning and AI - learn how to kick start your journey'
date: '2019-10-04'
tags: [event, AWS Deep Racer]
---
```

I didn't really want to manually add these, so looked to see what open source tools/scripts others might have put together. I stumbled upon [dev-fetch-articles](https://github.com/iggredible/dev-fetch-articles) from Igor Irianto, which I modified slightly (you can see my fork [here](https://github.com/094459/dev-fetch-articles) ), which exports all your posts from dev.to, and allows you to add these meta data into the markdown files.

I modified it to change the format of the meta data, as well as add some new ones. It is a super easy tool to use, so thank you Igor!

Running this left me with a folder with 130+ blog posts, now with the right meta data. They were ready to go into Hugo.

I decided that I would create two sets of content - all the stuff for the newsletter, and all the rest. So I moved this to the content folder under the hugo site I created and it looked like this.

```
├── _index.md
├── about.md
├── blog.md
├── newsletter
│   ├── 2020-01-11_aws-open-source-news-and-updates-1.md
│   ├── 2020-01-17_aws-open-source-news-and-updates-2-.md
...
│   ├── 2021-12-13_aws-open-source-news-and-updates-93.md
│   └── 2021-12-20_aws-open-source-news-and-updates-94.md
└── post
    ├── 2019-12-09_reinvent-2019-workshop-list.md
    ├── 2020-10-15_amazon-aurora---setting-up-and-configuration-four-ways.md
     ...
```

**Hugo Configuration**

All the magic happens in the configuration file, which initially I struggled with but soon found lots of great resources online to help. 

Within this I configured the navigation (to support the layout in the previous step) as well as setup some of the essential stuff such as the base dns name (this was important, as when I initially deployed this, the site "broke" as all the links were using incorrect links). You can change a lot of how the site works from the configuration file, and this varies from theme to theme.

You can view all of this in the repo, [config.yaml](https://github.com/094459/blog/blob/main/config.yaml)

**Testing locally**

Once I had this up and running, I could use:

```
hugo serve
```

And then test the site using a browser at http://localhost:1313 to make sure it looked ok. It does hot reloading, so I could make changes and see them immediately. The only thing that hot reloading did not seem to work with though is tags, so I needed to stop/start to see the tags update.

Once the site looked good, it was time to publish.

### Publishing the site

Now that I have a site that works, the next decision was publishing. Hugo allows you to export your site via the publish command, creating a folder that is ready for deploying on your favourite web hosting solution.

I contemplated just exporting this to an Amazon S3 bucket, but in the end really loved the simplicity of the Netlify experience. It took care of the hooks to the GitHub repo, automatically building/publishing the site. It had some nice features around automating the domain name and things like Google Analytics. In the end I decided to stick with Netlify, but at least I know I have options and can publish anywhere - all I need to do is update by dns. 

So the new workflow is more work than before, but I have the advantage of the content now being in my GitHub repo as a system of information, which I have the flexibility to change how/where I publish to over time.

>**new workflow**

> [Write content locally in markdown] ---> [Publish on dev.to]
> [Commit to GitHub]   ---> [Auto build site on Netlify]

#### Thanks all folks

Thanks for listing, let me know if you have any questions on this. I kind of put this post together as a "test" for the new blog, so am hoping it comes through. Also be sure to check out Hugo, it really is such a nice tool to use. If you are using dev.to, make sure you check out the project above that helps you easily export your files and convert them into markdown you can then host anywhere you want. Finally, I used the Cupper theme which really is super nice, check that theme out for your own Hugo sites - I love it. 

