# Calculating with Functions


This time we want to write calculations using functions and get the results. Let's have a look at some examples:

![image](https://user-images.githubusercontent.com/23621801/183771128-7817b9b6-e1b8-4e29-b36f-db7efdb76567.png)


### Requirements:

* There must be a function for each number from 0 ("zero") to 9 ("nine")
* There must be a function for each of the following mathematical operations: plus, minus, times, dividedBy
* Each calculation consist of exactly one operation and two numbers
* The most outer function represents the left operand, the most inner function represents the right operand
* Division should be integer division. For example, this should return 2, not 2.666666...:


![image](https://user-images.githubusercontent.com/23621801/183771242-615f7915-6c08-4981-9679-cd6f883309f7.png)


```js

function zero(value) {
  return generalAction('0', value);  
}

function generalAction(currentSign, value){
  if(value === undefined){
    return currentSign;
  }
  if(value.length === 1){
    return currentSign + value;
  }
  if(value.length === 2){
    return calculate(currentSign + value);
  }
}

function calculate(value){
  let aValue = value.split('');
  let result = 0;
  let firstOperand = parseInt(aValue[0]);
  let secondOperand = parseInt(aValue[2]);
  let operation = aValue[1];
  switch(operation){
      case '+':
      result = firstOperand + secondOperand;
      break;
      case '-':
      result = firstOperand - secondOperand;
      break;
      case '*':
      result = firstOperand * secondOperand;
      break;
      case '/':
      result = parseInt(firstOperand / secondOperand);
      break;
  }
  return result;
}

function one(value) {
  return generalAction('1', value); 
}
function two(value) {
  return generalAction('2', value); 
}
function three(value) {
  return generalAction('3', value); 
}
function four(value) {
  return generalAction('4', value); 
}
function five(value) {
  return generalAction('5', value); 
}
function six(value) {
  return generalAction('6', value); 
}
function seven(value) {
  return generalAction('7', value); 
}
function eight(value) {
  return generalAction('8', value); 
}
function nine(value) {
  return generalAction('9', value); 
}

function plus(value) {
  return generalAction('+', value); 
}
function minus(value) {
  return generalAction('-', value); 
}
function times(value) {
  return generalAction('*', value); 
}
function dividedBy(value) {
  return generalAction('/', value); 
}

```
