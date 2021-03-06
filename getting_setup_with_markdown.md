[Daniel Norris](https://github.com/daniel-norris), 19 March 2020

[Home](./) > Getting setup with Markdown

<br>

About 2 weeks to go till the start of the course and with the UK in a complete state of panic, sterling at a 35-year low and an inevitable economic recession coming up - I'd imagine there's been better opportunities in the past few years to think about changing careers. 

Still, onwards and upwards... 

Our first video conference uncovered this little gem called Markdown which I'm trying out for the first time. It produces markup which eliminates some of the annoying problems you run into when trying to keep snippets or code blocks in a word processor. The syntax highlighting functionality alone is great. Plus, you can host it on Github Pages which will conveniently help me avoid paying to host a blog that no one will probably ever read. 

**Markdown Editors**<br>
The Markdown website suggests some great tools and components for Markdown including: 

- [StackEdit](https://www.markdownguide.org/tools/stackedit/)
- [Notable](https://www.markdownguide.org/tools/notable/) 
- [Bear](https://www.markdownguide.org/tools/bear/)
- [Dillinger](https://www.markdownguide.org/tools/dillinger/) 
- [Jekyll](https://www.markdownguide.org/tools/jekyll/) 

Opted for StackEdit as it includes support for nearly everything including HTML and runs on Windows OS, plus the UI resembles EverNote which makes the transition feel like less work.  

**Hosting**<br>
The GitHub Pages site covers hosting and setting up a repo for it to be hosted. You'll need to copy the Jekyll themes and paste into your repo to edit if you want to change the HTML or CSS. 

You'll need to setup the _config.yml file to ensure its using the right Markdown processor (Kramdown in this case is GitHub Pages default) and the right syntax highlighter (Rouge is the default). You can copy and paste this into your config file and change the `title` and `description` to get started. 

	theme: jekyll-theme-tactile
	title: N00b to Coder
	description: Learning to code, plus notes, observations and general rants...
	highlighter: rouge
	markdown: kramdown
	kramdown:
		input: GFM
		auto_ids: true
		syntax_highlighter: rouge


**Syntax**<br>
The Markdown website offers cheatsheets and overview of syntax. John Gruber's original documentation is a good place to start too. 

- [Markdown Cheat Sheet](https://www.markdownguide.org/cheat-sheet/)
- [John Gruber's Documentation](https://daringfireball.net/projects/markdown/)

Some interested functionality includes syntax highlighting and how easy it is to include code blocks. 

```javascript
//triple backtick (`) followed by lang name
// ```javascript

for (let i = 0; i < 3; i++) {
	console.log("Hello, World!"); 
}
```
```javascript
//single tab 
let a = b 
```

That's it! Time for a coffee. 
