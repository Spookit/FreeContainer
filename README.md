# FreeContainer
Get things in easy way

## Usage
```java
// the configuration source
final YamlConfiguration config = new YamlConfiguration();

// result Map
final Map<String, List<Integer>> result = new HashMap<>();

// processing
for (final Map<?, ?> m : config.getMapList("customObjects")) {
	final FreeMap map = new FreeMap(m, true); // safe Mode without computing
	final String name = map.getString("name");
	final FreeList objects = map.getList("ids");
	final List<Integer> newList = new ArrayList<>();
	for (int i = 0; i < objects.size(); i++) {
		final int id = objects.getI(i);
		newList.add(id);
	}
	result.put(name, newList);
}
```
