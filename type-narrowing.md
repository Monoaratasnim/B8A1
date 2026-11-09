# Type Narrowing in TypeScript

## Introduction

In TypeScript, a variable can have more than one possible type. For example, sometimes we may receive a string or a number as input. But we cannot use the same operations for both types. Type narrowing helps us check the actual type of a value before using it. It makes our code safer and easier to understand.

## Detailed Explanation

One way to narrow a type is by using the `typeof` operator. It helps us check whether a value is a string or a number.

```ts
function checkValue(value: string | number): string {
  if (typeof value === "string") {
    return value.toUpperCase();
  }

  return value.toString();
}
```

Here, if the input is a string, it converts it to uppercase. If it is a number, it converts the number into a string.

Another way is using the `instanceof` operator. It checks whether an object belongs to a particular class.

```ts
class Student {
  name: string;

  constructor(name: string) {
    this.name = name;
  }
}

function showInfo(person: Student | Date): string {
  if (person instanceof Student) {
    return person.name;
  }

  return person.toDateString();
}
```

We can also use the `in` operator to check whether an object contains a particular property.

```ts
type Student = { name: string };
type Teacher = { subject: string };

function getDetails(person: Student | Teacher): string {
  if ("name" in person) {
    return person.name;
  }

  return person.subject;
}
```

In this example, TypeScript checks whether the object has a `name` property. If it does, it returns the name. Otherwise, it returns the subject.

## Conclusion

Type narrowing is an important feature of TypeScript. It helps us check different types of values and use them correctly. We can use `typeof` for basic types, `instanceof` for class objects and `in` for checking object properties. These methods help us write better and safer code.