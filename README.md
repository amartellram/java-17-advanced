# Notes about Java 17 Advances features Course in Pluralsight

https://app.pluralsight.com/library/courses/java-se-17-advanced-language-features/

## 01. Record

## 02. Sealed classes and interfaces

## 03. Advances classes and interfaces

## 04. Advances Generics

### Type Erasure

### Limitations caused by type erasure

* You can not use **primitive types** as type arguments, because primitive types are not objects.
* It is not possible to create a new instance of a type parameter.

```java
new T() // Error

Class<T> cls = ....;
var obj = cls.getDeclaredConstructor().newInstance();
```

* instanceof does not work non-reifiable types (a type which type information is lost during type erasure).
  Parameterized types with at least one concrete or bounded wildcard type argument.

```java
obj instanceof List<String> //Error
obj instance of List<?> //OK
```

* Operations where **type safety** cannot be guaranteed cause **unchecked** warnings.
* You cannot **overload methods** with the same **method signature**
* after type erasure.

```java
void print(List<String> strings)
void print(List<Integer> integers)
```

### Heap pollution

## 05. Lambda Expression and Method References

## Annotations

## Optional

## Try-with-resources and AutoCloseable
