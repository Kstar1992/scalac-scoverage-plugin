scales
======

Scales is a free Apache licensed code coverage tool for scala that offers statement and branch coverage.
Scales is available for both maven and sbt.

### Statement Coverage

In traditional code coverage tools, line coverage has been the main metric. 
This is fine for languages such as Java which are very verbose and very rarely have more than one
statement per line, and more usually have one statement spread across multiple lines.

In powerful, expressive languages like Scala, quite often multiple statements, or even branches
are included on a single line, eg a very simple example:

```
val status = if (age < 18) "No beer" else "Beer for you"
```

If you had a unit test that ran through the value 18 you would get 100% line coverage
yet you only have 50% statement coverage.

Let's expand this example out to be multifacted, albeit somewhat contrived:

```
val status = if (religion == "Pentecostalist") "Beer forbidden" else if (age < 18) "Underage" else "Beer for you"
```

Now we would get 100% code coverage for passing in the values ("Buddist", 34).

That's why in Scales we focus on statement coverage, and don't even include line coverage as a metric.
This is a paradigm shift that we hope will take hold.

### How to use

This project is the base functionality for instrumenting code via a scalac plugin. To actually use Scales in your
project you will need to use one of the build plugins:

* [maven-scales-plugin](https://github.com/scala-scales/maven-scales-plugin)
* [sbt-scales](https://github.com/scala-scales/sbt-scales)

### Alternatives

There are still only a few code coverage tools for Scala.

* [SCCT](https://github.com/SCCT/scct) - Offers line coverage
* [Jacoco4sbt](https://github.com/sbt/jacoco4sbt) - Instruments bytecode

## License
```
This software is licensed under the Apache 2 license, quoted below.

Copyright 2013 Stephen Samuel

Licensed under the Apache License, Version 2.0 (the "License"); you may not
use this file except in compliance with the License. You may obtain a copy of
the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS, WITHOUT
WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the
License for the specific language governing permissions and limitations under
the License.
```
