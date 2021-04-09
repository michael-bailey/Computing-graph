# Rust
Rust is a multi-paradigm programming language that incorporates strict typing and memory management rules built into the language itself.

## Contents
- Features
	- Ownership
	- Borrowing
	- Lifetimes

## Features
Rusts main features are its memory and thread saftey which is built into the language itself in the form of borrowing, lifetimes.

### Ownership
This is the princible that data can only be 'owned' by one thing and once is is passed to something else the original variable no longer has access to the data.

### Borrowing
Borrowing comes into play when using references. a variable can be borrowed by getting a reference to it. any one variable can have many references or only one mutable reference. this prevents race conditions during compile time

### Lifetimes
This concept applies to values and references. a reference must not outlive its value, from this a reference has a lifetime that the rust compiler tracks during compile time and then flags it if the original value deallocates.

### Pattern Matching
Rust utilises pattern matching to compare and store values extensivley. One of the main ways this is used is in the results enum and the option enum. 

The results enum encodes two values, an ok value; where it returned without problem, an data err value where an error occured using pattern matching with if statements or the match block you can control execution without the potential of crashing. it also means that errors should be explicitly handled. 

The option type replaces null by forcing the programmer to handle none variables as a value, this removes the possibility of null pointers and uninitalised vaiables.