## 在activity之间传递信息

### 核心函数

```
//发送数据
Intent intent=new Intent(this,SecondActivity.class);
intent.putExtra("book","string");
startActivity(intent);

//接受数据
String name = intent.getStringExtra("name");
int age = intent.getIntExtra("age");
```

