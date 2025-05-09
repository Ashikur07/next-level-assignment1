## 1. What is the use of the keyof keyword in TypeScript?

The keyof keyword is used to get a **union of the keys** of a given object type. It helps ensure type safety by restricting inputs to only the existing property names of that object. This is especially useful when writing generic functions that work with object properties.

### Example:

```ts
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


