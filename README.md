<!--
author:   André Dietrich, Sebastian Zug

email:    andre.dietrich@ovgu.de

version:  0.0.1

language: en

narrator: US English Female

comment:  Try to write a short comment about
          your course, multiline is also okay.

-->

# Liascript: A "new" Language for creating interactive online Courses

LiaScript is an attempt to enable everyone to create free and interactive online
courses, without the need of being an experienced programmer. Instead it aims to
bring both parties, software- and course-developers, closer together by
introducing Open-Source techniques into the Open-courSe development process.
LiaScript was designed to be compatible to Common-Markdown, but it introduces
lots of language extensions that deal with quizzes, suveys, ASCII-art,
text2speech, animations, online programming, the integration of JavaScript, etc.
as well as its own Macro-System that simplifies tedious and repetitive tasks. It
comes along with its own Just-In-Time compiler that runs in the Browser and
therefor does not require additional tooling.

## 1. Introduction

LiaScript was initially developed within the _"Industrial eLab-Project [^1]"_,
which aims to make university hardware and laboratories accessable via the
Internet. But, we soon realized that only by giving remote access to these
ressources via a fancy website  we will run into problems. Our mobile
Arduino-Bots could be used to teach programming, sensing, navigation, dive into
operating systems or even to applay artificial intelligence. Thus, the real
problem was to develop an extendable and adaptable system for creating courses
(instead of a single WebApp) with different objectives and for students with
different backgrounds, which only interface with our hardware other other
external ressources.

TODO: eLab image ...

Shurely, creating an online-course from scratch requires a lot of expertiese in
different web technologies at frontend (e.g., HTML, JavaScript, CSS, testing),
backend (e.g., webservers, databases), and different communication standards to
connect both sides (e.g., CRUD, Websockets, AJAX). Hence, it is nearly
impossible for a non-programmer to understand all of these issues, before
starting to develop his or her own online course. Screen- or pod-casts are not a
real alternatve, since they are expensive and time consuming in production, not
easy to change or translate, and require additional skills in movie cutting.
That is why plattforms such as Udacity or Coursea invest a lot of effort and
money in high-quality course productions, which is comparable to movie
productions, including screenplays, actors, different sets and locations.

Fortunatelly, there are also other course plattforms that try to ease the  course development for non-experts, such as Ilias, edX, Moodle,

TODO: noch mehr ....

And how is such a kind of "simplicity" achieved? Mostly, by offering an
integrated config-system and editors, that shall enable the user to create a
course with a lot of buttons and menues, sub-sub-menues, and masks, whos only
purpose is to hide the non-intuitive syntax and semantics of a language
that can be easily interpreted machines, not by humans.

> We should instead start to create languages that can be easy understood and
> applied by humans, in order to describe their intentions, and let the
> machine rack its cpu in order to find an appropriate translation.

[^1]: TODO: elab

## 2. Adapting OpenSource Development

More or less, all of the aforementioned systems have drawbacks in some of the
following points:

**Requirements from an OpenSource perspective**

1. No support for larger course developer-teams, including those who develop
   additional functionality and those who provide content
2. No versioning, in contrast to Wikipedia as a single source of truth, content
   shall be provided in different "styles" for a heterogenous groups of students
3. No reusability, parts of one course cannot simply be applied of coppied into
   another project
4. No support for internationalization/localization (i18n), thus a course cannot
   simply be translated into another language
5. No variance in representation
6. Difficulties in adopting and integrating new web technologies

Pin-points 1 and 2 can be easily solved by applying version control systems such
as git[^2], svn[^3], mercury[^4], etc. and their web-based hosting services such
as GitHub[^5], GitLab[^6], SourceForge[^7], etc. to name only a few. All
required ressources, including images, videos, datasheets, javascript and
css-styles, and everything else can be easily uploaded and made available via
the internet.

[^2]: Todo: git
[^3]: Todo: svn
[^4]: Todo: mercury
[^5]: Todo: github
[^6]: Todo: gitlab
[^7]: Todo: SourceForge

### 2.1 LiaScript: Basics

To describe educational content, Markdown can be applied, a lightwheigth
markup language that is widely applied in OpenSource-projects for documentation.
Of course, we are not the first ones that apply Markdown to ship educational
contents, earlier examples are:

* [gitbook](TODO):
* [common-mark](TODO):
* [elearnjs](TODO):
* [ascii-doc](TODO):
* others:

TODO: github flavored markdown ...

### 2.2 Extensions to Markdown

an other representation style ... watch youtube like screen cast with interactive elements backed in

