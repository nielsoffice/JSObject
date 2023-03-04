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
