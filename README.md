# Team 5426 Coding Standard

The following standard was agreed upon as the Java coding standard to be used in all projects by Team 5426.


| Version | Description     | Author        | Date       |
|---------|-----------------|---------------|------------|
| 1.0     | Initial Version | Duncan Snider | 2019-02-23 |


## Section 1 - Source Files
### 1.1 Naming Conventions
#### 1.1.1 General Naming Conventions

File names shall be capitalized. All other words within a file name should also be capitalized.

File names shall clearly represent their contents.

File names shall use proper spelling and grammar where applicable.

File names shall not contain spaces, hyphens, underscores or any other type of spacing character.

Good Examples:
```
Robot.java
CommandBase.java
```

Bad Examples:
```
robot.java       <- no capitalization
r.java           <- does not represent contents
commandBase.java <- bad capitalization
comandbase.java  <- bad spelling
```

#### 1.1.2 Command Naming

Command file names shall be prefixed by "Command"

*We often have many directories and files in our projects which can create a less productive environment. For example, if you have a command called `Drive.java` and you also have a subsystem called `Drive.java` it is not instantly clear which file does what. However, if you prefix your command with "Command", it can be quickly determined that one file is the command and the other is the subsystem.*

#### 1.1.3 Subsystem Naming

Subsystems file names shall not be prefixed.

### 1.2 Source File Structure

All Robot project structures shall follow the following format.

Index: `-[` means package, `--` means file, **bold** means required

<pre>
-[ auto
-[ enums
-[ utils
-[ <b>commands</b>
  -- <b>CommandBase.java</b>
-[ <b>subsytems</b>
-- <b>OI.java</b>
-- <b>Robot.java</b>
-- <b>RobotMap.java</b>
</pre>

**Definitions:**

| File/Package  | Usage                                                                                            |
| ------------- |--------------------------------------------------------------------------------------------------|
| auto          | If using autonomous routines, place routine files inside this package.                           |
| enums         | If enums are used, place their declaring files within this package.                              |
| utils         | Any utility files are to be placed within this package. Ex: XboxController.java                  |
| commands      | Contains command files                                                                           |
| commands/CommandBase.java | Acts as a base for all commands. Contains subsystem instances that commands require. |
| subsystems | Contains subsystem files                                                                            |
| OI.java | Contains human interface code (controllers, joysticks, command bindings, etc)                          |
| Robot.java | The project's main file                                                                             |
| RobotMap.java | Contains all static variables                                                                    |

*Other packages/files can be added **if and only if absolutely necessary**. You should not need to have any additional packages/files. If you do, consider adding it to the above list if they could be necessary for future years as well.*

*Wherever possible, limit creation of additional packages/files within the root package.*

### 1.3 File Encoding

All files shall be encoded in UTF-8.

## Section 2 - Code Formatting

### 2.1 Braces

#### 2.1.1 Use Braces Where Optional

Braces shall be used with ``if``, ``else``, ``for``, ``do``, and ``while`` statements even if the body is empty or only contains a single statement.

#### 2.1.2 Brace Style

All code blocks follow the following style examples:

```java
if (true) {
	// do something
}

else if (false) {
	// do something else
}

else {
	// something else
}

// while loops
while (true) {
	// do something
}

// do while loops
do {
	// something
} while (true);

// for loops
for (int i = 0; i < 10; i++) {
	// something
}

// classes and class functions
public class TestCommand extends Command {
	public Command() {
		// some constructor content
	}
    
	public void test() {
		// some function content
	}
}

// try/catch
try {
	// try something
} catch (Exception e) {
	// catch something
}
```

### 4.2 Block Indentation

All blocks shall be indented with either a tab with a length of 4. Spaces shall not be used.

### 4.3 Line Breaks

Each statement shall be followed by a line break.

Variable declarations of various types shall also be followed by a line break.

**Example:**

```java
public boolean doSomething() {
	int integerOne = 1;
    int integerTwo = 2;
    
    double doubleOne = 1.0;
    double doubleTwo = 2.0;
    
    boolean booleanOne = true;
    
    if ((integerOne + integerTwo) == 4) {
    	return true;
    }
    
    return false;
}
```

### 4.4 Whitespace
#### 4.4.1 Vertical Whitespace

A single blank line always appears:
  - Between functions/methods
  - Between variable declarations of different types
  - As required by other sections of this document

#### 4.4.2 Horizontal Whitespace

A single space must appear:
  - After any reserved word (if, else, etc)
  - After any closing parenthesis of a function declaration
  - Before and after any operator (, ==, +, -, *, /, etc)

Other than the aforementioned conditions, horizontal whitespace can be added at the discretion of the author. Ensure that consistency is maintained.

**Examples**:
```java
if (i == 1) {}

public void doSomething() {}

if ((i + 1 / 2 * 5 % 2)) == 0) {}
```

#### 4.4.2 Horizontal Alignment

Horizontal is not required and can be added at the discretion of the author.

**Examples:**
```java
This is fine:

int integerOne = 1;   // integer one description
int integerTwo = 200; // integer two description

But so is:

int integerOne = 1; // integer one description
int integerTwo = 200; // integer two description
```

### 4.5 Variable Declarations

Only one variable per declaration is permitted. Declarations such as ```int a, b;``` are not to be used.

**Good Example:**
```java
int a;
int b;
```

**Bad Example:**
```java
int a, b;
```

#### 4.5.1 Array Declarations

C-Style array declarations are not to be used.

**Good Example:**
```java
String[] args;
```

**Bad Example:**
```java
String args[];
```


### 4.6 Switch Statements

Switch statements should be formatted as follows:

```java
switch (input) {
	case 1:
		fallThrough();
	case 2:
		prepareOneOrTwo();
        // fall through
    case 3:
    	prepareOneTwoOrThree();
        break;
    case 4:
    	prepareFour();
        break;
    default:
    	prepareDefault();
        break;
}
```

## Section 5 - Naming
All identifiers shall only use ASCII letters and digits.

**Identifiers must clearly identify what they represent.**
Jokes, Pop-Culture and other references are **not** appropriate identifier names. Identifier prefixes such as `m` or `k` shall not be used in any projects.

If you can't look at an identifier and understand what it represents with minimal thought involved, it's probably not a good identifier.


### 5.1 Rules by identifier type
#### 5.1.1 Package Names

Package names shall be all lowercase with consecutive words concatenated together. Example: `org.usfirst.frc.team5426.robot.autoroutines`

#### 5.1.2 Class names

Class names are written in upper camel case. Example: `UpperCamelCase`.

As a general rule, class names should be nouns or noun phrases. Example: `Robot` or `RobotBase`.

#### 5.1.3 Method Names

Method names are written in lower camel case. Example: `lowerCamelCase`.

As a general rule, method names should be verbs or verb phrases. Example: `stop` or `sendMessage`.

Be aware that many methods included in WPILib will not follow this format.




#### 5.1.4 Constant Names

All constants shall be written in constant case.

**Examples:**
```java
static final int NUMBER = 10;
static final String MESSAGE_TO_USER = "Hello!";
```

#### 5.1.5 Non-Constant Names

All non-constant variable names must be written in lower camel case. 

**Examples:** 
```java
int number = 5;
int otherNumber = 10;
```

#### 5.1.6 Parameter Names

Parameter names are written in lower camel case.

**Examples:** 
```java
public void doSomething(int number, int otherNumber) {}
```











