# Interview Questions - Blog Task added

## TypeScript Made Easy: Enums, Type Inference, and More

Hey there! TypeScript is like JavaScript but with extra tools to make coding easier and less messy. It helps you catch mistakes and keep your projects organized. In this blog, I’ll explain four cool TypeScript features: **enums**, **type inference**, **how it improves code quality**, and **union/intersection types**. I’ll keep it simple, clear, and fun, like your favorite tech blogs. Let’s get started!

## 1. What Are Enums in TypeScript?

Enums let you create a list of named values. They’re great when you have a set of options that don’t change, like colors, sizes, or statuses. Enums make your code easier to read and stop you from using wrong values.

### Why Are Enums Helpful?

- **Easy to Read**: Names like `High` or `Done` are clearer than numbers or random words.
- **Safe**: You can only use the values you’ve defined, so fewer mistakes.
- **Simple Updates**: Change one enum, and it updates everywhere you use it.

### Example: Numeric and String Enums

Imagine you’re making a to-do app. You want to set task priorities and statuses. Here’s how enums can help:

```typescript
// Numeric Enum (TypeScript gives numbers automatically)
enum Priority {
  Low, // 0
  Medium, // 1
  High, // 2
}

// String Enum (You choose the words)
enum Status {
  Todo = "TODO",
  InProgress = "IN_PROGRESS",
  Done = "DONE",
}

// Using the enums
const task = {
  name: "Write blog",
  priority: Priority.Medium,
  status: Status.InProgress,
};

console.log(task); // { name: "Write blog", priority: 1, status: "IN_PROGRESS" }
```

Numeric enums (`Priority`) get numbers starting from 0. String enums (`Status`) let you set specific words, which is great for things like APIs or user-facing text.

## 2. What Is Type Inference in TypeScript?

Type inference is when TypeScript guesses the type of your data without you telling it. For example, if you write `let age = 25`, TypeScript knows `age` is a number. This makes coding faster and still keeps your code safe.

### Why Is Type Inference Useful?

- **Saves Time**: You don’t have to write types for everything.
- **Catches Mistakes**: TypeScript stops you from using the wrong type, like putting a word where a number should be.
- **Helps Coding**: Your editor gives better suggestions and spots errors as you type.

### Example: Type Inference

Check this out:

```typescript
// TypeScript knows 'name' is a string
let name = "Alice";

// TypeScript knows 'score' is a number
let score = 95;

// TypeScript knows 'student' is an object with a string and number
let student = {
  course: "Math",
  grade: 90,
};

// This will cause an error because 'score' is a number
// score = "ninety"; // Error: Type 'string' is not assignable to type 'number'

function sayHi(person: string) {
  return `Hi, ${person}!`;
}

// TypeScript knows the return value is a string
const greeting = sayHi("Bob");
console.log(greeting); // Hi, Bob!
```

TypeScript automatically figures out that `name` is a string, `score` is a number, and so on. If you mess up, like trying to set `score` to a word, TypeScript will warn you before you run the code.

## 3. How Does TypeScript Improve Code Quality and Maintainability?

TypeScript makes your code better and easier to manage in a few big ways:

- **Finds Errors Early**: It checks your code as you write, catching mistakes like wrong types or missing properties.
- **Clearer Code**: Types and enums make it obvious what your code does, so others (or future you) can understand it.
- **Easier Changes**: With types, you can update code without breaking things, and TypeScript will tell you if something’s wrong.
- **Team Friendly**: In big projects, TypeScript helps everyone stay on the same page with clear rules for data.

For example, if you’re working on a huge app, TypeScript’s types stop someone from passing a string to a function that needs a number. This saves hours of debugging and makes your project easier to grow or fix later.

## 4. What Are Union and Intersection Types in TypeScript?

Union types let a variable be one of several types, like a string _or_ a number. Intersection types combine multiple types, so a variable has _all_ their properties. They’re super handy for flexible but safe code.

### Example: Union and Intersection Types

Let’s say you’re building a user profile system:

```typescript
// Union Type: id can be a string or number
type UserId = string | number;

// Intersection Type: AdminUser has all properties of User and Admin
interface User {
  name: string;
  email: string;
}

interface Admin {
  role: string;
}

type AdminUser = User & Admin;

// Using union type
function getUser(id: UserId) {
  console.log(`Fetching user with ID: ${id}`);
}

getUser(123); // Works
getUser("abc123"); // Works

// Using intersection type
const adminUser: AdminUser = {
  name: "Emma",
  email: "emma@example.com",
  role: "superadmin",
};

console.log(adminUser); // { name: "Emma", email: "emma@example.com", role: "superadmin" }
```

In this example, `UserId` can be a string or number, so `getUser` accepts either. The `AdminUser` type combines `User` and `Admin`, so it must have `name`, `email`, and `role`. This keeps your code flexible but strict enough to avoid errors.

Happy coding! 😄
