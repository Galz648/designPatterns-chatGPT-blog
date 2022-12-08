Here is an example of code written in TypeScript that defies the Single Responsibility Principle:

```
class UserAccount {
  private username: string;
  private password: string;
  private email: string;
  private securityQuestion: string;
  private securityAnswer: string;

  constructor(username: string, password: string, email: string) {
    this.username = username;
    this.password = password;
    this.email = email;
  }

  public setSecurityQuestion(question: string, answer: string): void {
    this.securityQuestion = question;
    this.securityAnswer = answer;
  }

  public resetPassword(): void {
    // code to reset password
  }

  public updateEmail(newEmail: string): void {
    // code to update email
  }
}
```

This code defines a `UserAccount` class that has multiple responsibilities, such as setting security questions and answers, resetting passwords, and updating email addresses. This violates the Single Responsibility Principle, which states that a class should have only one reason to change. In this case, the `UserAccount` class has multiple reasons to change, as it is responsible for multiple distinct tasks.

Here is an example of code written in TypeScript that follows the Single Responsibility Principle:

```
class UserAccount {
  private username: string;
  private password: string;
  private email: string;

  constructor(username: string, password: string, email: string) {
    this.username = username;
    this.password = password;
    this.email = email;
  }
}

class SecurityInformation {
  private securityQuestion: string;
  private securityAnswer: string;

  constructor(securityQuestion: string, securityAnswer: string) {
    this.securityQuestion = securityQuestion;
    this.securityAnswer = securityAnswer;
  }
}

class PasswordReset {
  public resetPassword(username: string): void {
    // code to reset password
  }
}

class EmailUpdate {
  public updateEmail(username: string, newEmail: string): void {
    // code to update email
  }
}
```

In this example, the `UserAccount` class only has one responsibility, which is to store user account information. The other responsibilities, such as storing security information, resetting passwords, and updating email addresses, are each handled by their own separate classes. This follows the Single Responsibility Principle, as each class has only one reason to change.
