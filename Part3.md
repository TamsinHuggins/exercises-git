# 🐙 Git & GitHub Workshop - Part 3: Using Git in IntelliJ

---

## Section 1 - Git Integration in IntelliJ

IntelliJ has Git support built in - you can use the user interface to manage your commits, branches, and remote connections without using the commands if you prefer.

### Step 1 - Create a new Maven project

Create your Maven project as normal.

If IntelliJ shows an **Add Git Repository** option during setup, tick it. If not, open the project first, then go to:

> **VCS** > **Enable Version Control Integration** > **Git**


### Step 2 - Create a `.gitignore` file


A `.gitignore` file is a simple list of files and folders you want Git to leave alone and not include in commits.

IntelliJ generates a `.idea/` folder to store your project settings. Most of this is personal to your machine and should **not** be committed to Git.

In the root of your project, create a file called `.gitignore` and add the following:

```
# IntelliJ project files
.idea/
*.iml

# Maven build output
target/

# Compiled Java classes
*.class
```

> 💡 Without this, your teammates will constantly see noisy, irrelevant changes to IDE config files every time they pull your work. The `target/` folder is just temporary build output that Maven can recreate automatically, so it should never be committed.

> 💡 Your `pom.xml` file **should** be committed - it is the heart of a Maven project and tells everyone on the team which dependencies and build settings the project uses.

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