one benefit of using markdonw ... still readable ...

#### 2.2.1 Multimedia Content & ASCII-Art

                            --{{0}}--
References in Markdown are encoded with a simple bracket-parenthesis notation
and a starting exlamation-mark defines it as an image.


``` markdown
[i am an link](link url)

![I am an image](image-url "info")
```

                           --{{1}}--
In contrast to this, it is still complicated to include multimedia content.
Based on the previous notation, it is possible in LiaScript to mark a link as an
audio-file by adding a starting question-mark, which can be interpreted with a
little bit of imagination as an ear. Adding an additional excalmation-mark can
be interpreted as visual plus audio and thus marks the appearance of a movie.
The benefit of this notation is, that it is still compatible with Markdown, and
at every other Markdown-viewer you will still have a working link to click on.

``` markdown
?[i am an link](link url)

!?[I am an image](image-url "info")<!--width="800px"-->
```

From our experience, we know that a lot of produced images represent simple
diagrams that represent some signal values or some trends. Plotting them with
Excel, gnuplot, or any other programm, makes it also difficult to change them or
to translate labels. Well, in LiaScript you can simply create such diagrams by
using your text editor, such ASCII-art patterns are automatically detected and
translated into a nicely rendered diagram. Different charaters represent
different colors and upper and lower-case different sizes. So that you can still
refer in your text to the red line. For more elaborate examples of ASCII-art, see also the documentation at: Todo


``` HTML
    <!--style="max-width: 400px"-->
                            Multiline-Diagram
    1.9 |    DotS
        |                 ***
      y |               *     *
      - | r r r r r r r*r r r r*r r r r r r r
      a |             *         *
      x |            *           *
      i | B B B B B * B B B B B B * B B B B B
      s |         *                 *
        | *  * *                       * *  *
        +------------------------------------
        0              x-axis               1
```

        <!--style="max-width: 400px"-->
                            Multiline-Diagram
    1.9 |    DotS
        |                 ***
      y |               *     *
      - | r r r r r r r*r r r r*r r r r r r r
      a |             *         *
      x |            *           *
      i | B B B B B * B B B B B B * B B B B B
      s |         *                 *
        | *  * *                       * *  *
        +------------------------------------
        0              x-axis               1



As you have problably noticed, the code examples contain aditional comments with attributes that are used to style the associated elements, a comment at the beginning of a block (i.e., table, list, paragraph) is used to style the entire block, if it is attached to the end, it can be used to style single elements, such as words or phrases.


``` markdown
<!--style="color: red"-->
This whole paragraph will be colored in red ;-)<!--
class="animated infinite bounce"
style="animation-delay: 3s;"
-->, but only this smiley is going to start jumping
after 3 seconds.
```

        <!--style="color: red"-->
This whole paragraph will be colored in red ;-)<!--
  class="animated infinite bounce"
  style="animation-delay: 3s;"
-->, but only the smiley is going to start jumping
after 3 seconds.


#### 2.2.2 Quizzes and Surveys

                              --{{0}}--
One of the language feature we wanted at most, was an easy way to integrate
quizzes in different flavors and thus, to give students the possiblity to check
their knowledge. Quizzes are always associate with double brackets, such that to
add a text quiz, you only have to enter the solution in double braces and the
input fild, check and show solution buttons are automatically generated.


                               {{0-1}}
*******************************************************************************

``` markdown TextQuiz
What did the **fish** say when he hit a **concrete wall**?

      [[dam]]
```

What did the **fish** say when he hit a **concrete wall**?

      [[dam]]

*******************************************************************************

--{{1}}--
Some might adapt the question to handle the disambiguity in this question. But
LiaScript also offeres different methods to tweak a quiz in various ways. It is
either possible to add as manny hints, by adding question-marks in double
brackets and let the user decide if he needs help, by clicking on the associated
button in the rendered course. The additional `script`-tag allows to check the
input and trim the input or transform the input to lower-case and to compare it
with different allowed solution. Therefor the `@input`-macro gets replaced by
the current user input. The final Markdown-blocks surrounded by two lines of
stars define an more detailed explanaition, which appears if either the user
input was correct or if the user clicked onto the resolve button.


                                {{1-2}}
*******************************************************************************

``` markdown TextQuiz
What did the **fish** say when he hit a **concrete wall**?

[[dam]]
[[?]]   Do not thake this question serious.
[[?]]   It is actually a joke in lower-case.
<script>
  let input = "@input".trim().toLowerCase();
  input == "damn" || input == "dam";
</script>
******************************************************

A __dam__ is a barrier obstructing flowing water.

__Damn__ usually refers to damnation, a condemnation,
usually by a god; frequently used as a profanity.

******************************************************
```

