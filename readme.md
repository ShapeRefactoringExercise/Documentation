<!-- GENERATED DOCUMENT DO NOT EDIT! -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->

<!-- Compiled with doculisp (version 2.2.0) https://www.npmjs.com/package/doculisp -->

# Shape Refactoring Exercise #

### A Refactoring Chew Toy ###

## Table of Contents ##

1. [Section: Note on Refactoring](#note-on-refactoring)
2. [Section: Introduction](#introduction)
3. [Section: Requirements](#requirements)
4. [Section: Definitions](#definitions)
5. [Section: Setup](#setup)
6. [Section: Run the tests](#run-the-tests)
7. [Section: Purpose of Code](#purpose-of-code)
8. [Section: Changes that need to be made](#changes-that-need-to-be-made)
9. [Section: Contributors](#contributors)
10. [Section: How to contribute](#how-to-contribute)
11. [Section: A Note on Tooling](#a-note-on-tooling)

## Note on Refactoring ##

_If_ you have to change a test to make a change work, you are not refactoring. You are instead rearchitecting. Now this code can benefit from a change to architecture but don't call it refactoring.

## Introduction ##

This is a different kind of refactoring exercise. Most code exercises have a specific answer and are designed to be solved within a couple of hours. This one is intended to have a large number of solutions and take more then 10 hours without completion.

The idea is to be an exercise that you can continuously go back to and see new things. This is not intended for someone who is new to "_test based refactoring_" but for those who are familiar with the process and want to stay sharp or want to dive deeper.

## Requirements ##

The requirements are for each exercise is in the language specific readme. Please look there to know more.

## Definitions ##

**Refactoring**: Throughout this exercise the word "refactoring" means changing structure _without_ changing external behavior.

## Setup ##

### Global Setup

You need [gittey](https://www.npmjs.com/package/gittey) installed globally.

`npm i gittey -g`

### Local Setup

In the directory for the exercise run:

`gittey setup`

### Supported Languages

- [TypeScript](https://github.com/ShapeRefactoringExercise/LanguageTypeScript)
- [C#](https://github.com/ShapeRefactoringExercise/LanguageCSharp)

## Run the tests ##

Thanks to Gittey running the tests looks the same. However please look at the language specific read me for how to run the tests.

## Purpose of Code ##

The code takes an array of points and returns an objects that represents the shape and some of its properties.

### Types of Shapes

- Empty
- Point
- Line Segment
- Triangle
- Rectangle
- Other

### Basic Shapes

#### Empty

The empty shape is a non-shape. It is formed from an empty array of points and has no properties except being an empty shape.

#### Point

The point shape is formed from an array containing a single point and has an X and Y.

### Line Segment

The line segment is formed from an array containing 2 points. It has both points as properties as well as length and slope.

### Triangle

The triangle is formed from an array with 4 points, the first and last are the same point forming a closed shape. The first 3 points are unique. It will have three line segments, formed from the three points: side A, side B, and side C with side A being formed from the first two points and consecutively from there.

It will have three angles, angle A, angle B, and angle C. Angle A, is opposite side A, angle B is opposite side B, and angle C is opposite side C. Each angle will be formed of two line segments that form the angle and have the degrees of the angle.

A triangle will also contain the area of the triangle.

### Rectangle

The rectangle is formed by an array of 5 points, the first and last are the same point forming a closed shape. The first 4 points are unique. A rectangle will contain 4 line segments, side A, side B, side C, and side D. Side A is formed from the first two points, and each side if formed consecutively from there. To be a rectangle the angle between any adjoining sides will be 90 degrees.

A rectangle will contain the area of the rectangle.

### Other

The other shape is formed by an array of points that do not make any other shape. It contains the points that formed it.

## Changes that need to be made ##

Now to make the refactoring more focused, we have two expected changes that need to happen. These are optional for the purpose of the exercise but help us have a goal in mind.

### A Bug

**Expected Behavior:**
If three points are on the same line they should be classified as a line segment between the two furthest points.

**Actual Behavior:**
The segment is classified as 'Other' and contains all points.

### New Feature

**Parallelogram**
If given 5 points that form a parallelogram, but not a rectangle the shape returned should be a parallelogram. The fifth point should be the same as the first forming a closed shape. Each of the other 4 points are unique.

A parallelogram has 4 line segments, side A, side B, side C and side D with side A being the first line segment and all other line segments being consecutive. It has for angles angle A, angle B, angle C and angle D, with angle A being the first angle, and all other angles being consecutive.

A parallelogram should have a height, a width, a perimeter, and a volume.

## Contributors ##

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/edf-re"><img src="https://avatars.githubusercontent.com/u/13739273?v=4?s=100" width="100px;" alt="EDF Renewables"/><br /><sub><b>EDF Renewables</b></sub></a><br /><a href="#financial-edf-re" title="Financial">💵</a></td>
      <td align="center" valign="top" width="14.28%"><a href="http://www.chrisstead.net/"><img src="https://avatars.githubusercontent.com/u/4184510?v=4?s=100" width="100px;" alt="Chris Stead"/><br /><sub><b>Chris Stead</b></sub></a><br /><a href="#tool-cmstead" title="Tools">🔧</a></td>
    </tr>
  </tbody>
</table>

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

## How to contribute ##

The guide to how to contribute is here: [How To Contribute](./contributing.md).

## A Note on Tooling ##

When developing this exercise I used two tools I want to call out. The first is ```Gittey```.

**[Gittey](https://www.npmjs.com/package/gittey)** is a free command automation that has understanding of git. It is used to help automate workflows. I have also used it to ensure a common feel between exercises of different languages.

**[Book Lisp](https://www.npmjs.com/package/booklisp)** is a mark down document generator that was used to build the document you are currently reading. Book Lisp allows me to break the document into smaller manageable chunks and then compile them into bigger documents.

Both of these tools were created and maintained by [Chris Stead](https://github.com/cmstead). I give him a due thanks for the work he puts into making developer lives easier.

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->
<!-- GENERATED DOCUMENT DO NOT EDIT! -->