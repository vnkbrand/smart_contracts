Project: Design and Develop a Smart Contract
Coursera - This is the 2nd course of the Coursera Blockchain Specialization Certificate. 

Project Description

Solidity Version Mandatory Reading

How to run?
Pre-requisites
Remix IDE
Web Browser
Desktop Application (Electron)
Passion for Next level of World Wide Web and its bright future ;)
Run
Open Remix IDE
copy code from Auction.sol
Compile and deploy
Done - You should be able to interact with the Smart Contract registering bidders, placing bids and revealing winners
Technology Stack
This project uses the following technologies:

Solidity v0.4.17

COURSE NOTES:

<!-- Smart Contract Basics -->

<!-- Week 1 -->

1. Why Smart Contracts?

Bitcoin added an embedded script - conditional feature that was bootstrapped as a softfork in Bitcoin.  It enabled simple conditional transfers.

A significant contribution of Ethereum is a working smart contract layer that supports any arbitrary code execution over the blockchain.

Smart contract allows for user-defined operations of arbitrary complexity.

This feature enhances the capability of Ethereum blockchain to be a powerful decentralized computing system.

Examples:
- Transfer on specific date.
- Credentials need to be provided.
- Need to deliver specific product for payment.

This introduces conditions, rules, policies beyond that of which a simple money transfer cryptocurrency protocols can handle.

2. Smart Contract Advantages
- Transfers assets other than value or crypto.
- Smart contract allows specification of rules for an operation on the blockchain.
- It facilitates implementation of policies for transfer of assets in a decentralized network. 
- It also adds programmability and intelligence to the blockchain.

A smart contract embeds function that can be invoked by messages that are like function calls.
These messages and the input parameters for a single message are specified in a transaction.

All the operations are transparent and are recorded on the blockchain.
Customers can directly access the tools without an intermediary like a bank.

3. Smart Contracts
Smart contract work with the application-specific semantics and constraints of the transaction and verify, validates, and executes them.

Once the code is deployed, it cannot be changed.

We will have to redeploy the code as a new smart contract, or somehow redirect the calls from a old contract to the new one.

Smart contract can store variables in it called state variables. We could retrieve how these variables change over the blocks.

VARIABLES:
1. pragma directive
2. name of the contract
3. data or the state variable that define the state of the contract
4. collection of function to carry out the intent of a smart contract

4. 3 Steps in the development of a smart contract
- Design
Greeter has a string variable named yourName, the constructor Greeter, a set function to set the name, and a hello function that returns a string name so that you can use it to greet the world.

- Code
Version of solidity. Name on contract. State variable. Functions. 

- Test
Remix is where we test. 

4. Smart Contracts - Compiling on Remix

ARTIFACTS AFTER COMPILATION:

ABI, Application Binary Interface - the interface schema for a transaction to invoke functions on the smart contract instance bytecode.

Contract bytecode - this is the bytecode that is executed for instantiating a smart contract on the EVM. Think of it like executing a constructor of a smart contract to create an object.

WebDeploy script -  json script to web application to invoke smart contract function AND script for programmatically deploying a smart contract from a web application.

Gas estimates - this provides a gas estimates for deploying the smart contract and for the function invocation.

Function hashes - first four byte of the function signatures to facilitate function invocation by a transaction.

Instance bytecode - the bytecode of the smart contract instance.

5. Deploying Smart Contracts

i. First, a smart contract solution is written in high-level language and compiled bytecode.

ii. An ABI is also generated for high-level language application. Example, Web Apps to interact with the binary smart contract. 

iii. The smart contract requires an address for itself so that transaction can target it for invocation of its function. The contract address is generated by hashing the sender's account address and its nonce. 

DEPLOYING A SMART CONTRACT USING THE REMIX IDE

1. Enter the smart contract code inn the IDE and Compile
2. Remix generates several artifacts
3. Remix provides us with the Web3 deployment script which contains a bytecode. Application Binary Interface, ABI, and account detail.
4. Deploy - execute script
5. Once the deployment is done, the address is generated by hashing creator's account number and nonce.
6. To interact with the smart contract, we'll use the smart contract address, ABI definition, and the function hashes.

<!-- WEEK 2 - SOLIDITY -->
Solidiy - It is specially designed to write smart contracts and to target the Ethereum Virtual Machine.

Smart contracts are like classes in OOP

SMART CONTRACT STRUCTURE

1. Data or state variables

2. Functions - Constructor (default or specified - ONLY ONE), Fallback function, View functions, Pure functions, Public functions, Private, Internal, External

