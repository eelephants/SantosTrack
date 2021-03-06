#Iterator Pattern

> The essence of the Iterator Pattern is to Provide a way to access the elements of an aggregate object sequentially without exposing its underlying representation.

```javaScript
function Iterator(arr) {
  var currentPosition = -1;
  
  return {
     hasNext:function() {
       return currentPosition+1 < arr.length;
     },
     next: function() {
        if(!this.hasNext())
           return null;
        currentPosition++;
        return arr[currentPosition];
     }
  }
}

// Example Usage
var people = [{id:1,name:'John'}, {id:2,name:'George'}, {id:3,name:'Guy'}];
var peopleIterator = Iterator(people); // Create Iterator for 'people'
while(peopleIterator.hasNext()) {
	var person = peopleIterator.next();
	console.log(person.name + '\'s id is: ' + person.id + '!');
}

// John's id is: 1!
// George's id is: 2!
// Guy's id is: 3!
```

##### Reference
[7 JavaScript Design Patterns Every Developer Should Know](https://javascript.plainenglish.io/7-javascript-design-patterns-every-developer-should-know-df9c40e7debf)