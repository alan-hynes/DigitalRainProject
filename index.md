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

## Algorithm

### Character Generation and Movement

The main algorithm of the Digital Rain effect involves generating random characters and creating the illusion of movement. Each column works independently, with characters falling at different speeds.

The `MatrixColumn` class manages this behaviour:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/MatrixColumnClass.png?raw=true" alt="Matrix Column Class" width="400"/>

This algorithm:
1. Adds a new random character to the end of the column
2. Removes the oldest character if the column exceeds its maximum length
3. Updates the "head" position to create the illusion of movement

### Random Character Generation

To create different patterns, I used multiple character sets:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/RandomCharacterGeneration.png?raw=true" alt="Random Number Generation" width="400"/>

This function uses C++11's random number generation to create different types of characters based on the selected character set (Katakana, Latin, Symbols).

### Visual Effects

To create the "trailing" effect, I implemented a brightness system where characters have different brightness levels based on their position relative to the "head":

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/Brightness.png?raw=true" alt="Brightness" width="400"/>

Here is the terminal showing the brightness levels:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/BrightnessTerminal.png?raw=true" alt="Brightness Terminal" width="400"/>

## Problem-solving

### Console Rendering Challenges
It was challenging to render Unicode characters in the Windows console. I needed to ensure the characters displayed properly while maintaining good performance.

To solve this I:

1. Used the Windows Console API directly through the `TerminalInterface` class
2. Set the console to use UTF-8 encoding
3. Implemented cursor movement and character rendering

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/ConsoleRenderingChallenge.png?raw=true" alt="Console Rendering Challenges" width="400"/>

### Performance Optimisation
I needed to optimise the rendering loop to maintain smooth animation. I implemented frame rate control to ensure that the animation speed was consistent:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/PerformanceOptimisation.png?raw=true" alt="Performance Optimisation" width="400"/>

With this approach, the animation runs at a consistent speed regardless of how quickly the update and render operations complete.

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/FPSTerminal.png?raw=true" alt="FPS on Terminal" width="400"/>

## Modern C++ Insight & Reflection

### Smart Random Number Generation
Instead of using the older C-style rand() function, I used C++11's random number generation:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/SmartNumberGen.png?raw=true" alt="Smart Number Generation" width="400"/>

This provides better statistical properties and more control.

### Chrono Library for Timing

For the FPS calculation, I used the `<chrono>` library instead of timing functions:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/FPSCalc.png?raw=true" alt="FPS Calculation" width="400"/>

This makes the code more portable and safe for time units.

### Range-based For Loops

I used range-based for loops introduced in C++11:

<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/RangebasedForLoops.png?raw=true" alt="Range-based For Loops" width="400"/>

This syntax is more concise and less prone to errors than traditional loops.

### Final Reflections

Developing this Digital Rain project has been a valuable learning experience. I have a deeper understanding of:

1. Object-oriented design principles in C++
2. Modern C++ features and best practices
3. Console application development
4. Animation and visual effects algorithms

The modular architecture I implemented allows for easy extension. Future enhancements could include:
- More character sets and color schemes
- Customisable animation patterns
- GUI version using a graphics library
- Saving and loading configuration settings

Overall, this project has strengthened my C++ programming skills and given me practical experience in developing a complete application from design to implementation.

## Terminal Running
<img src="https://github.com/alan-hynes/DigitalRainProject/blob/main/docs/assets/images/DigitalRainGif.gif?raw=true" alt="Digital Rain Animation" width="600"/>


 
