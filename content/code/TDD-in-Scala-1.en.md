+++
title = "TDD in Scala - 1, tasking and base UT"
+++

## Set-up a basic Scala project by using sbt

Assuming all prerequisites have been installed in your machine, in my case, they are: JDK8, Scala 2.12.8, SBT 1.3.3, and IDEA.

Create a new project in IDEA named `tdd_with_example`. 

Add a `build.sbt` file to the root path of project with the content as
```
ThisBuild / scalaVersion := "2.12.8"

ThisBuild / organization := "com.example"

lazy val tdd_with_example = (project in file("."))
  .settings(
    name := "tdd_with_example",
    libraryDependencies += "org.scalatest" %% "scalatest" % "3.2.3" % Test
  )

```

Make sure all of the dependencies are already getting done in your project.


## Tasking

Referring to the book <i>Test-Driven Development By Example</i>, we are now having two basic tasks

* $5 + 10 CHF = $10 if rate is 2:1
* $5 * 2 = $10

The second one is much easier than top one, so we would like to implement it. So let's mark it bold.

* $5 + 10 CHF = $10 if rate is 2:1
* <b>$5 * 2 = $10</b>


## First Test Case

Do not forget the rhythm of TDD

- Write a test (Even it cannot compile)
- Make it pass compile
- Run the test (Definitely it returns wrong, no worry)
- Make test correct (By write production code)
- Remove duplication between test and production code

Now, coding time. Let's have our first scala class in test. 

``` Scala
package com.example

import org.scalatest.matchers.should.Matchers
import org.scalatest.wordspec.AnyWordSpec

class MultiplicationSpec extends AnyWordSpec with Matchers {

  "Multiplication Spec" should {
    "Do multiplication" in {
      val five: Dollar = Dollar(5)
      five.times(2) shouldEqual 10
    }
  }
}

```

Certainly, we get compile error here, the class Dollar doesn't exist, let alone its member variables and methods. We should fix them very quickly by several times of type in.

Now we have production code: `class Dollar`

``` Scala
package com.example

case class Dollar(amount: Int) {
  
  def times(i: Int): Int = amount

}
```

So, where are we now? Back to the rhythm and cross some items off
- ~~Write a test (Even it cannot compile)~~
- ~~Make it pass compile~~
- ~~Run the test (Definitely it returns wrong, no worry)~~
- Make test correct (By write production code)
- Remove duplication between test and production code

Looks we need to let the test pass. I have the fastest magic to let the bar turn green, just as following

``` Scala
package com.example

case class Dollar(amount: Int) {

  def times(i: Int): Int = 10

}
```

Awesome! But wait, wait a moment. Something must be wrong, hard code doesn't make any sense, right?

But how to reveal the problem? We need another test case from a different direction. This kind of methodology called <b>Triangulation</b>.

Let's add one assertion to our test code: `five.times(3) shouldEqual 15`. And it will reveal the reality to us, that is, hard code cannot help us deal with changing scenarios.

So moving on `Make test correct (By write production code)`, we have to consider the real implementation. In this case, it's easy to work out. 

``` Scala
package com.example

case class Dollar(amount: Int) {

  def times(i: Int): Int = amount * i

}

```

## Review the rhythm

- ~~Write a test (Even it cannot compile)~~
- ~~Make it pass compile~~
- ~~Run the test (Definitely it returns wrong, no worry)~~
- ~~Make test correct (By write production code)~~
- Remove duplication between test and production code

Does there any duplication between test and production code? Looks no, we eliminated them by reducing hard code.

So now we finish our first cycle of TDD. Commit our change to Github and prepare for the next one.
