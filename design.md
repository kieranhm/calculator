# WHAT THE PROGRAM IS

This program is a calculator application with a web interface. It contains a form with a text input and buttons. The user can enter an equation into a text input. The calculator will parse and evaluate that equation. It will then clear the text input and return the result inside the text input. Users can enter the text input in two ways:

- directly from the keyboard. They will submit when they enter the equal sign key.
- by pressing buttons on the form which will add the corresponding key to the text form.

At the moment, the calculator should be able to support:
- addition
- subtraction
- multiplication
- division
- performing multiple operations at once

# IMPLEMENTATION

## USER INTERFACE

The user interface of the application will be a white page that looks like a calculator. Users will type input into the input tab of the calculator. They will also be able to press buttons on the calculator. Output will be displayed in the input tab. A Canva design is presented below:

## CLIENT-SERVER ARCHITECTURE

The application will have a client and a server. The client will take user input and send it to the server. The server will parse and process user input (solve the expressions the user give the client either the result of the expression or an output an error if any expressoin is invalid). The client will display user output in the input tab of the calculator.

## PARSING

To make the calculator work, I will need to implement string parsing. For this, I will create a context free grammar as follows:

<expression> -> <number> | <number><operand><number> | <number><operand><expression>
<number> -> <digit> | <digit><digit> | <digit><number>
<digit> -> 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
<operand> -> + | - | * | /