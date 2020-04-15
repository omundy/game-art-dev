

![unity logo](images/unity-logo-293w.png)

## Reference Sheet - Unity C# Scripting - 04

* Storing and using data in multiples and collections


### Classes




### Structs

* Useful for holding small data values
* Structs are value types (so faster than a class object). When you pass a struct, it creates a copy of the data.
* Easier to transfer a class object than a struct so do not use struct when you are passing data across the wire or to other classes
* Can contain parameterized constructor, static constructor, constants, fields, methods, properties, indexers, operators, events and nested types

```C#
public struct NPC
{
    // fields
    public string Title;
    public bool GoodGuy;
    // constructor
    public NPC(string _Title, bool _GoodGuy)
    {
        Title = _Title;
        GoodGuy = _GoodGuy;
    }
}
// create instance using constructor
NPC badguy1 = new NPC(1, "Dr. Evil", false);
// test 
Console.Write(badguy1.Name); // prints Dr. Evil
```


### Arrays

* Can contain elements of any data type
* Stores a sequential collection of values of the same type
* Length is fixed, unchangeable, and can be specified or inferred
* Use index number to access values (below, `colors[1] = "green"`)

```C#
using UnityEngine;
using System.Collections;

public class Array : MonoBehaviour
{
    public string[] colors = new string[] { "red", "green", "blue" };

    void Start()
    {
        for (int i = 0; i < colors.Length; i++)
        {
            Debug.Log("Array " + i + " = " + colors[i]);
        }
    }
}
```


### ArrayList

* A non-generic type of collection
* Stores objects of any type like an array
* Unlike an array, you don't need to specify the size as it grows automatically as you add items in it

```C#
IList arrayList = new ArrayList() { 100, "Two", 12.5, 200 };
arrayList.Add("hello");
print (myArryList[4]); // prints "hello"
```


### Lists

* The List<T> collection is the same as an ArrayList except that List<T> is a generic collection
* Stores a sequential collection of values of the same type
* Length is adjustable
* You can easily add and remove elements from a List

```C#
IList<int> intList = new List<int>();
intList.Add(10);
print (intList[0]); // prints 10
```


### Dictionaries

* Dictionaries store a collection of Keys and Values
* The Dictionary<TKey, TValue> class is a generic collection class in the System.Collection.Generics namespace. 
* TKey denotes the type of key and TValue is the type of TValue.

```C#
Dictionary<string, string> dict = new Dictionary<string, string>();
dict.Add("greeting","hello world!");
print (dict["greeting"]);
```


### Sources
* Unity Script Reference: [Array](https://docs.unity3d.com/ScriptReference/Array.html), [Lists and Dictionaries](https://learn.unity.com/tutorial/lists-and-dictionaries) 
* TutorialsTeacher: C# [Structs](https://www.tutorialsteacher.com/csharp/csharp-struct), [Arrays](https://www.tutorialsteacher.com/csharp/array-csharp), [ArrayLists](https://www.tutorialsteacher.com/csharp/csharp-arraylist), [Lists](https://www.tutorialsteacher.com/csharp/csharp-list), [Dictionaries](https://www.tutorialsteacher.com/csharp/csharp-dictionary)
* W3Schools: C# [Arrays](https://www.w3schools.com/cs/cs_arrays.asp)
* [How to use arrays, lists, and dictionaries in Unity for 3D game development](https://hub.packtpub.com/arrays-lists-dictionaries-unity-3d-game-development/)
