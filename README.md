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

für viele Menschen scheint der Aufwand schwer ein online-kurs zu gestalten schwierigkeiten …

Ilias edx und co … bieten zwar Masken zur Kurserstellung aber diese sind eher hinderlich und verlangen bei vielen sachen trotzdem dass man html benötigt, sonst ist man eingeschränkt

Frei? Wenn sich jemand die Mühe gemacht hat, dann kann der Kurs auch einfach heruntergeladen werden??? Eher nicht …

Standards SCORM (Sharable Content Object Reference Model)

authoring tools?

Was ist besser als ein Text-Editor???

A template is a set of styles and page layout settings that determine the appearance of a document. This template matches the printer settings that will be used in the proceeding and the CD-Rom. Use of the template is mandatory.
Clearly explain the nature of the problem, previous work, purpose, and contribution of the paper.
    2. How does it

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
