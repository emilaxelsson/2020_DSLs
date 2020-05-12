![](/dsl.png)

# Making the computer speak BEE

What do web pages, numeric computing, knitting and BEE have in common? Not much, it seems. But I have a suggestion: They can all benefit from *domain-specific programming languages*.

I'm a software developer at Mpowered. I came here after many years of programming language research at [Chalmers University](https://www.chalmers.se). More specifically, my area was in domain-specific programming languages (DSLs). These are "little languages" that are made to solve problems in a limited domain. As such, they are designed to speak the language of the *domain expert* rather than the programmer.

This post will present DSLs in general, demonstrate some of the uses of DSLs at Mpowered, and show some ideas we are exploring for the future.



## DSL examples

There are a wide range of DSLs available for different purposes. Here follows a few examples.

### HTML

HTML is the main language for the front end web developer. It allows you to describe the contents of web pages in a structured form. Here is a simple piece of HTML:

```html
<h1>Free time</h1>

Things I like to do in my free time:

<ul>
  <li>Swimming in the sea</li>
  <li>Watching birds</li>
</ul>
```

This little snippet may get rendered into something like the following in the front end:

> <b>Free time</b>
>
> Things I like to do in my free time:
>
>   * Swimming in the sea
>   * Watching birds

Note how the HTML code captures exactly the intention of the text -- no more and no less. For example, it does not dictate a certain font or letter size. It doesn't even say whether the list items should be marked by bullets or something else. `<ul>` simply stands for "unordered list", and `<li>` stands for "list item".

### MATLAB

[MATLAB](https://en.wikipedia.org/wiki/MATLAB) ("MATrix LABoratory") is a programming language for numerical processing. It aims to make such programs easier to write by supporting notation familiar to mathematicians. A large part of our daily lives are built around data processing units -- for example TV sets, mobile phones and base stations, control systems in smart cars, etc. There's a high probability that these programs are based on mathematical equations that have first been prototyped and tested in MATLAB. Some applications even run directly in MATLAB and its associated tooling.

### Kitting stitch patterns

Just to throw in a bit of a wild card into the mix: there is even a DSL for [kitting patterns](https://www.knittingstitchpatterns.com).

How about this program for making a ["pie crust basketweave"](https://www.knittingstitchpatterns.com/2014/08/pie-crust-basketweave.html) pattern:

```
Knitted in a multiple of 8, +2 sts and a 8-row repeat.
Row 1 - Wrong side:  Purl 2 * knit 6, purl 2; repeat from * to end.
Row 2 - Right side: Knit 2, * purl 6, knit 2; repeat from * to end.
Row 3: As Row 1.
Row 4: Knit.
Row 5: Knit 4, purl 2, * knit 6, purl 2; repeat from * to last 4 sts, knit 4.
Row 6: Purl 4, knit 2, * purl 6, knit 2; repeat from * to last 4 sts, purl 4.
Row 7: As Row 5.
Row 8: Knit.
```

I admittedly have no idea how to read the above. But to someone who knows the language, it makes perfect sense. Again, the point is that it captures exactly the right amount of information for creating the pattern. It does not say anything about color or thickness of the thread, for example.



## Taking advantage of your limitations (how less is more)

The main advantage of DSLs is the fact that they can be used by domain experts who are not necessarily programmers in the ordinary sense. But this is not just a matter of understandability. By limiting the kinds of programs one can write, we can actually do *more* things with them than we can with programs in general-purpose languages.

A good illustration is HTML, which does not by itself support any kind of computations or actions (such as reading/writing to/from the disk, starting other programs, etc.). Because of this limitation, we can do things with HTML pages that we generally cannot do with ordinary programs (written in Java, say):

  * We can interpret the same HTML page in different ways -- with different styles and layouts, for example.
  * We can analyze the page, e.g. to see what other pages it links to.
  * We can split the page in parts and render each section in parallel.
  * Etc.



## DSLs at Mpowered

