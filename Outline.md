Teaching with Rmarkdown
========================================================
author: Shamar Stewart and Clay Wright
date: Nov. 23, 2020
autosize: true

Outline
========================================================

- Bottom-up (Clay)
- Static documents (Shamar)
- Slides (Shamar)
- Other resources (Clay)

Bottom-up (Clay)
========================================================

- Start a project
- Rstudio cheatsheets


Static documents (Shamar)
========================================================

- Template files
- Generating multiple filetypes

Slides (Shamar)
========================================================

- Beamer (ppt), ioslides (html)
- Powerpoint (has its limitations)

Other resources (Clay)
========================================================
- Exams ([http://www.r-exams.org/](https://github.com/carpentries/sandpaper))
- Interactive lessons
    - Basic markdown
          - Using parameters to create quizzes
          - Learnr ([https://rstudio.github.io/learnr/](https://github.com/carpentries/sandpaper))
          - Sandpaper (carpentries style lessons, [https://github.com/carpentries/sandpaper](https://github.com/carpentries/sandpaper))
- Shiny
    - Plots of Data ([https://huygens.science.uva.nl/](https://huygens.science.uva.nl/))
    - Rstudio inbuilt templates

Exams package
========================================================

[http://www.r-exams.org/](http://www.r-exams.org/)
I've used this to put together problem sets for HWs and flipped-classes.
It works just OK for uploading to Canvas. I mostly export to PDF.
It is nice once you have a good question bank.

Interactive lessons with markdown
========================================================
An easy approach
- Using parameters to create quizzes
    - Include `params` in your yaml header to exclude code and solution/key code blocks

Interactive lessons with markdown
========================================================

```yaml
params:
  key: FALSE
  code: TRUE
```

Interactive lessons with markdown
========================================================
An easy approach
- Using parameters to create quizzes
    - Include `params` in your yaml header to exclude code and solution/key code blocks
    - In the setup chunk create

Interactive lessons with markdown
========================================================

```r
knit_engines$set(answer = function(options) {
  if (options$include && options$echo && options$eval) knit_child(text = options$code)
})
```


Interactive lessons with markdown
========================================================
Other resources
- Learnr [https://rstudio.github.io/learnr/](https://github.com/carpentries/sandpaper)
    - create exercises and quizzes within markdown html
    - I believe there is a way to collect answers
    - Built for teaching R
- Sandpaper [https://github.com/carpentries/sandpaper](https://github.com/carpentries/sandpaper)
    - carpentries style lessons built in Rmarkdown
    - Independent, self guided lessons
    - Might be an easy way to build/customize a quick intro from carpentries/data camp materials.
- Bookdown [https://bookdown.org/yihui/bookdown/](https://bookdown.org/yihui/bookdown/)
    - put this all together to create interactive, online textbooks

Shiny
========================================================

Plots of Data [https://huygens.science.uva.nl/](https://huygens.science.uva.nl/)
- a great way to introduce best plotting pratices and ggplot

Rstudio inbuilt templates