3. User defined types in struct and enums

4. Events

FUNCTION DEFINITIONS

1. Function header, followed by the function code in {}

Function header can be as simple as an anonymous noname function to a complex function header loaded with a lot of details.
- function is key word
- parameters - any number of pairs type identifier

Function code contains the local data and statements to process the data and return the results of processing.

Any number of values can be returned, unlike common programming languages that allow only one return value. For example, multiple variables, age and gender, can be assigned return values from a function getAgeGender.

In summary, a smart contract for Ethereum can be specified using Solidity defined structure and functions. A variety of function types are provided for expressing smart contract operations. A smart contract in Solidity can inherit its attribute and functionality from another smart contract.

DATA TYPES AND STATEMENTS

1. Default modifier is private. You explicitly state the public modifier.
2. For every data declared public, accessor or getter function is automatically provided.

SPECIFIED DATA TYPES

Address
1. Address is a special Solidity define composite data type. It can hold a 20-byte ethereum address. Recall address is a reference address to access a smart contract.
2. Address data structure also contains the balance of the account in Wei. It also supports a function transfer, to transfer a value to a specific address.

Mapping
1. Mapping is a very versatile data structure that is similar to a key value store, it also can be thought of as a hash table.
2. The key is typically a secure hash of a simple Solidity data type such as address and the value in key-value pair can be any arbitrary type.

Message
1. Message is a complex data type specific to smart contract. It represents the call that can be used to invoke a function of a smart contract.
2. msg.sender that holds the address of the sender
3. msg.value that has the value in Wei sent by the sender. 

DATA STRUCTURES
The smart contract creator is the chairperson who gets a weight of two for her vote.

Others get a weightage of one for their one vote. 
***
"Voting"
Each voter has to be registered first by the chairperson before they can vote and can vote only once. A constant function is included to enable the client applications to call to obtain the result. The constant modifier of the function prevents it from changing any state of the smart contract. This call comes directly to the smart contract not via a transaction, so it is not recorded in the blockchain. It does not change state of contract, thus no need.
***
"Struct"
Struct is a composite data type of a group of related data that can be referenced by a single, meaningful, collective name.
Individual elements of the struct can be accessed using the dot notation.
Voter struct is used to define a mapping of address.
We could also add another data to the struct, say proposal name that is of string type. Set of proposals is represented by an array of proposals.
***
"Time units" - TIME IT WAS CONFIRMED!
In a blockchain application, all the participants and nodes have to synchronize to one universal time. For this purpose, blockchain proposals include a time server that serves the Unix Epoch time or time since January 1st 1970 in seconds.

This time is used in timestamping the block time. When a block is added to the blockchain, all the transaction confirmed by the block also have the same block time as their confirmation time.

A variable called "Now" defined by solidity, returns the block timestamp. This variable is often used for evaluating time related conditions.
****

"Enum"
Enum or enumerator data type, allows for user defined data types with limited set of meaningful values. It is mostly used for internal use and are not supported currently at the ABI level of solidity.

However, it serves an important purpose of defining states or phases of a smart contract.

ACCESS MODIFIERS AND APPLICATIONS

The main intent of smart contract transaction is to execute a function. 

However, smart contracts often require control over who are what can execute the function, at what time a function needs to be executed, what are the precondition to be met before getting access to the function?

Modifiers can change the behavior of a function. It is also known as a function modifier since it is specified at the entry to a function and executed before the execution of the function begins.

<!-- WEEK 3 -->

DEVELOPING SMART CONTRACTS
1. Define the Problem Statement
2. Analyze the problem
3. Use class diagram to represent design
4. Define the visibility for the state variables & functions
5. Define the access modifiers for the functions
6. Define validation for input variables of the functions
7. Define conditions that must hold true on completion of critical operations within functions
8. Declaratively express the conditions that were discovered in steps four to seven using access modifiers
9. Visibility modifiers require an assert classes

VALIDATION & TESTS

Solidity features a function revert that results in state-reverting exception. This exception handling will undo all the changes made to the state in the current call and reverses the transaction and also flags an error to the caller.

CLIENT APPLICATIONS

1. Events
A generic format is, event, name of the event, and parameters. For example, event votingCompleted.

Typically, an event feature is to indicate to a client application, user interface or a transaction monitor that a significant milestone has been reached. The application can listen to the events pushed, using a listener code, to track transactions, to receive results through parameters of the event, initiate a pull request to receive information from the smart contract.


<!-- WEEK 4 -->
Evaluating Smart Contracts
- Ensure a blockchain is relevant

