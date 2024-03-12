# C# Style Guide

This coding style is based on the following guidelines:

- [Unity](https://unity.com/how-to/naming-and-code-style-tips-c-scripting-unity)
- [Microsoft](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/coding-conventions#style-guidelines)
- [Dotnet](https://github.com/dotnet/runtime/blob/main/docs/coding-guidelines/coding-style.md)
- [Google](https://google.github.io/styleguide/csharp-style.html)
- [O’Reilly](https://www.oreilly.com/library/view/java-pocket-guide/9781491938683/ch01.html)

# Index
| [Naming](#Naming)                    	 | [Braces](#Braces) 		 | [Practices](#Practices) 		|
| :---                                   | :---:             	         | ---:          			|
| [🔗](#name-general) General                | [General](#brace-general)     | [Parameters](#practice-parameters) 	|
| [🔗](#name-symbols) Symbols                | [Property](#brace-property)   | [Enum](#practice-enum) 		|
| [🔗](#name-acronyms) Acronyms              | [Method](#brace-method)       | [File](#practice-file)		|
| [🔗](#name-namespace) Namespace            | [Condition](#brace-condition) | [Namespace](#practice-namespace)	|
| [🔗](#name-class) Class                    | [Switch](#brace-switch)       | [Declaration](#practice-declaration)	|
| [🔗](#name-struct) Struct                  |                         	 | [Comment](#practice-comment)		|
| [🔗](#name-interface) Interface            |				 | [Definition](#practice-definition)	|
| [🔗](#name-enum) Enum                      |				 | [Event](#practice-event)		|
| [🔗](#name-field) Field                    |				 | [String](#practice-string)		|
| [🔗](#name-property) Property              |				 | [Linq](#practice-linq)		|
| [🔗](#name-method) Method                  |				 | [Property](#practice-property)	|
| [🔗](#name-local-variable) Local variable  |				 | [Switch](#practice-switch)		|
| [🔗](#name-parameters) Parameters          |
| [🔗](#name-event) Event                    |

# Naming

<h2 id="name-general"> General </h2>

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

<div>
<h2 id="name-symbols"> Symbols </h2> <span align="right"> top </span>
</div>

❌ **Never** use underscores `_`, dashes `-` or numbers `123`.  
✔️ **Always** use only letters.  
  •  Avoid the use of `and`.

```csharp
// Allowed
public int TwoTimesFour
{
    get => 8;
}

private int daysOfTheWeek;

public string johnMarySusan;
```

```csharp
// Not allowed
public int TwoTimes4
{
    get => 8;
}

private int _days-of-the-week;

public string johnMaryAndSusan;
```

<h2 id="name-acronyms"> Acronyms </h2>

✔️ **Always** capitalize only the first letter and only when it’s appropriate.

```csharp
// Allowed
public string FbiText
{
    get => "FBI";
}

private int faq;
```

```csharp
// Not allowed
public string FBIText
{
    get => "FBI";
}

private int Faq;
```

<h2 id="name-namespace"> Namespace </h2>

✔️ **Always** use `PascalCase`.

```csharp
public namespace Package.LastRow
{

}
```

<h2 id="name-class"> Class </h2>

✔️ **Always** the name should be a noun, as it represents a thing or an object.  
✔️ **Always** use `PascalCase`.

```csharp
public class Tree
{

}
```

<h2 id="name-struct"> Struct </h2>

✔️ **Always** follows the same rules as `class`.

```csharp
public struct Coin
{

}
```

<h2 id="name-interface"> Interface </h2>

✔️ **Always** the name should be an adjective, ending with `-able` or `-ible`, whenever the interface provides a capability.  
         Except if the rule above is not possible, then it should be a noun.  
✔️ **Always** precede with a capital i `I`.  
✔️ **Always** use `PascalCase`.

```csharp
public interface IDamageable
{

}
```

<h2 id="name-enum"> Enum </h2>

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

<h2 id="name-field"> Field </h2>

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `camelCase`.

```csharp
public int count;

private bool hasBullets;
```

<h2 id="name-property"> Property </h2>

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `PascalCase`.

```csharp
public bool IsHeavy
{
    get => false;
}

protected string Name
{
    get => "none";
}
```

<h2 id="name-method"> Method </h2>

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


<h2 name="name-local-variable"> Local variable </h2>

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `camelCase`.

```csharp
{
    bool willExplode = false;
    var alphabet = "ABC";
}
```

<h2 name="name-parameters"> Parameters </h2>

✔️ **Always** the name should be a noun, representing a thing or state.  
         Except if it’s a `boolean` type, then it should be prefixed with a verb, followed by a condition.  
✔️ **Always** use `camelCase`.  
✔️ **Always** a single letter, when inside a `for`.  
  •  Avoid using single letters, when lambdas have more than one parameter.

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

<h2 name="name-event"> Event </h2>

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

## [General](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- always put braces alone on a new line, for the following: `class`, `struct`, `interface`, `namespace`.

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

## [Property](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- **always** put braces on a new line alone

```csharp
public bool IsBoolean
{
    get => false;
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

---

```csharp
public bool IsBoolean { get => false }

public string Name {
    set {
        id = 0;
        name = value;
    }
}
```

---

## [Method](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- **always** put braces on a new line
- **always** use empty braces on the same line of the method declaration.

```csharp
public void NewMethod ()
{
    Statement();
}

protected virtual void CreateAttachment () {}
```

```csharp
public void NewMethod () {
    isBoolean = true;
}

protected virtual void CreateAttachment () 
{
}
```

---

## [Condition](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- **always** use braces on a new line alone, if writing more than one statement.
- **never** omit braces, if using more than one statement after a condition.
- **never** omit braces, if nesting conditions.

```csharp
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

---

```csharp
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

---

## [Switch](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- **always** use the first and last brace on a new line alone.
- **always** omit braces. Leave an empty line between `case`.
- **never** use one line `case`.

```csharp
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

---

# [Practices](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

## Parameters

- favor using `var`.
- **always** use `this` to avoid ambiguity between members and local variables.
- avoid `var` if it makes the type ambiguous.

```csharp
{
    bool willExplode = false;
    var doubleValue = (double)(2 * 2);
    var rock = material as Rock;
    var text = material.ToString();
    
    if (Raycast(ray, out var hit))
    {
        Debug.Log(hit);
    }
}

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
{
    var doubleValue = 2 * 2;
    var rock = material;
    var text = StartMovement();

    if (Raycast(ray, out var found))
    {
        Debug.Log(found);
    }
}

public class Train ()
{
    private float speed;

    public Train (float speed)
    {
        speed = speed;
    }
}
```

---

## [Enum](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- favor declaring the member `None`, with a initial value of zero.

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

---

## [File](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- Column limit: 120.
- Indentation must be the size of four spaces.
- Tab must create four spaces.
- **always** end the file with an empty single line.
- **never** follow an empty line, with another empty line.

---

## [Namespace](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- **always** import at the top of the file, outside the declaration of any `namespace`.
- **always** put `System.*` namespaces on top of all the others.
- **always** sort them alphabetically.
- **never** leave unused namespaces.

---

## [Declaration](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- **always** match the source file’s name with the `MonoBehaviour` declared inside of it.
- **always** declare only one structure per file.
- **never** declare an `enum`, `struct` or `class` inside another class, unless not public.
- favor declaring `class` instead of `struct`.
- **always** declare fields at the top of the class.
- avoid using public fields.

---

## [Comment](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- **Always** use `///` to produce comments in classes and its members. It should automatically create a `<summary>` tag or `<parameter>` and `<return>`, if necessary.
- favor using the `[ToolTip]` attribute, as it will create both editor and XML comment.

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

## [Definition](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

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

## [Event](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- favor using `event` for callbacks.
    - except when exposing to the editor, then use `UnityEvent`.
- favor using `System.Action`.

---

## [String](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

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

## [Linq](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- favor using it when handling collections.
- **always** use only one type: keywords or methods

```csharp
as select
```

---

# [Property](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

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

## [Switch](https://www.notion.so/C-Style-Guide-9febc21f7cdc4ee08188da425946dfa3?pvs=21)

- always implement default, to handle unknown cases.
- always leave an explicit comment, when falling through.

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

// Using classes to nest variables or to simply enjoy of the editor folding option

// ? operator when calling methods from objects

// Nesting parameters to the same identation of the first one, increase readibility

// Properties vs methods of Get and Set

// When using UnityEvent or any other callback that is not an event, you can 
// hide the member and create methods to call, register and unregister to it.
// It's a more extensive approach but it will allow proper encapsulation

// Singleton boilerplate

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
