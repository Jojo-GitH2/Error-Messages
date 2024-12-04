# Console.ReadKey Method (System)

## Definition:
- `Console.ReadKey()` is a method in C# that reads the next key pressed by the user and returns the key information.
- The method does not display the pressed key on the console.
- The method is used to read a single key press from the user.
- The method is a blocking method, which means that the program will wait for the user to press a key before continuing.
- The method returns a `ConsoleKeyInfo` object that contains the key information.
- The `ConsoleKeyInfo` object contains the following properties:
  - `Key` - The key that was pressed.
  - `KeyChar` - The character representation of the key that was pressed.
  - `Modifiers` - The modifier keys that were pressed along with the key.
  - `Key` and `KeyChar` properties are used to get the key that was pressed.
  - The `Modifiers` property is used to get the modifier keys that were pressed along with the key.


## Syntax:
Console.ReadKey()

## Example:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Press any key to continue...");
        Console.ReadKey();
        Console.WriteLine("You pressed a key!");
    }
}
```
## Output:
```csharp
Press any key to continue...
You pressed a key!
```

## Error

```bash
Press any key to continue...
Unhandled exception. System.InvalidOperationException: Cannot read keys when either application does not have a console or when console input has been redirected. Try Console.Read.
   at System.ConsolePal.ReadKey(Boolean intercept)
   at Program.<Main>$(String[] args) in C:\Users\Lawal\OneDrive\Desktop\GitHub Folders\C#\LearnToC#\Program.cs:line 9
```

![alt text](<assets/image copy.png>)

## Solution
- The error occurs when the program is run in a non-interactive environment, such as when the program is run from a script or when the program is run from a non-console application.
- To fix the error, you can check if the program is running in an interactive environment before calling the `Console.ReadKey()` method.
- In my case, that was the issue. I was running the program by using the Play button on Visual Studio Code. To fix the error, I ran the program by using the terminal using the `dotnet run` command.

## Output
```bash
Press any key to continue...
You pressed a key!
```

![alt text](<assets/image.png>)

**Note**: If you would like to see the ConsoleKeyInfo in the output, you can add the `Console.WriteLine()` method to display the key information.

![alt text](<assets/image copy 2.png>)