- Most suitable for apps with:
1. Decentralied problems without intermediaries
2. Require validation, verification, recording of timestamped, immutable ledger
3. Autonomous ops guided by automatic rules and policies.
4. Visible to all participants on chain and executed on all full nodes
5. Need when you need consensus on all aspects
6. Not for single node computation

Designing Smart Contracts (I)
1. Keep simple - avoid errors
2. Variables to address problems - no redundancy
3. Make it auditable by making custom modifiers
4. Keep necessary data - BC is not for large data
5. Good practice to analyse app data and seperate to on and off-chain data (managed by higher-level apps)

Designing Smart Contracts (II)
1. Use appropriate data types, understand that Ethereum Virtual Machine, is a two 56-bit processor optimized for integer computations. (EXAMPLE) Instead of using a variable string name for the proposals, use an integer identification for the proposal.

2. Make sure you use the integer arithmetic for most of your computational needs.

3. All state variables are created as private. Any variable on the block chain is viewable to all, irrespective of the visibility modifier. You have to explicitly state that a variable is public. When a variable is declared public, Solidity compiler automatically creates a getter method to view the value of the variable. Internal to the contract, the variable is accessed as data, externally it is accessed as a function.

4. Maintain a standard order for different function types within a smart contract, according to their visibility as specified in Solidity docs. 

The recommended order for functions within a smart contract are; constructor, fallback function, external, public, internal, private. Within a grouping, plays the constant functions last.

5. Multiple modifiers that apply to a function, by specifying them in a white space separated list and are evaluated in the order presented. Hence, if the output of one modifier depends on the other, make sure you order them in the right sequence. For example, function buy, has three modifiers specified in the following order; payable, enoughMoney, item available.

6. Use modifier declarations for implementing rules. 

Use function access modifiers for; implementing rules, policies and regulations. 

Implementing common rules for all who may access a function, declaratively validating application specific conditions and providing auditable elements to allow verification of the correctness of a smart contract.

7. Events

Using events in smart contract. Use events to log important milestones, during the span of a smart contract execution especially long running ones.

Events can carry at most three index parameters that can be used efficiently for searching through the events in the block chain. 

8. NOW

Beware of "now" time variable. Now is the alias for block timestamp of the block indicating the universal time when the block and the transaction within it are mined and recorded. Variable now can be used for approximate elapsed time comparison, as we illustrated in the ballot example. However, it is not a good practice to use it for computation within the application logic.

9. Hashing

Use secure hashing for protecting data. Recall that hashing is a very important function in a block chain. Data in the block chain is viewable by all. This means that we may want to secure hash, to protect its visibility. Solidity provides a variety of built-in functions for standard secure hash functions. Keccak, SHA-256, RIPEMD-160 are Solidity functions available to use for hashing application data.

End of Course - Addendum
Some of the changes in the newer version of Solidity are in the syntax of the constructor and the event feature. Please

Keep the constructor to be “function Auction” instead of newer version “constructor”
Call an event by its name (say, eventName) rather than “emit eventName” of the newer version of Solidity. It is not difficult to move to the newer version after you complete the course projects with version 0.4.17. You just have to pay attention to the errors and read the documentation.

SUMMARY

Week One: Smart Contract Basics
Contract in the Ethereum Blockchain has:

Pragma directive
Name of the contract
Data or the state variables that define the state of the contract
Collection of functions to carry out the intent of a smart contract
Other items we will discuss in later lessons.
Remix is a web Integrated Development Environment (IDE) that creates, deploys, executes and explores the working of smart contracts on the Ethereum blockchain.

Two very simple smart contracts are:

Greeter
One integer storage: SimpleStorage
The 3 steps to developing a smart contract is:

Design
Code
Test
Remix Solidity compiler generates several artifacts such as:

Name of the contract
Bytecode executed for the contract “creation” on the EVM
ABI: Application Binary Interface, details functions, parameters and return value
Web3 deploy module that provides the script code for invoking the smart contract from a web application
Gas estimates for the execution of the function, and
Actual runtime bytecode of the smart contract
Smart contracts can be deployed from:

Remix IDE
Another smart contract
A command line interface
Another high level application
A web application.
Complete process of deployment using Remix IDE:

You enter the smart contract code in the Remix IDE and compile.
Remix generates several artifacts as discussed earlier and as shown in the picture.
For the ease of deployment, remix provides us with the web3 deployment script which contains byte code, Application Binary Interface (ABI), account details.
To deploy the smart contract we could just execute this script.
Once the deployment is done, the address is generated by hashing creator’s account number and nonce.
To interact with the smart contract we will use the smart contract address, the ABI definition, and the function hashes.
Week Two: Solidity
Detailed structure of a smart contract:

