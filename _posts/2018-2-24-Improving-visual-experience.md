---
layout: post
title: Improving my blog's visual experience.
---

The code block highlights were bad, finally i got one solution.

While i was in the creative process of this blog, i found that all code blocks that in wrote in the markdown language were rendering poorly in the final HTML webpage, producing a block of code similar to the one shown in the following image.

![Error using the library]({{ site.baseurl }}/images/2018-2-24/visual_bug.png "Visual bug")

After searching exhaustively, i found the solution by editing the SASS source files, at %ROOT_DIR%/_sass/_highlight.scss the following code was found between lines 1 to 11.

~~~ css
.highlight {
  background-color: #efefef;
  ...
~~~

Changing line two for this:

~~~ css
pre.highlight {
  background-color: #efefef;
  ...
~~~

Eureka! Problem solved.