What did the **fish** say when he hit a **concrete wall**?

    [[dam]]
    [[?]]   Do not thake this question serious.
    [[?]]   It is actually a joke in lower-case.
    <script>
      let input = "@input".trim().toLowerCase();
      input == "damn" || input == "dam";
    </script>
    ******************************************************

    A __dam__ is a barrier obstructing flowing water.

    __Damn__ usually refers to damnation, a condemnation,
    usually by a god; frequently used as a profanity.

    ******************************************************

*******************************************************************************








                              --{{1}}--
How would you encode a multiple-choice quiz with a typewriter, probably
similarly as we did it, which looks like a list of simple check buttons that
alreay shows the correct solution. You can add as much rows/options.


                              {{1-2}}
*******************************************************************************

``` markdown Multiple-Choice-Quiz
Just add as many points as you wish:

    [[X]] Only the **X** marks the correct point.
    [[ ]] Empty ones are wrong.
    [[X]] ...
```

Just add as many points as you wish:

    [[X]] Only the **X** marks the correct point.
    [[ ]] Empty ones are wrong.
    [[X]] ...

*******************************************************************************

           --{{2}}--
Knowing how check buttons can be defined by using brackets, it seems obvious to
define radio buttons and thus single choice quizzes with the following syntax.

{{2-3}}
*******************************************************************************

``` markdown Single-Choice-Quizzes
Click the center!

    [( )] This is wrong.
    [(X)] <-- The only correct option.
    [( )] Also not right.
```

Click the center!

    [( )] This is wrong.
    [(X)] <-- The only correct option.
    [( )] Also not right.

*******************************************************************************



{{3-4}}
*******************************************************************************

``` markdown Single-Choice-Quizzes
What did the **fish** say when he hit a **concrete wall**?

    [[dam]]
    [[?]] This is actually a joke.
    [[?]] Fishes cannot realy speak.
    <script>

    </script>
********************************************

todo

********************************************
```

What did the **fish** say when he hit a **concrete wall**?

    [[dam]]
    [[?]] This is actually a joke.
    [[?]] Fishes cannot realy speak.
    <script>

    </script>
********************************************

todo

********************************************

*******************************************************************************





#### 2.2.2 Diagrams and ASCII-Art

Use ASCII-Art to draw diagrams:

                            Multiline-Diagram
    1.9 |    DOTS
        |                 ***
      y |               *     *
      - | r r r r r r r*r r r r*r r r r r r r
      a |             *         *
      x |            *           *
      i | B B B B B * B B B B B B * B B B B B
      s |         *                 *
        | *  * *                       * *  *
        +------------------------------------
        0              x-axis               1


#### 2.2.3 Fragments & Text2Speech

### 2.3 Embracing the Internet

What did the **fish** say when he hit a **concrete wall**?

    [[dam]]

### Multiple Choice

Just add as many points as you wish:

    [[X]] Only the **X** marks the correct point.
    [[ ]] Empty ones are wrong.
    [[X]] ...

### Single Choice

Just add as many points as you wish:

    [( )] ...
    [(X)] <-- Only the **X** is allowed.
    [( )] ...

## Executable Code

A drawing example, for demonstrating that any JavaScript library can be used, also for drawing.

```javascript
// Initialize a Line chart in the container with the ID chart1
new Chartist.Line('#chart1', {
  labels: [1, 2, 3, 4],
  series: [[100, 120, 180, 200]]
});

// Initialize a Line chart in the container with the ID chart2
new Chartist.Bar('#chart2', {
  labels: [1, 2, 3, 4],
  series: [[5, 2, 8, 3]]
});
```
<script>@input</script>

<div class="ct-chart ct-golden-section" id="chart1"></div>
<div class="ct-chart ct-golden-section" id="chart2"></div>


### Projects

You can make your code executable and define projects:

``` js     -EvalScript.js
let who = data.first_name + " " + data.last_name;

if(data.online) {
  who + " is online"; }
else {
  who + " is NOT online"; }
```
``` json    +Data.json
{
  "first_name" :  "Sammy",
  "last_name"  :  "Shark",
  "online"     :  true
}
```
<script>
  // insert the JSON dataset into the local variable data
  let data = @input(1);

  // eval the script that uses this dataset
  eval(`@input(0)`);
</script>

## More

Find out what you can even do more with quizzes:

https://liascript.github.io/course/?https://raw.githubusercontent.com/liaScript/docs/master/README.md
