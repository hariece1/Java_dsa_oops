Map is set of key value pair
Basics

```java

HashMap<String, Integer> map = new HashMap<>();
map.put("Hari", 91);
map.put ("Hari v",93);
System.out.println(map.get("Karan"));
System.out.println(map.getOrDefault("Rahul",99));
sout(map.containsKey("Hari"));
HashSet<Integer> set = new Hashset<>();
set.add(24);
set.add(23);
set.add(23);
set.add(12);
```

Implementation

```
class MapusingHash{
		private Entity[] entities;
		
}
```

Hashmaps first unique character return index

```java
class Solution {
    public int firstUniqChar(String s) {
        HashMap<Character,Integer> list = new HashMap<>();
        for(int i=0;i<s.length();i++){
            char ch = s.charAt(i);
            if(list.containsKey(ch)){
                list.put(ch,list.get(ch) + 1);
            }else{
                list.put(ch,1);
            }
        }
        for(int i=0;i<s.length();i++){
            char ch = s.charAt(i);
            if(list.get(ch) ==1){
                return i;
            }
        }
        return -1;
    }
}
```
