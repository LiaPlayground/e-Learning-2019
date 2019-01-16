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

More or less, all of the mentioned systems have drawbacks in some of the
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



## 2. How Does It Work



### 2.1 Basic Syntax

### 2.2 Extensions to Markdown

#### 2.2.1 Quizzes and Surveys




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
