# Combining Union '|' and Intersection '&' Types 

## Introduction

The two important types is Union '|' and Intersection '&'. Union types allow a value to have one of several possible types, while Intersection types combine multiple types into one.

## Practical Example

Such as A User Management System. Each user has personal information and account details. A user's status has two value "active" or "inactive".

type UserStatus = "active" | "inactive";

type PersonalInfo = {
  id: number;
  name: string;
};

type AccountInfo = {
  email: string;
  status: UserStatus;
};

type User = PersonalInfo & AccountInfo;

Here, UserStatus uses a Union '|' type because the status can have two values.

The 'User' type uses a Intersection to combine the 'PersonalInfo' and 'AccountInfo'. So, a User must contain all the properties from both types.

Now, suppose user:
const user: User = {
  id: 1,
  name: "Akash",
  email: "arakash022@gmail.com",
  status: "active"
};

If we remove any property or gives a invalid status, TypeScript will show error.

## Conclusion

using both Union and Intersection types makes code more flexible and organizable. for the Union when a value can have multiple possible options, and for the Intersection when an object needs to join multiple type structures.