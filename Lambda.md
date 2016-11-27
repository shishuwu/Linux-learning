# Lambda Learning
## lambda 表达式
### 概念
* 它是一个**匿名函数** （非类的写法）
* 任何**函数式接口**都可以使用**lambda表达式替换**
	* ActionListener
	* Comparator
	* Runnable



> Note:
>
> - 函数式接口 @FunctionalInterface，并只有一个方法（java8 default/static/Object 方法除外）
> - 替换：即 用简单的lambda表达式替代**匿名内部类**的实现
> - 在Java 8之前，如果想将行为传入函数，仅有的选择就是匿名类: 可见**匿名类是用来当方法传递的**

### 基本语法
3部分，即: 参数列表，箭头（->），以及一个表达式或语句块。

	(parameters) -> expression

	或

	(parameters) ->{ statements; } 

	e.g.:
	(int x, int y) -> x + y;

## 用途
### 优点
* 替代**匿名内部类**
* 代码少

### 缺点
* 学习曲线

---
---
# 方法引用

##静态方法引用：ClassName::methodName 
##实例上的实例方法引用：instanceReference::methodName 
##超类上的实例方法引用：super::methodName 
##类型上的实例方法引用：ClassName::methodName 
##构造方法引用：Class::new 
##数组构造方法引用：TypeName[]::new


	public class TestDemo {
	    @Test
	    public void testStaticMethodRef() {
	        // static method ref (BOTH: input & output)
	        Function<Integer, String> sr = String::valueOf;
	        String str = sr.apply(100);
	        assertEquals("100", sr.apply(100));
	    }
	
	    @Test
	    public void testInstanceRef() {
	        // instance method ref (only: output)
	        Supplier<String> mr = "abc"::toUpperCase;
	        assertEquals("ABC", mr.get());
	    }
	
	    @Test
	    public void testMultipeParams() {
	        // bi
	        BiFunction<String, String, Integer> bfr = String::compareTo;
	        int result2 = bfr.apply("A", "B");
	        assertEquals(-1, result2);
	    }
	
	    @Test
	    public void testConstructRef() {
	        BiFunction<Long, String, Message> constructFunc = Message::new;
	        Message msg = constructFunc.apply(1L, "this is a message");
	
	        assertEquals(1L, (long) msg.getId());
	        assertEquals("this is a message", msg.getName());
	    }
	
	
	    @Data
	    @AllArgsConstructor
	    class Message {
	        public Long id;
	        public String name;
	    }
	}

---
---
# Stream
## 概念
可以支持**顺序**和**并行**对元素操作的元素集合。

	  List<Shape> shapes = ...
	    shapes.stream()
	      .filter(s -> s.getColor() == BLUE)
	      .forEach(s -> s.setColor(RED));

## 如何使用
Collection 转换成 stream

## 常见*中间*方法
1. Filter（过滤）
2. Map(对元素进行操作)
3. limit(截断)
4. distinct(去重)

## 常见*终点*方法
1. count(统计) 
2. Collect(收集流的结果) 

## 顺序流 & 并行流
1. .stream()
2. .parallelStream()