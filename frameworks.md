[Daniel Norris](https://github.com/daniel-norris), 25 May 2020
 
[Home](./) > Accelerating web and API development with frameworks

![](https://camo.githubusercontent.com/c4b3056564d4d97f40afa08cffefa26c2a695316/68747470733a2f2f7265732e636c6f7564696e6172792e636f6d2f6474666276766b79702f696d6167652f75706c6f61642f76313536363333313337372f6c61726176656c2d6c6f676f6c6f636b75702d636d796b2d7265642e737667)
[^1] *Laravel - an open source PHP web framework*

A lot has happened since my last post and I have to admit it's been particularly difficult juggling the bootcamp, side projects I'm trying to complete and find time to blog. 

One of the biggest obstacles I've found, is that I've been placing too much emphasis on trying to write "good" content but to the detriment of even starting. I have a backlog of blog ideas but keep pushing the writing to one side to prioritise coding and want to find a better balance. So I'm going to opt for shorter posts but on a more consistent basis. 

## What's happened so far... 

In the past six weeks, we've covered **a lot** of content, including: 

[x]   JavaScript  
[x]   The DOM  
[x]   Tooling, e.g. Git & Gulp   
[x]   OOP PHP   
[x]   Laravel Blade   
[x]   Laravel APIs  

I also spotted a great idea on Twitter called the **#100DaysOfCode** challenge and opted to participate and try to set aside at least an hour every day to contribute to project work. 

Creating something independently, I find, really helps my understanding of a subject and provides a great opportunity to explore an area a bit deeper. It's tricky to commit to it every day because of the bootcamp workload but some is better than none. You can check out what I've done so far on GitHub [here](https://github.com/daniel-norris/100-days-of-code/blob/master/log.md). 

## Getting to grips with Laravel    

The past two weeks have been spent developing a basic full stack application on the LAMP stack. We were introduced to a tool called [Vagrant](https://www.vagrantup.com/) which we used to setup our development environment and at the end of the two weeks deployed the app to our own [AWS EC2](https://aws.amazon.com/ec2/) instances using an automation deployment tool called [Capistrano](https://capistranorb.com/). You can find a copy of the repository on my GitHub [here](https://github.com/daniel-norris/laravel_setup). 

What I found really suprising was how much of the legwork, a framework like Laravel, covered in respect to routing, authentication, MVC's, migrations and testing. 

My preconceptions of how difficult it would be to develop something like an API were a lot different to my experience of doing it with the support of a framework. Which is not only encouraging but probably a bit of a relief too. I'm interested in exploring how less mature frameworks like `Express.js` achieve similar things and want to look at this at a later date. 

## Key takeaways from developing using a framework

Every time I blog, it begins begrudgingly and then ends with the realisation (once again) about how beneficial thinking retrospectively about what I've learnt over the past few weeks has been for my learning process. 

This is one of those moments and when I think about it, there has been quite a few takeaways that are transferable regardless of the framework you use. 

### Unit testing is your friend 
I found TDD did two things: (1) it made me slow down and think about the approach I was taking when developing logic in my applications and (2) it provided a systematic way to break down larger more complex problems. Plus, there was something strangely satisfying about getting all green passes to light up on your test runner. 

### MVC design patterns 
It took a couple days for this concept to really sink in but once it did it provided a great mental model for how to approach the implementation of a new feature or how to debug the application when something went wrong. 

### `dd()` often
Dump more often. Making this a habit helped me to unblock myself multiple times during the week and debug my own code 10x as fast. 

### Documentation is a skill too 
Working your way around documentation quickly and efficiently is a skill in its own right. Half of the battle as a beginner feels like *knowing* what is the right question to ask in the first place. By the end of the week, getting to grips with the Eloquent ORM, PHP Unit, Faker, Passport and Laravel docs was a smoother process. 

### Work smarter not harder 
When we first started looking at Laravel, I had concerns about how much the added layer of abstraction prohibited us from developing the solutions ourselves in native PHP. Now I realise how much there is to know when you consider testing, tooling, automation and deployment on AWS and it's okay not to be an capable of doing **everything** at once. 

We're already working on layers and layers of abstraction, utilise it to focus on solving bigger problems faster and more efficiently. 

[^1]: https://laravel.com/
