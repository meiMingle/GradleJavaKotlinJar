# GradleJavaKotlinJar

Here is a sample gradle project mixing java+kotlin exporting a runnable jar.

## Bonuses

* The git version is available from the code
* Log4j
* resources access

## Compiling

* UNIX-like (Linux, MacOS X, ...) : ```./gradlew build```
* Windows : ```gradlew.bat build```

results :

| File                              | Description                                                                  |
|-----------------------------------|------------------------------------------------------------------------------|
| `build/GradleJavaKotlinJar-dev.jar`          | The latest build of the jar, constant name, useful for testing.   |
| `build/libs/GradleJavaKotlinJar-VERSION.jar` | The same file with a [versioned](#Version) name.                  |

:bulb: The jar name and main class can be changed in `build.gradle`

```groovy
def name = 'GradleJavaKotlinJar'  // <- Will change the .jar name
def main = 'org.pignat.demo.Main' // <- Main class name
```

## Running

* ```gradle run```

## Version

The version number used in the file name and available using `Version.string()` is generated by inspecting the git
state (see [com.palantir.git-version](https://github.com/palantir/gradle-git-version) for details).

Here is an example : 1.5.7-3-g2aabbbf.dirty

* 1.5.7 is the last tag
* -3- we are 3 commits after the tag
* g2aabbbf : git short hash
* .dirty : some changes are not committed

## How to release (and have a nice version number)

0. git commit
0. git tag -a MAJOR.MINOR.SUB -m "tag vMAJOR.MINOR.SUB"
0. git push origin MAJOR.MINOR.SUB
0. [compile](#Compiling)
