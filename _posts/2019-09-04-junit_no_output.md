---
layout: post
title:  "JUnit no output in vscode"
date:   2019-09-04 12:23:55 +0200
---
## When run test in vscode in learning taming text, there is no output
**Potential cause**  It may due to the in the BeforeClass, there is checking to check whether openNLP model exists in the folder, and due to previous open the project at parent level, which result in the path can not been found, but strangely, the exception is not captured by the vscode test runner, but stop the major test to run

