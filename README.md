# Makefile Examples
---
title: Makefile Examples
author: Fengyi Liu
date: 2024-12-24
---
Github: [https://github.com/lucasliu2019/makefile](https://github.com/lucasliu2019/makefile/)



We create some simple examples for Makefile. Makefile helps automate the compilation process!


## Requirement
Required tools:
- make


# How to compile
Go to the project folder using the 'cd' command in the terminal. Once, we are in the project folder, Type the following command will compile and give an executable file.
```
make
```

## Makefile
We will briefly explain some syntax of makefile.
### variable
The following line creates a variable called varName and assigns a value with varValue.
```
varName = varValue
```
To use the variable, we use the following syntax
```
${varName}
````
In the above line, it will substitute ${varName} with the assigned value (varName) to the varName.

### Rule and Dependency
The rule(target) is defined using the following syntax.
```
rulename: condition
```
Once we have rules, we can define what to be executed when the condition(prerequisites or dependency) is met.
```
 targets: prerequisites
	command
	command
	command
```
#### Special Rule Clean
```
clean:
```
This rule never runs unless we type make clean! We sometime to put .PHONY before the clean rule to prevent Make from confusing the target with a file name.

### Execution order
 When typing 'make', the 1st rule will be executed. If the condition file does not meet (the file does not exist), then it will run the prerequisites rule, i.e., go to the rule on how to create the files required in the prerequisites.  It does recursively until it reaches the rule that dependency is met!

### Wild Card
Given the following rule, we can use a wild card in the command to reference targets or prerequisites.
```
 targets: prerequisites
	command
	command
	command
```
Special variable: 
- $^: all prerequisites,
- $? all prerequisite newer
- $< first prerequisite
- $@ target name

