# Hash
## Hash Map
#### HashMap 是一个散列表，它存储的内容是键值(key-value)映射。</b>
#### HashMap 的 key 与 value 类型可以相同也可以不同，根据定义，不受限制。</b>

### 1.定义哈希表
```Java
    HashMap<Integer, String> hashmap= new HashMap<Integer, String>();
```

### 2.添加键值对（key-value）（增）
```Java
    hashmap.put(1, "string1"); // 执行完后hash表内为{1=string1}
    hashmap.put(2, "string2"); // 执行完后hash表内为{1=string1, 2=string2}
    hashmap.put(2, "string2"); // 执行完后hash表内为{1=string1, 2=string2, 3=string3}
```

### 3.添根据key值访问value（查）
```Java
    hashmap.get(1); // 返回string1
    hashmap.get(2); // 返回string2
    hashmap.get(3); // 返回string3
```

### 4.添加键值对（key-value）（增）
```Java
    hashmap.remove(1); // 执行完后hash表内为{2=string2, 3=string3}
    hashmap.remove(2); // 执行完后hash表内为{3=string3}
    hashmap.remove(3); // 执行完后hash表内为{}
    // 删除所有键值对
    hashmap.clear();
```

### 5.替换 hashMap 中是指定的key对应的 value
```Java
    hashmap.replace(key,value); // 返回0
```

### 6.返回hashmap中键值对的数量
```Java
    hashmap.size(); // 返回0
```

### 7.getOrDefault(Object key, V defaultValue)
<b>意思就是当Map集合中有这个key时，就使用这个key对应的value值，如果没有就使用默认值defaultValue；
```Java
    hashmap.getOrDefault(key,defaultValue);
```

### 8.entrySet() 方法
<b>可以与 for-each 循环一起使用，用来遍历迭代 HashMap 中每一个映射项
```Java
    // foreach循环
    for(var entry : map.entrySet()){
        // 获得key
        int key = entry.getKey();
        // 获得value
        int value = entry.getValue();
    }
```

### 9.检查hashMap中是否存在指定的key对应的映射关系
```Java
    hashmap.containsKey(key); 
```

### 10.检查hashMap中是否存在指定的value对应的映射关系
```Java
    hashmap.containsValue(value); 
```

### 11.hashmap是否为空
```Java
    hashmap.isEmpty(); 
```

### 12.HashMap.values() 方法
```Java
    hashmap.values(); // 返回所有Value值组成的集合
    /*
	    如果有HashMap: {1=Google, 2=Runoob, 3=Taobao}
	    则返回Values: [Google, Runoob, Taobao]
    */
```
### Hash Set
<b>HashSet是基于HashMap的一个不允许有重复元素的集合，但其中允许存在null值。

### 1.定义一个hashset
```Java
    Set<Integer> hashset= new HashSet<Integer>();
```

### 2.添加值（增）
```Java
    hashset.add(1);
    /*迭代存入元素
        int[] nums = new int[]{1,2,3,4,5,6}
        for(int x : nums) hash.add(x);
     */
```

### 3.判断元素是否存在
```Java
    hashmap.contains(1);
```

### 4.删除元素（删）
```Java
    hashmap.remove(1);
    // 删除所有元素
    hashmap.clear();
```

### HashSet如何实现去重
#### HashSet是通过HashCode()与equals()方法实现去重的。

HashCode()的作用是对Java堆上的对象产生一个哈希码，用于确定该对象在哈希表中的索引位置，Java的任何类中都含有HashCode()。
equals()方法用于比较两个对象中存放的地址是否相等。
对象加入HashSet的过程：对象加入HashSet时，HashSet会计算对象的hashcode值来判断对象加入的位置，如果该位置没有值，则直接放入；如果有值，则HashSet通过equals()方法来检查两个对象是否相同，如果两者相同，则加入失败，否则将会重新散列到其他的地方。

#### 注意：

两个对象相等，也就是适用于equals(java.lang.Object) 方法，那么这两个对象的hashCode一定要相等；
hashcode相等，两个对象不一定相等
