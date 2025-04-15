# sasLang

sasLang is a Meta Attack Language (MAL) for Substation Automation Systems (SAS). The language is an extension of coreLang and icsLang found at https://github.com/mal-lang. 

# Current compiler
The language can be compiled with the malc compiler for MAL-based languages: [https://github.com/mal-lang/malc](https://github.com/mal-lang/malc). 
The MAL toolbox can be used for creating MAL models and attack graphs: [https://github.com/mal-lang/malc.](https://github.com/mal-lang/mal-toolbox) Please see the mal-toolbox tutorial for more information: [https://github.com/mal-lang/mal-toolbox-tutorial](https://github.com/mal-lang/mal-toolbox-tutorial).

# Previous compiler
The following are the instructions of how to compile sasLang with a previous compiler.
This project has the following structure:

* The file `pom.xml` is a Maven configuration file of the project.
* The directory `src/main/mal` contains the MAL specification
  `sasLang.mal`, which is the MAL specification of sasLang.
* The directory `src/main/resources/icons` contains SVG icons for the
  assets in sasLang.
* The directory `src/test/java/org/mal_lang/saslang/test`
  contains the unit tests of sasLang.

## Apache Maven

[Apache Maven](https://maven.apache.org/) is a build tool and
dependency management tool for Java projects. You can read more about
Maven at <https://en.wikipedia.org/wiki/Apache_Maven>. Follow the
instructions at <https://maven.apache.org/download.cgi> to download
Maven, and follow the instructions at
<https://maven.apache.org/install.html> to install Maven.

## Building sasLang and running the unit tests

The
[MAL compiler](https://github.com/meta-attack-language/malcompiler)
compiles MAL specifications (`.mal` files) into different formats,
using different backends. The reference backend generates Java code
that is suitable for testing purposes and evaluating your language.

### Building with the reference backend and running the unit tests

To compile sasLang with the reference backend of the MAL compiler
and then run the unit tests, execute the following command from the
`sasLang` directory:

```
mvn test
```

This will invoke the MAL compiler's reference backend to generate
`.java` files under `target/generated-test-sources`. These `.java`
files and the unit tests in `src/test/java` will then be compiled
into `.class` files under `target/test-classes`. The unit tests will
then finally be executed.

To only compile sasLang into `.java` files, execute the following
command:

```
mvn generate-test-sources
```

To compile sasLang into `.java` files and then compile these
`.java` files and the unit tests in `src/test/java` into `.class`
files, execute the following command:

```
mvn test-compile
```

To run a specific test class, execute the following command:

```
mvn test -Dtest=TestsasLang
```

Where `TestsasLang` is the test class.

To run a specific test method in a test class, execute the following
command:

```
mvn test -Dtest=TestsasLang#TEST
```

Where `TestsasLang` is the test class and `TEST` is the
test method.

## License

Copyright © 2020 sasLang contributors

All files distributed in the sasLang project are licensed under the [Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0).
See [`LICENSE`](LICENSE) and [`NOTICE`](NOTICE) for details.

- - - -
This is a project run by the [Software Systems Architecture and Security reseach
group](https://www.kth.se/nse/research/software-systems-architecture-and-security/)
within the [Division of Network and Systems Engineering](https://kth.se/nse) at
the Department of Computer Science at the School of [Electrical Engineering and
Computer Science](https://www.kth.se/en/eecs) @ [KTH university](https://www.kth.se).

For more of our projects, see the [SSAS page at
github.com](https://github.com/KTH-SSAS).
