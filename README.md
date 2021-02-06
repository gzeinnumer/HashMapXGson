# HashMapXGson
 
```gradle
implementation 'com.google.code.gson:gson:2.8.5'
```

```java
//create test hashmap
HashMap<String, String> testHashMap = new HashMap<String, String>();
testHashMap.put("key1", "value1");
testHashMap.put("key2", "value2");

//convert to string using gson
Gson gson = new Gson();
String hashMapString = gson.toJson(testHashMap);

//save in shared prefs
SharedPreferences prefs = getSharedPreferences("test", MODE_PRIVATE);
prefs.edit().putString("hashString", hashMapString).apply();

//get from shared prefs
String storedHashMapString = prefs.getString("hashString", "oopsDintWork");
java.lang.reflect.Type type = new TypeToken<HashMap<String, String>>() {
}.getType();
HashMap<String, String> testHashMap2 = gson.fromJson(storedHashMapString, type);

//use values
String toastString = testHashMap2.get("key1") + " | " + testHashMap2.get("key2");
Toast.makeText(this, toastString, Toast.LENGTH_LONG).show();
```

---

```
Copyright 2021 M. Fadli Zein
```