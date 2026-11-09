# Type Aliases vs. Interfaces in TypeScript

## Introduction

In TypeScript, we use types to define what kind of data a variable can store. Type aliases and interfaces are two ways to define the structure of data. They look quite similar, but they have some differences. Let's understand them with simple examples.

## Detailed Explanation

An interface is mostly used to describe the properties of an object. For example, if we want to store student information, we can write:

```ts
interface Student {
  name: string;
  age: number;
}
```

Here, every Student object should have a name and an age. We can also extend an interface to add more properties.

```ts
interface CollegeStudent extends Student {
  department: string;
}
```

Now, CollegeStudent has all the properties of Student, along with a department.
We can create the same kind of object using a type alias.

```ts
type Course = {
  title: string;
  duration: number;
};
```

But type aliases can do more than just describe objects. We can also use them for union types and tuples.

```ts
type Result = "Pass" | "Fail";
type Coordinate = [number, number];
```

One more difference is that interfaces support declaration merging. This means we can declare the same interface more than once and TypeScript combines their properties.

```ts
interface User {
  name: string;
}

interface User {
  age: number;
}
```

Now, the User interface contains both name and age. Type aliases do not support this feature.

## Conclusion

Both type aliases and interfaces are useful in TypeScript. I would use interfaces when working with objects and when I need to extend their structure. For union types, tuples and other types, I would prefer type aliases. We can choose either one depending on what we need in our code.