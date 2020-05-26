## `Jackson`

### 简介

Jackson 是一个能够将java对象序列化为JSON字符串，也能够将JSON字符串反序列化为java对象的框架



### 参考链接

http://www.studytrails.com/java/json/java-jackson-introduction/



### 序列化方式

1. JSON <--> Java Object 

2. JSON <--> JsonNode Tree（类似于XML的DOM树）

3. JSON <--> Json Stream （这是一个低层次的api，很强大，但是很繁琐）



### JAR包下载链接

jar包下载地址

https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-annotations

https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-core

https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind

### 在AS中使用步骤

1. 下载`jackson-all-***.jar`包并导入工程

```
private void serializeTest(String returnValue){
        SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd");
        try{
//            Date birth = format.parse("2010-10-10");
//            Person person = new Person("zhangsan",11,birth,"weiying","caifang");
//            person.info.put("height","175cm");
//            person.info.put("weight","80kg");

            ObjectMapper mapper = new ObjectMapper();
            mapper.configure(SerializationFeature.INDENT_OUTPUT,true);
            mapper.setDateFormat(format);
            mapper.configure(SerializationFeature.ORDER_MAP_ENTRIES_BY_KEYS,true);

//            String personJson = mapper.writeValueAsString(person);
//            System.out.println(personJson);
//
//            Person p = mapper.readValue(personJson,Person.class);
//            System.out.println(person.toString());
            DailyPush d = mapper.readValue(returnValue,DailyPush.class);
            System.out.println(d.toString());
        }
//        catch (ParseException e){
//            e.printStackTrace();
//        }
        catch (JsonProcessingException e){
            e.printStackTrace();
        }


    }
```



