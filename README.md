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

LiaScript is an attempt to enable everyone to create free and interactive open
educational ressources without the need of being an experienced programmer.
Instead it aims to bring both parties, software- and course-developers, closer
together by introducing Open-Source techniques into the Open-courSe development
process. LiaScript is an extention to Common-Markdown that introduces notations
for quizzes, suveys, ASCII-art, text2speech, animations, online programming
amongst others. It comes along with its own Just-In-Time compiler that runs in
the Browser and therefor does not require additional tooling.

## 1. Introduction

LiaScript was initially developed within the _"Industrial eLab-Project [^1]"_,
which aims to make university hardware and laboratories accessable via the
Internet. But, we soon realized that only by giving remote access to these
ressources via a fancy website (single WebApp) we will run into problems by
offering different courses for the same hardware. Our mobile Arduino-Bots could
be used to teach programming, sensing, navigation, dive into operating systems
or even to applay artificial intelligence. Thus, the real problem was to develop
an extendable and adaptable system for creating courses with different
objectives and for students with differen backgrounds, that only interface with
our hardware other other external ressources.

elab image ...


Shurely, creating an online-course from scratch requires a lot of expertiese in
various different web technologies such as HTML, JavaScript, CSS, Webservers, Databases, testing with different browsers,

CORS, Websockets and other communication protocolls, probably WebGL. It is
nearly impossible for a non-programmer to understand all of this stuff before
developing his own online course. Thus, screen- or pod-casts are not a real
alternatve, since they are expensive and time consuming in their production, bot
not easy to adapt, translate, and require additional skills in movie cutting ...
XXX hier noch Coursea und Udacity einbringen. quasi die Hochglanzverlage,
zentralisiert für online-kurse mit videos und Drehbüchern.

Fortunatelly there already exist a myriad of different course plattforms that
want to ease the course development, such as Ilias, edX, Moodle, XXX noch mehr ....
And how is that kind of simplicity achieved, mostly by offering an integrated
editor that enable the user to write develop a course with a lot of buttons and
menues, sub-sub-menues and masks whos only intention is to hide non intuitive
syntax and semantics of programming languages that are interpreted machine in
order to display such a course ...

but this approach lacks in exchangeability, of course, system like ILIAS support SCORM (Sharable Content Object Reference Model), but who needs this standard if most of the other systems do not apply it.

**Requirements from an OpenSource perspective**

* versionierung different ressources of truth
* unterstützung von etwickler teams
* übersetzung
* darstellung in verschiedenen formaten
* integration verschiedener webtechnologien für visualiserung, etc.




Ilias edx und co … bieten zwar Masken zur Kurserstellung aber diese sind eher hinderlich und verlangen bei vielen sachen trotzdem dass man html benötigt, sonst ist man eingeschränkt

für viele Menschen scheint der Aufwand schwer ein online-kurs zu gestalten schwierigkeiten …




Frei? Wenn sich jemand die Mühe gemacht hat, dann kann der Kurs auch einfach heruntergeladen werden??? Eher nicht …

Standards SCORM

authoring tools?

Was ist besser als ein Text-Editor???

besser als code in sprachen zu entwickeln, die von computern verstanden werden
ist es sprachen zu entwickeln, die intentionales coding ermöglichern... der computer muss versuchen herauszufinden, was der mensch im sinne hat ...

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
