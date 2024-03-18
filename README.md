# C# Style Guide

This coding style is based on the following guidelines:

- [Unity](https://unity.com/how-to/naming-and-code-style-tips-c-scripting-unity)
- [Microsoft](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions#style-guidelines)
- [Dotnet](https://github.com/dotnet/runtime/blob/main/docs/coding-guidelines/coding-style.md)
- [Google](https://google.github.io/styleguide/csharp-style.html)
- [O’Reilly](https://www.oreilly.com/library/view/java-pocket-guide/9781491938683/ch01.html)

# Index

| [Naming](#Naming)				| [Braces](#Braces)		| [Practices](#Practices)		|
| :---						| :---				| :---					|
| [🔗](#1-general) General			| [🔗](#2-general) General	| [🔗](#3-parameters) Parameters	|
| [🔗](#1-symbols) Symbols			| [🔗](#2-property) Property	| [🔗](#3-enum) Enum			|
| [🔗](#1-acronyms) Acronyms			| [🔗](#2-method) Method	| [🔗](#3-file) File			|
| [🔗](#1-namespace) Namespace			| [🔗](#2-condition) Condition	| [🔗](#3-namespace) Namespace		|
| [🔗](#1-class) Class				| [🔗](#2-switch) Switch	| [🔗](#3-declaration) Declaration	|
| [🔗](#1-struct) Struct			|				| [🔗](#3-comment) Comment		|
| [🔗](#1-interface) Interface			|				| [🔗](#3-definition) Definition	|
| [🔗](#1-enum) Enum				|				| [🔗](#3-event) Event			|
| [🔗](#1-field) Field				|				| [🔗](#3-string) String		|
| [🔗](#1-property) Property			|				| [🔗](#3-linq) Linq			|
| [🔗](#1-method) Method			|				| [🔗](#3-property) Property		|
| [🔗](#1-local-variable) Local variable	|				| [🔗](#3-switch) Switch		|
| [🔗](#1-parameters) Parameters		|				|					|
| [🔗](#1-event) Event				|				|					|

# Naming

## 1. General

❌ **Never** abbreviate, unless it’s math.  
✔️ **Always** declare the level modifiers.  
  •  Favor clarity of understanding instead of chopping off a few letters.

```csharp
// Allowed
public class SchoolGeography
{
    private bool hasMembers;
}

public void PageDown () {}
```

```csharp
// Not allowed
public class SchoolGeo
{
    bool hasMembers;
}

public void PgDn () {}
```

## 1. Symbols

❌ **Never** use underscores `_`, dashes `-` or numbers `123`.  
✔️ **Always** use only letters.  
  •  Avoid the use of `and`.

```csharp
// Allowed
public int TwoTimesFour
{
    get {return 8;}
}

private int daysOfTheWeek;

public string johnMarySusan;
```

```csharp
// Not allowed
public int TwoTimes4
{
    get {return 8;}
}

private int _days-of-the-week;

public string johnMaryAndSusan;
```

## 1. Acronyms

✔️ **Always** capitalize the first letter and **only** when it’s appropriate.

```csharp
// Allowed
public string FbiText
{
    get {return "FBI";}
}

private int faq;
```

```csharp
// Not allowed
public string FBIText
{
    get {return "FBI";}
}

private int Faq;
```

## 1. Namespace

✔️ **Always** use `PascalCase`.

```csharp
public namespace Package.LastRow
{

}
```

## 1. Class

✔️ **Always** the name should be a noun, as it represents a thing or an object.  
✔️ **Always** use `PascalCase`.

```csharp
public class Tree
{

}
```

## 1. Struct

✔️ **Always** follow the same rules as `class`.

```csharp
public struct Coin
{

}
```

## 1. Interface

✔️ **Always** the name should be an adjective, ending with `-able` or `-ible`, whenever the interface provides a capability.  
         Except if the rule above is not possible, then it should be a noun.  
✔️ **Always** precede with a capital i `I`.  
✔️ **Always** use `PascalCase`.

```csharp
public interface IDamageable
{
    void ReceiveDamage(int power)
}

public interface IHabitat
{
    object GetTurtle()
}
```

## 1. Enum

✔️ **Always** the name should be a singular type name.  
         Except if marked with the `System.FlagsAttribute`, then it should be pluralized, as these may represent more than one value.  
❌ **Never** use prefix or suffix.  
✔️ **Always** use `PascalCase`.

```csharp
public enum Verticality
{
    Up,
    Down,
}

[System.FlagsAttribute]
public enum Colors
{
    Red,
    Blue,
    Green,
    Yellow,
}
```

## 1. Field

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `camelCase`.

```csharp
public int count;

private bool hasBullets;
```

## 1. Property

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `PascalCase`.

```csharp
public bool IsHeavy
{
    get {return false;}
}

protected string Name
{
    get {return "none";}
}
```

## 1. Method

✔️ **Always** the name should contain a verb, as it’s used to make an object take action.  
✔️ **Always** use `PascalCase`.

```csharp
public void SelfDelete ()
{

}

protected int GetNumber ()
{
    return -1;
}
```

## 1. Local variable

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `camelCase`.

```csharp
{
    bool willExplode = false;
    var alphabet = "ABC";
}
```

## 1. Parameters

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `camelCase`.  
✔️ **Always** a single letter, when inside a `for`.  
  •  Avoid using single letters on anonymous methods, when it have more than one parameter.

```csharp
// Allowed
public void StartEngine (bool isHeavy, int speed) {}

for (int i = 0; i < 10; i++) {}

RegisterCallback (x => x.Speed = 0);

RegisterEvent ((blue, speed) => this.speed = blue.heigth * speed);
```

```csharp
// Not allowed
public void StartEngine (bool IsHeavy, int s) {}

for (int index = 0; index < 10; index++) {}

RegisterEvent ((x,y) => speed = x.heigth * y);
```

## 1. Event

✔️ **Always** the name should be prefixed with `on`.  
         if invoked after its represented action, follow with a verb on simple past.  
         if invoked before or during its represented action, follow with a verb on present.  
✔️ **Always** use `PascalCase`.  
✔️ **Always** apply this same rules to `UnityEvent`;

```csharp
public event Action OnExplode;

public UnityEvent<int> OnDisabled;
```

# Braces

## 2. General

✔️ **Always** put braces alone on a new line, when declaring types or a namespace.

```csharp
public namespace Vehicles.FourWheels
{
    public class Car
    {
        public struct Door
        {

        }
    }

    public interface IDrivable
    {

    }
}

```

## 2. Property

✔️ **Always** put braces on a new line alone.
  •  Allowed to use braces on the same line, when the body of the expression is just one statement.

```csharp
// Allowed
public bool IsBoolean
{
    get {return false;}
}

public string Name
{
    set
    {
        id = 0;
        name = value;
    }
}
```

```csharp
// Not allowed
public bool IsBoolean { get {return false;} }

public string Name
{
    set {
        id = 0;
        name = value;
    }
}
```

## 2. Method

✔️ **Always** put braces on a new line.
✔️ **Always** use empty braces on the same line of the method declaration, for empty methods.

```csharp
// Allowed
public void NewMethod ()
{
    Statement();
}

protected virtual void CreateAttachment () {}
```

```csharp
// Not allowed
public void NewMethod () {
    isBoolean = true;
}

protected virtual void CreateAttachment () 
{
}
```

## 2. Condition

✔️ **Always** use braces on a new line alone, if writing more than one statement.
❌ **Never** omit braces, if using more than one statement after a condition.
❌ **Never** omit braces, if nesting conditions.

```csharp
// Allowed
if (isBoolean == true)
    return;

if (instance == null)
    FirstStatement();
else if (text == "") 
    SecondStatement();
else
    intVar++;

if ((10 / 2) == 5) {
    Statement();
}

if (table == null)
{
    if (chair == null)
    {
        ChairStatement();
    }
}
```

```csharp
// Not allowed
if (isBoolean == true) {
    Statement();
    return;
}

if (instance == null) {
    intVar++;
    FirstStatement();
}
else 
    SecondStatement();
    
if (table == null)
    if (chair == null)
        ChairStatement();
```

## 2. Switch

✔️ **Always** use the first and last brace on a new line alone.
✔️ **Always** omit braces. Leave an empty line between each `case`.
❌ **Never** use one line `case`.

```csharp
// Allowed
switch (condition)
{
    default:
        Notify();

    case 0:
        Statement();
        break;

    case 1:
        SecondStatement();
        count++;
        break;
}
```

```csharp
// Not allowed
switch (condition) {
    default:
        Notify();

    case 0: Statement(); break;

    case 1:
    {
        SecondStatement();
        count++;
        break;
    }
}
```

# Practices

## 3. Var

❌ **Never** use it, if it makes the type ambiguous.
  •  favor using `var` at all times.

```csharp
// Allowed
{
    Transform position = StartMovement();
    var doubleValue = (double)(2 * 2);
    var rock = material as Rock;
    
    if (Raycast (ray, out var raycastResult))
    {
        Debug.Log (raycastResult);
    }
}
```

```csharp
// Not allowed
{
    var position = StartMovement();
    var doubleValue = 2 * 2;
    var rock = material;

    if (Raycast (ray, out var output))
    {
        Debug.Log (output);
    }
}
```

## 3. Parameters

✔️ **Always** use `this` to avoid ambiguity between members and local variables.

```csharp
// Allowed
public class Train ()
{
    private float speed;

    public Train (float speed)
    {
        this.speed = speed;
    }
}
```

```csharp
// Not allowed
public class Train ()
{
    private float speed;

    public Train (float speed)
    {
        speed = speed;
    }
}
```

## 3. Enum

  •  favor declaring the member `None`, with a initial value of zero.

```csharp
public enum Side
{
    None = 0,
    Up,
    Down,
    Right,
    Left,
}
```

## 3. Lambda expression

Only on anonymous methods, never on member declaration

---

## 3. File

  •  Column limit: 120.
  •  Indentation must be the size of four spaces.
  •  Tab must create four spaces.
✔️ **Always** end the file with an empty single line.
❌ **Never** follow an empty line, with another empty line.

## 3. Namespace

✔️ **Always** import at the top of the file, outside the declaration of any `namespace`.
✔️ **Always** put `System.*` namespaces on top of all the others.
✔️ **Always** sort them alphabetically.
❌ **Never** leave unused namespaces.

## 3. Declaration

✔️ **Always** match the source file’s name with the `MonoBehaviour` declared inside of it.
✔️ **Always** declare only one structure per file.
❌ **Never** declare an `enum`, `struct` or `class` inside another class, unless not public.
  •  favor declaring `class` instead of `struct`.
✔️ **Always** declare fields at the top of the class.
  •  avoid using public fields.

## 3. Comment

✔️ **Always** use `///` to produce comments in classes and its members. It should automatically create a `<summary>` tag or `<parameter>` and `<return>`, if necessary.
  •  favor using the `[ToolTip]` attribute, as it will create both editor and XML comment.

```csharp
/// <summary>
/// Represent the graphics and collision of the arena.
/// </summary>
public class Scenario
{
    [SerializeField]
    [ToolTip("Text that will be displayed on the main menu.")]
    private string uiName;
}
```

---

## 3. Definition

- Never use `new()`, if the type is not explicit on the left-hand side.

```csharp
private List<int> manyNumbers = new();

{
    List<int> localNumbers = null;
    localNumbers = new List<int>();
}
```

```csharp
{
    List<int> localNumbers = null;
    localNumbers = new();
}
```

---

## 3. Event

- favor using `event` for callbacks.
    - except when exposing to the editor, then use `UnityEvent`.
- favor using `System.Action`.

---

## 3. String

- string interpolation = $””
- favor using the `+` operator, to increase readibility.

```csharp
public string introText = "" + + + + 

private string listText = $"{someList.Name} has {someList.Count} children.";

$"{3.25f:F3}"
```

```csharp
public string introText = ""
```

---

## 3. LINQ

- favor using it when handling collections.
✔️ **Always** use only one type: keywords or methods

```csharp
as select
```

---

## 3. Property

- avoid auto-Implemented properties, because Unity editor can’t display the anonymous field.
    - Instead, explicitly declare the field for the property.
- Favor using it, instead of methods, when dealing with a single field and few calculations.

```csharp
public bool IsBoolean
{
    get => isBoolean;
    set => isBoolean = value;
}

[SerializeField]
private bool isBoolean;
```

---

```csharp
public bool IsBoolean { get; set; }
```

---

## 3. Switch

✔️ **Always** implement default, to handle unknown cases.
✔️ **Always** leave an explicit comment, when falling through.

```csharp
switch (otherCondition)
{
    default:
    // Fallingthrough

    case 0: 
    headerText = "invalid value";
    break;

    case 1:
    headerText = "initiating"; 
    break;
}
```

---

```csharp
// TODO

// Markdown
// Implement the 'top' button in each header, that will bring the view to the index header

// Using classes to nest variables or to simply enjoy of the editor folding option
// UnityEvent + C# event
// ? operator when calling methods from objects

// Nesting parameters to the same identation of the first one, increase readibility

// Properties vs methods of Get and Set

// foreach (var item in List)

// Line breaks should occur before binary operators, if necessary.

// avoid unnecessary comments inside of code blocks

// naming of coroutines 
// (how to deal with coroutines being stopped when the GO is disabled)

// always use a brace alone in each line, when the lambda have more than one expression

// if lambda is referenced outside its declaration, create a method for it

// Field initializers are generally encouraged.

// Avoid Container.ForEach(...) for anything longer than a single statement.

// Prefer List<> when the size of the container can change.
// Prefer arrays when the size of the container is fixed and known at construction time.
// Prefer array for multidimensional arrays.

// have .editorConfig for this whole style
// have an editor theme style

// C# keywords (using, try, as,...)
```


<small><a href="#wrapper">[top]</a></small>
<!-- End of Sample Content -->
