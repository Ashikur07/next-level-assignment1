## 1. What is the use of the keyof keyword in TypeScript?

The keyof keyword is used to get a **union of the keys** of a given object type. It helps ensure type safety by restricting inputs to only the existing property names of that object. This is especially useful when writing generic functions that work with object properties.

### Example:
```
type User = {
  name: string;
  age: number;
};

type UserKeys = keyof User; // "name" | "age"

function getValue(obj: User, key: UserKeys) {
  return obj[key];
}

const user: User = { name: "John", age: 25 };
console.log(getValue(user, "name")); // Output: John
```


## 2. Provide an example of using union and intersection types in TypeScript?

In TypeScript, union and intersection types allow us to compose types in powerful ways.

- A **union type** (`|`) means a value can be any one of several types.
- An **intersection type** (`&`) combines multiple types into one that includes all their properties.


### Union Type Example:

```
type Status = "success" | "error" | "loading";

function showStatus(status: Status) {
  console.log(`Status is: ${status}`);
}

showStatus("success");
showStatus("loading");
```

### Intersection Type Example:
```
type Person = {
  name: string;
};

type Employee = {
  employeeId: number;
};

type Staff = Person & Employee;

const staffMember: Staff = {
  name: "Alice",
  employeeId: 101,
};
```



