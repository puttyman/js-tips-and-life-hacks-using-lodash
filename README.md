# Javascript tips and life hacks with lodash

### Retriving a value from a nested object using [_.get()](https://lodash.com/docs/4.17.4#get)
Given the following object:
```javascript
let request = {
  person: {
    address: {
      postcode: '3000'
    }
  }
}
```

**Avoid:**
```javascript
var postcode = 3000; // default postcode
if(request && request.person && request.person.address && request.person.address.postcode) {
    postcode = request.person.address.postcode;
}
```

**Do:**
```javascript
var postcode = _.get(request, 'person.address.postcode', 3000);
```

### Checking if object has a set of keys using _.has()

Given:
```javascript
let person = {
    address: {},
    age: 100,
    weight: 77,
    name: 'Tom',
    skills: ['js', 'java', 'c++']
  }
```

**Avoid:**
```javascript
if(person.address && person.age && person.weight && person.name) {
    person.save();
}
```

**Do:**
```javascript
if(_.has(person, ['address', 'age', 'weight']) {
    person.save();
}
```


