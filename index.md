---
name: Alan Hynes
id: G00400498
tags: cpp coding project
categories: demo
---

# A Modern C++ Digital Rain Project

## Introduction

This is my Digital Rain Project! This project is a modern C++ implementation of the "digital rain" effect popularised by film The Matrix. The application creates a variety of characters falling down the terminal screen, with customisable features like color schemes, character sets, and animation density.

In this blog, I will document my journey developing this project, focusing on software design, algorithm development, problem-solving approaches, and modern C++ insights. I will share key code snippets and design decisions that showcase my understanding of C++ programming principles.

## Design & Test

### Architecture Overview

The project follows an object-oriented design with clear separation. I structured the code into three main components:

1. **MatrixColumn**: Represents a column of falling characters
2. **TerminalInterface**: Handles console terminal
3. **DigitalRain**: Runs the overall application

This approach allows for better maintainability and testing. Each component has a single responsibility, making the code easier to understand and iterate.

### Class Relationships

Here's a diagram of how the classes interact:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/ClassRelationships.png?raw=true" alt="Digital Rain Class Relationships" width="400"/>

### Unit Testing

I performed unit tests for the MatrixColumn class to ensure its core functionality works correctly. Here is a snippet:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/UnitTest.png?raw=true" alt="Digital Rain Unit Test" width="400"/>

These tests make sure each columns are created and updated correctly and produce the right brightness values.

## Terminal Running
<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/DigitalRainGif.gif?raw=true" alt="Digital Rain Animation" width="600"/>

 
