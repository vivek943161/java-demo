# 🚀 Maven Project Demo

This guide will help you create, build, and run a simple Java application using **Maven**.

---

# 🧰 Prerequisites

Make sure you have the following installed:

### ✅ Check installations

```bash
java -version
mvn -v
```

If not installed:

* Install Java (JDK 8 or above)
* Install Maven

---

# 📁 Step 1: Create Maven Project

Run the following command:

```bash
mvn archetype:generate \
  -DgroupId=com.demo \
  -DartifactId=my-app \
  -DarchetypeArtifactId=maven-archetype-quickstart \
  -DinteractiveMode=false
```

👉 This will create a project folder:

```
my-app/
```

---

# 📂 Step 2: Navigate into Project

```bash
cd my-app
```

---

# 🏗️ Step 3: Understand Project Structure

```
my-app/
 ├── pom.xml
 └── src/
     ├── main/java/com/demo/App.java
     └── test/java/com/demo/AppTest.java
```

* `pom.xml` → Project configuration (dependencies + build)
* `src/main/java` → Application code
* `src/test/java` → Test code

---

# ✍️ Step 4: Update Application Code

Open file:

```
src/main/java/com/demo/App.java
```

Replace with:

```java
package com.demo;

public class App {
    public static void main(String[] args) {
        System.out.println("Hello Maven!");
    }
}
```

---

# 📦 Step 5: Add Dependency

Open `pom.xml` and update `<dependencies>` section:

```xml
<dependencies>

  <!-- Test dependency -->
  <dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>3.8.1</version>
    <scope>test</scope>
  </dependency>

  <!-- Utility library -->
  <dependency>
    <groupId>org.apache.commons</groupId>
    <artifactId>commons-lang3</artifactId>
    <version>3.12.0</version>
  </dependency>

</dependencies>
```

---

# 🔨 Step 6: Build the Project

```bash
mvn clean package
```

👉 This will:

* Compile code
* Download dependencies
* Create a JAR file

---

# 📦 Output (Artifact)

After build, check:

```
target/my-app-1.0-SNAPSHOT.jar
```

---

# ▶️ Step 7: Run the Application

```bash
java -cp target/my-app-1.0-SNAPSHOT.jar com.demo.App
```

👉 Output:

```
Hello Maven!
```

---

# 🔁 Step 8: Maven Lifecycle (Important)

```
clean → compile → test → package → install → deploy
```

Common commands:

```bash
mvn compile
mvn test
mvn package
mvn install
```

---

# 📥 Step 9: Install to Local Repository

```bash
mvn install
```

👉 Stores your artifact in:

```
~/.m2/repository
```

---

# ❗ Common Errors

| Issue            | Fix                        |
| ---------------- | -------------------------- |
| Build fails      | Check `pom.xml` syntax     |
| Class not found  | Check package name         |
| Dependency error | Re-run `mvn clean package` |

---

# 🎯 What You Learned

* What is Maven
* What is `pom.xml`
* How to build a JAR
* How to run a Java application
* How dependencies work

---

# 🚀 One-line Summary

👉 Maven converts your Java code + dependencies into a runnable JAR file

---
