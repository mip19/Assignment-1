# Type Narrowing 

in typescript a vairable can store different types ; such as string | number . In such cases. using method can reopot error. Type narrowing is the process where typescript checks condition and reduces broad type to specific one. It ensures the type safety and avoids any error .

## Type Narrowing with typeof operator 

For primitive types , typeof is best tool.

```typescript  
function pirnt(value:string| number){
    if(typeof value ==="string"){
        console.log(value.toUpperCase()) ;
    }
    else {
        console.log(value*2) ;
    }
}
```
## Type Narrowing with instanceof operator

It is used to check whether a value is an instance of a class or constructor

```typescript 
class Cat {
    meow(){
        console.log("Meooowww!!!") ;
    }
}

class Dog {
    gheu(){
        console.log("Gheeuuu!!")
    }
}

function sound(animal:Cat | Dog){
    if(animal instanceof Cat){
        animal.meow() ;
    }
    else {
        animal.gheu() ;
    }
}
```

## Type Narrowing with in operator
in operator checks whether an object has a particular property. It works for differentiating between union object types. 

```typescript
interface Admin {
    name: string ;
    role: string ;
}
interface User {
    name : string ;
}

function checkAccessPerson(person : Admin | User){
    if("role" in person){
        console.log(`Admin role: ${person.role}`)
    }
    else {
        console.lof(`Regular user: ${person.name}`)
    }
}
```

Type narrowing makes typescript efficient and error free .It is the ket of type safety