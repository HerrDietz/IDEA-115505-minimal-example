# Read me

This is a minimal example for [IDEA-175469](https://youtrack.jetbrains.com/issue/IDEA-175469).

## Expected behavior

A profile from the projects root pom should be activated automatically if a file 
`src/main/resources/important-file.txt` is present. This profile should copy an arbitrary file 
from a dependency to the output directory (using wicket as an example is only due to my lazyness,
it could be any dependency).

This file needed for activation is present in the root module. It is not present in the submodule 
`maven-submodule`. 

## Behavior using plain maven

Running `mvn clean generate-resources` copies the file only for the root project. As expected.

## Behavior using IntelliJ

Using the IntelliJ-Button "Generate Sources and Update Folders For All Projects" is expected to 
behave the same way as maven. But the file is copied for both modules. 
