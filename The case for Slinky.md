# The case for [[Slinky]]

Considering the following entity;

```kt
@Entity
@Table(name = "todos")
data class Todo(
	@Id
	@GeneratedValue(strategy = GenerationType.AUTO)
	override var id: Long?,
	var name: String?,
	var description: String?,
	var completed: Boolean?
) : IGenericEntity<Long>
```

You can go from

```kt
@Repository
interface TodoRepository: JpaRepository<Todo, Long>
```

```kt
```

```kt
```

to:

```kt
@Repository
class TodoRepository(entityManager: EntityManager)
: GenericRepository<Todo, Long>(Todo::class.java, entityManager)
```

```kt
@Service
class TodoBusiness(repository: TodoRepository)
: GenericBusiness<Todo, Long>(repository)
```

```kt
@RestController
@RequestMapping("/api/v1/todos")
class TodoController(business: TodoBusiness)
: GenericController<Todo, Long>(business)
```