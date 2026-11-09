# Type Hierarchy in TypeScript

TypeScript's type-system follows a certain order or a  special hierarchy . There are types  at the top hierarchy and the bottom of hierarchy ; unknown , any and never are among them .

## never : The Bottom Type

In this type hierarchy never is a <br bottom type>  which does not has any real value . For example it is such a function which always throws expression or gets stuck in an infinite loop . 

```typescript
function  throwError(message: string): never{
    throw new Error(message) ;
}

function infiniteLoop(): never {
    while(true) {

    }
}
```

Now let's dive into the <br Top Types>

## unknown : The Tope Type

unknown stays at the peak of type-system. So any data type can be assigned. 

```typescript
let value: unknown = "hello world" ;
value.toUpperCase() ; //Error: cannot be used without type check
if (typeof value ==="string"){
    value.toUpperCase() ;
}
```

## any : A hole in Type Safety 
On the other side , any breaks the hierarchy . It behaves like both top and bottom type simultaneously  ; which stops the type-checking .

```typescript
let value: any = 2026 ;
value.toUpperCase() ; // compiles but crashes at runtime

```

## unknown is always preferred over any.But why?
In this point we can understand why developers pick unknown . Because when we use any , the compiler turns of all check ; which will cause runtime crash eventually.
On the other hand , unknown is type-safe.Because it cannot be accessed without type checking or type narrowing .

unknown can store any value but it force to verify before use. any on the other hand removes the protection.