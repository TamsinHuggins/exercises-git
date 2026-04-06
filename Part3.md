# 🐙 Git & GitHub Workshop - Part 3: Using Git in IntelliJ

---

## Section 1 - Git Integration in IntelliJ

IntelliJ has Git support built in - you can use the user interface to manage your commits, branches, and remote connections without using the commands if you prefer.

### Step 1 - Create a new Java (Maven) project

Create your project as normal using **File > New > Project...**.

Try checking the option that says **Create Git Repository**.

Checking this box will automatically run `git init` for you and create a local Git repository in your project folder. 

### Step 2 - Review your `.gitignore` file

A `.gitignore` file is a simple list of files and folders you want Git to leave alone and not include in commits.

When you build a project with "Create Git" selected, IntelliJ automatically creates a `.gitignore` for you at the root of your project. Open it and you should see entries like:

```
# IntelliJ project files
.idea/

# Maven build output
target/
```

Here is what the key entries mean:

- `.idea/` - IntelliJ stores your personal IDE settings here. These are specific to your machine and would create noisy, irrelevant changes for your teammates if committed.
- `target/` - temporary build output that Maven recreates automatically. This also covers all compiled `.class` files since Maven always outputs them here.

> 💡 Your `pom.xml` file **should** be committed - it defines how the project is built and which libraries it uses, so everyone on the team needs it.

---


## 🏆 Pair Challenge - Collaborate on a Shared Java Project

Now that you know the basics, it's time to practise a real team workflow with a partner.

---

### Setup - one person per pair

1. **Person A** creates a new public GitHub repo called `java-pair-practice`
2. **Person A** adds Person B as a collaborator:
   > **Settings** > **Collaborators** > **Add people**
3. **Both** clone the repo in IntelliJ:
   > **File** > **New** > **Project from Version Control** > paste the repo URL

---

### The Program

You are building a simple Java program together. Person A creates the starting point.

**Person A** - inside `src/main/java`, create `Main.java` with this skeleton and push it to `main`:

> 💡 For this exercise, keep it simple and use the default package (no `package` line).

```java
public class Main {
    public static void main(String[] args) {
        Greeter greeter = new Greeter();
        Calculator calculator = new Calculator();

        greeter.greet("World");
        System.out.println(calculator.add(3, 5));
    }
}
```

> 💡 In a Maven project, your Java source files live in `src/main/java`. Make sure you are creating your classes there, not in the project root.

---

### The Challenge - work on separate branches

Each person creates their **own branch** and works on a **different class**:

| Person | Branch name | Task |
|---|---|---|
| **Person A** | `feature/greeter` | Create `Greeter.java` with a `greet(String name)` method that prints a greeting |
| **Person B** | `feature/calculator` | Create `Calculator.java` with an `add(int a, int b)` method that returns the sum |

> 💡 Keep it simple - a few lines each is fine. The point is to practise the workflow, not write complex code.

---

### Workflow - each person follows these steps

1. Create and switch to your feature branch in IntelliJ
2. Write your class
3. Commit your changes with a clear message
4. Push your branch to GitHub
5. Open a **Pull Request** on GitHub into `main`
6. **Review each other's PR** and approve it
7. Merge both PRs into `main`
8. Both pull the latest `main` locally - you should now have each other's code

---

### Stretch goal 🚀

If you finish early, try adding a `subtract(int a, int b)` method to `Calculator.java` on a new branch - and see if you can do the whole PR workflow again without any guidance.
