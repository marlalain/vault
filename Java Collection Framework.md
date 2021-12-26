---
alias: ['Java Collection']
---

## ArrayList ([[Arrays]])

```ad-info
title: Important: [[Why use interfaces]] or [[Why use interfaces|Why List over ArrayList]]
```

### Basic Operations

```java
// Declaring
ArrayList<String> names = new ArrayList<>();
// ArrayList<String> names = new ArrayList<>(5); <- Specify size

// Adding
names.add("John");
names.add("Mark");
names.add("Josh")

// Removing
names.remove(0);
names.remove("Mark");

// Replacing
names.put(0, "Joshua"); // Josh -> Joshua

// Getting size
names.size(); // <- number

// Checking if list contains an element
names.contains("Joshua"); // <- boolean

// Getting element
names.get(0); // <- T (ArrayList<T>)

// Printing
System.out.println(names.toString());
```

### Looping

```java
ArrayList<String> names = new ArrayList<>();

// Oldschool way
for (String name : names) {
	System.out.println(name);
}

names.forEach(name -> {
	System.out.println(name);
})

names.forEach(System::out::println);
```

### Sorting

Using [[Java Collections|Collections]]

```java
Collections.sort(myList);
```

Using `ArrayList.sort()`
```java
users.sort(Comparator.comparing(User::getName));
```

### Unmodifiable Lists

To protect our `private` list, we could return a unmodifiable version of our list

```java
class NameHolder {
	private List<String> names;
	public List<String> getNames() {
		return Collections.unmodifiableList(names);
	}
}
```

Now, if someone gets our `names` it can't edit, add or sort it

## LinkedList

```ad-info
title: [[Linked Lists|Linked Lists vs Array Lists]]
```
The implementation is more or less the same

## Sets

---

Related: [[Java Collections]]