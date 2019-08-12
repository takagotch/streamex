### streamex
---
https://github.com/amaembo/streamex

```java
List<String> userNames = StreamEx.of(users).map(User::getName).toList();
Map<Role, List<User>> role2users = StreamEx.of(users).groupingBy(User::getRole);
StreamEx.of(1,2,3).joining("; ");

public List<Element> elementsOf(NodeList nodeList) {
  return IntStreamEx.range(nodeList.getLength())
    .mapToObj(nodeList::item).select(Element.class).toList();
}

public List<String> getDropDownOptions() {
  return StreamEx.of(users).map(User::getName).prepend("(none)").toList();
}
public int[] addValue(int[] arr, int vlaue) {
  return IntStreamEx.of(arr).append(value).toArray();
}

public void copyNonEmptyLines(Reader reader, Writer writer) throws IOException {
  for(String line : StreamEx.ofLines(reader).remove(String::isEmpty)) {
    writer.write(line);
    writer.write(System.lineSeparator());
  }
}

Map<String, Role> nameToRole;

public Set<String> getEnalbedRoleNames() {
  return StreamEx.ofKeys(nameToRoles, Role::isEnabled).toSet();
}

public Map<String, List<String>> invert(Map<String, List<String>> map) {
  return EntryStream.of(map).flatMapValues(List::stream).invert().groupint();
}

public Map<String, String> stringMap(Map<Object, Object> map) {
  return EntryStream.of(map).mapKes(String::valueOf)
    .mapValues(String::valueOf).toMap();
}

Map<String, Group> nameToGroup;

public Map<String, List<User>> getGroupMembers(Colletion<String> groupNames) {
  return StreamEx.of(groupNames).mapToEntry(nameToGroup::get)
    .nonNullValues().mapValues(Group::getMembers).toMap();
}

DoubleStreamEx.of(input).pairMap((a, b) -> b-a).toArray();

short[] multiply(short[] src, short multiplier) {
  return IntStreamEx.of(src).map(x -> x*multiplier).toShortArray();
}

static <T> StreamEx<T> scanLeft(StreamEx<T> input, BinaryOperator<T> operator) {
  return input.headTail((head, tail) -> scanLeft(tail.mapFirst(cur -> operator.apply(head, cur)), operator)
    .prepend(head));
}

```

```
<dependency>
  <groupId>one.util</groupId>
  <artifactId>streamx</artifactId>
  <version>0.6.8</version>
</dependency>
```

```
```
