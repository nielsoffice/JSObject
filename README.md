# JSObject
Handling JavaScript Object loop and notation and method basic approach

```JS

  const niel = {
    
    firstName: 'Niel',
    lastName: 'Fernandez',
    Job: 'WordPress Developer'
    
    contract: function(dateHired) {    
      return 2025 - dateHired;
    }
    
    specialize: function() { 
     // "this" using that key word you can create another property or properties inside the method
      this.skill = ['JS', 'PHP', 'C++'];
      
      return this.skill;
      
    }

  }
   
  // dot notation
  console.log(niel.firstName);
  // bracket notation
  console.log(niel['firstName']);
  
  // loop the object data E6
  for (let [key, value] of Object.entries(niel)) { console.log(key, value); }

  // Loop the object data
  for (let key in niel) { console.log(key, niel[key]); }
  
  // invoke the method from Object JS 
  // using dot notation
  console.log(niel.contract(2022));
  
  // using bracket notation
  console.log(niel['contract'](2022));

```

Reference<br />
<a href="https://stackoverflow.com/questions/14379274/how-to-iterate-over-a-javascript-object">How to iterate over a JavaScript object</a><br />

<br />
-----------------------------------------------------------------------------------------------------------------------------------------------------------
<br />

Object Data 

```JS

 Object.keys
 Object.values
 Object.entries
 
 let Obj = {
  
   one : 'Christmas',
   two : 'New Year',
   three : 'Valentines'

 }

 // Object to String 
 Object.keys(Obj).forEach((key, index) => { console.log(key, Obj[key]); });

 // Object to String 
 Object.values(Obj).forEach((value) => { console.log(value); });
 
 // Arrays Of Data
 Object.entries(Obj).forEach( (value) => { console.log(value); });
 
```

```JS
// Console.log | result 

//  Object.keys
one Christmas
two New Year
three Valentines
-------------------------------
//  Object.values
Christmas
New Year
Valentines
-------------------------------
//  Object.entries
(2) ['one', 'Christmas']
    0: "one"
    1: "Christmas" 
    length: 2 
[[Prototype]]: Array(0)
(2) ['two', 'New Year']
(2) ['three', 'Valentines']
```

<br />
-----------------------------------------------------------------------------------------------------------------------------------------------------------
<br />

FALSY AND TRULY VALUES ! Long and shorthand version Checking.

```JS
// FALSY AND TRULY VALUES ! Long and shorthand version Checking.
 if(Obj.one) { 
  /* Is Obj having one property? */ 
  console.log(Obj.one);
 }
 // w/ OR condition 
 if(Obj.one || Obj.two) { 
  /* Is Obj having one property? */ 
   console.log(Obj.one || Obj.two);
 }
 // w/ && condition 
 if(Obj.one && Obj.two) { 
  /* Is Obj having one property? */ 
  console.log(Obj.one && Obj.two);
 }

 // SHORTHAND VERSION
 let objectData = Obj?.one?.two || 'now found'; 
 let objeData   = (Obj?.one?.two) && Obj?.three; 

 console.log(objectData);
 console.log(Obj?.three);
```

```JS
 Christmas
 Christmas
 New Year
 now found
 Valentines
```

<br />
-----------------------------------------------------------------------------------------------------------------------------------------------------------
<br />

<br />Object Litteral | Dynamic object properties


```JS
// Property             Value
// [`day-${ 1 + 5 }`] : { object: data }
console.log() | result : day-6 : { open: 11, close: 10 }

const weekdays = ['mon','tue','wed','thu','fri','sat','sun'];

const workingHours = {
  
  // Thursday
  [weekdays[3]] : {
    open : 12,
    close: 12,
  },
  // This means Friday !
  [weekdays[4]] : {
    open : 11,
    close: 10,
  },
  // This means "day-6"
  // pretend that the number 1 and 5 is dynamic value from third party object.
  [`day-${ 1 + 5 }`] : {
    open : 11,
    close: 10,
  }

};

console.log(workingHours);
```

```JS
// Console.log() | Result 
{thu: {…}, fri: {…}, day-6: {…}}
day-6 : 
  close : 10
  open : 11
  [[Prototype]] : Object
fri : {open: 11, close: 10}
thu : {open: 12, close: 12}
[[Prototype]] : Object
```
