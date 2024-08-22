# WHAT THE PROGRAM IS

This program is a calculator application with a web interface. It contains a form with a text input and buttons. The user can enter an equation into a text input. The calculator will parse and evaluate that equation. It will then clear the text input and return the result inside the text input. Users can enter the text input in two ways:

- directly from the keyboard. They will submit when they enter the equal sign key.
- by pressing buttons on the form which will add the corresponding key to the text form.

At the moment, the calculator should be able to support:
- addition
- subtraction
- multiplication
- division
- performing multiple operations at once\

# WEB DESIGN

## USER INTERFACE

The user interface of the application will be a white page that looks like a calculator. Users will type input into the input tab of the calculator. They will also be able to press buttons on the calculator. Output will be displayed in the input tab. A Canva design is presented below:

## CLIENT-SERVER ARCHITECTURE

The application will have a client and a server. The client will take user input and send it to the server. The server will parse and process user input (solve the expressions the user give the client either the result of the expression or an output an error if any expression is invalid). The client will display user output in the input tab of the calculator.

# COMPILER DESIGN

This program will use many techniques found in compiler design. Simply put, when web forms send messages to servers, they send them as strings. However to evaluate equations, we need to interpret them as a set of numbers and operations. To do this, we need to compile these strings using techniques such as lexing and parsign.

## LEXING

Lexing is a technique by which a string is broken up into tokens. It's also a good way to catch and handle errors. I will decide which inputs are valid and invalid. I want the program to accept the following inputs:

- number
- neg_sign, number
- number, operand, number, (operand, number) * n
- neg_sign, number, operand, number
- number, operand, neg_sign, number
- neg_sign, number, operand, neg_sign, number

I want the program to reject the following inputs:

- any input that doesn't end with a number
- any input that doesn't start with a number or a neg_sign
- any input with more than one operand in between numbers

To do this, I will design a DFA.

## PARSING

To make the calculator work, I will need to implement string parsing. For this, I will create a context free grammar as follows:

<expression> -> <number> | <number><operand><number> | <number><operand><expression>
<number> -> <digit> | <digit><digit> | <digit><number>
<digit> -> 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
<operand> -> + | - | * | /