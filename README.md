
# Install Jar to Maven (.m2) Folder

There're some packages that is not provide by maven-repository anymore due to 
outdated or some other issues

We have to manually inject those packages into our project with 2 solutions
-------------------
**1. Directly with .jar in lib folder**

![App Screenshot](https://i.imgur.com/dP5Sp7T.png)

    <dependency>
        <groupId>com.finder</groupId>
        <artifactId>imgresize</artifactId>
        <version>2.6.3</version>
        <scope>system</scope>
        <systemPath>${basedir}/lib/CKFinderPlugin-ImageResize-2.6.3.jar</systemPath>
    </dependency>
 **2. Install Jar to Global Maven(.m2) folder - Recommended**

- Q: **Why?**
- A: There's problem when leaving lib at **<scope>system</scope>** is that
    when we install maven project that packages will not be include inside /target or war, jar file

### Solution
Clone this source and then do "Maven Install" (*Depend on what OS and IDE are you, please have a look on Google how to do Maven Install)

- Tada, packages in lib folder are place in maven(.m2) folder

![App Screenshot](https://i.imgur.com/sz4YBtV.png)

After that you can do like this

    <dependency>
        <groupId>com.finder</groupId>
        <artifactId>fileeditor</artifactId>
        <version>2.6.3</version>
        <scope>compile</scope>
    </dependency>

---
