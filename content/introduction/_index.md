+++
title = "Introduction"

sort_by = "weight"
weight = 1
+++

# CS 5744: Software Design and Quality
## Project 1
Created by:
* Matthew Averyt
* Andrew Ferrin
* Matthew Harrington
* Matthew Newcomer

```java
public static void main(String[] args){
    int x = 0;
    for(int index = 0; index < 10; index++){
        x *= 2;
    }
    // Why left shift when you can loop?
    System.out.println(x);
}
```