Data or state variables
2. Functions : There are several types of functions allowed

Constructor (default or user specified; only one, meaning it cannot be overloaded)
Fallback function (This is a powerful feature of an anonymous function that we will discuss in the best practices module later in this course.)
View functions
Pure functions (no state change, it computes and returns a value; example: math functions)
Public functions (accessible from outside thru transactions, state changes recorded on the bc)
Private functions (accessible only with the current contract)
Internal functions (accessible inside current contract and inherited contract)
External functions (can be accessed only from outside the smart contract)
3. User defined types in struct and enums

4. Modifiers

5. Events

“function” is a keyword at the beginning of all functions

Parameters are any number of pairs {type, identifier} . E.g. uint count

Return parameters: return values can be specified as pair {type, identifier} or just {type}. When only type is specified it has to be explicitly returned using a return statement.

If type and identifier are specified in the returns statement, any state change that happens to the identifier within the function is automatically returned.

Any number of values can be returned unlike common programming languages that allow only one return value. For example, multiple variables, age, gender can be assigned the return values from a function

1 Ether is 10^18 Wei.

Solidity is a high-level language that is a combination of Javascript, Java and C

The Bidder smart contract design contains three items:

Name of the contract
The data/states
The functions
“Address” is a special Solidity defined complex data type that can hold a 20 byte Ethereum address. Address is the base of a smart contract.

“Mapping” is a very versatile data structure that is similar to a <key, value> store. It can be thought of as a hash table.

“Message” is a complex data types specific to smart contract. It represents the call that can be used to invoke a function of a smart contract.

“Struct” is composite data type of a group of related data that can be referenced by a single meaningful collective name.

“enum” or enumerated data type allows for user-defined data types with limited set of meaningful values.

The main intent of a smart contract transaction is to execute a function.

You can think of a modifier as a gatekeeper protecting a function since it can change the behavior of a function

Week Three: Putting it all Together
Solidity features a function revert() that results in state-reverting exception.

This exception handling will undo all changes made to the state in the current call, and reverses the transaction and also flags an error to the caller.

An event feature is used to indicate to a client application (user interface or a transaction monitor) that a significant milestone has been reached.

A listener code can be used to:

Track transactions
Receive results through parameters of the events
Initiate a pull request to receive information from the smart contract.
The Chairperson is the creator of the smart contract. He/she will be the only person who can register the voters.

List of functions:

1. Constructor is a function that is called to create the smart contract. In Solidity, unlike a regular Object Oriented language, there can be only one constructor. Also, the constructor has the same name as the contract. The sender of the message invoking the constructor is the chairperson.

2. Register is a function to register the voter. Only the chairperson can register a voter. The Sender of the message for registration has to be the chairperson.

3. Vote is a function in which voters including the chairperson can vote for a proposal.

4. Winningproposal is the final function that determines the winning proposal and can be called by client applications.

Stage has four distinct stages: Init, reg, state, and done. The stage is initialized to init at the time of the deployment of the smart contract. Then, in the constructor, the init is changed to reg stage. After the registration period is over, the stage changes to vote. After the voting duration elapses, the stage is set to Done.

Week Four: Best Practices
Blockchain is not a solution for all applications. Make sure your application requirements need blockchain features

A blockchain solution is most suitable for applications with these characteristics:

Decentralized problems, meaning participants hold the assets and are not co-located,
involve peer-peer transactions without intermediaries,
operate beyond the boundaries of trust among unknown peers,
require validation, verification and recording on an universally timestamped immutable ledger
Autonomous operations guided by rules and policies
Make sure you need a smart contract on blockchain for your application.

Keep the smart contract code simple, coherent, and auditable.

Blockchain is not a data repository. Keep only the necessary data in the smart contract.

Make sure you use the integer arithmetic for most of your computational needs.

Maintain a standard order for the different function types within a smart contract, according to their visibility, as specified in Solidity docs.

The recommended order of functions within a smart contract are:

1. constructor

2. fallback function

3. external

4. public

5. internal

6. private

Within a grouping, place the constant functions last.

Use Solidity defined “payable” modifier when sending value

Pay attention to Order of Statements inside a function

Use Modifier Declarations for implementing rules

Using Events in Smart Contract

Use Secure hashing for protecting data

Download and print this document:

