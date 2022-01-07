---
date created: 2022-01-04 20:27
date updated: 2022-01-05 19:54
---

# Cheatsheet

## Relationships

Given the relationship between the resources `Todo` and `Pendency`;

### @OneToMany

```kotlin
@ManyToOne
@JoinColumn(name = "id")
var todo: Todo
```

```kotlin
@OneToMany(mappedBy = "todo")
var pendencies: Set<Pendency>
```

### @ManyToMany

#### Composite Key Method

```kotlin
@ManyToMany
@JoinTable(
	name ="todos_pendencies",
	joinColumns = [JoinColumn(name = "pendency_id")],
	inverseJoinColumns = [JoinColumn(name = "todo_id")]
)
var todos: Set<Todo>
```

```kotlin
@ManyToMany(mappedBy = "todos")
var pendencies: Set<Pendency>
```

#### New Entity Method

```kotlin
// TodoPendencyGlue
@ManyToOne
@JoinColumn(name = "todo_id")
var todo: Todo

@ManyToOne
@JoinColumn(name = "pendency_id")
var pendency: Pendency
```

```kotlin
// inside Todo
@OneToMany(mappedBy="todo")
var todos: Set<Todo>

// inside Pendency
@OneToMany(mappedBy="pendency")
var pendencies: Set<Pendency>
```

### @OneToOne

#### Foreign Key Method

```kotlin
@OneToOne
@JoinColumn(
	name = "todo_id",
	referencedColumnName = "id" 
)
var todo: Todo
```

```kotlin
@OneToOne(mappedBy = "todo")
var pendency: Pendency
```

#### Shared Primary Key Method

```kotlin
@OneToOne(mappedBy = "pendency")
@PrimaryKeyJoinColumn
var todo: Todo
```

```kotlin
@OneToOne
@MapsId
@JoinColumn(name = "id")
var pendency: Pendency
```

#### Join Table Method

```kotlin
@OneToOne
@JoinTable(
	name = "todo_pendency",
	joinColumns = [JoinColumn(name = "pendency_id",
														referencedColumnName = "id")],
	inverseJoinColumns = [JoinColumn(name = "todo_id",
																	 referencedColumnName = "id")]
)
var todo: Todo
```

```kotlin
@OneToOne(mappedBy = "todo")
var pendency: Pendency
```

### How to deal with recursion

#### Ignoring the Field

```kotlin
@JsonIgnore
var todo: Todo
```
