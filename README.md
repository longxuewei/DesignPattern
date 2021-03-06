# **设计模式**

### 这里是本人日常工作和学习书本上面知识所摘录的一些知识,希望大家一起学习,如有不对敬请指出,大家共同学习!

## 单例设计模式

![image](https://github.com/longxuewei/DesignPattern/blob/master/image/Single.png?raw=true)

    public class Demo{
    	private static Demo instance;
    	private Demo(){
    		throw new Exception("不能new实例哦");
    	}
    	public static Demo getInstance(){
    		if(instance==null){
    			instance = new Demo();
    		}
    		return instance;
    	}
    }


> 上面的例子是一个饿汉式的写法, 是线程不安全的.如果需要安全的可以使用加锁!

> **优点: 整个对象在内存中只有一个实例,避免了多次new和gc 所产生的内存开销!**


> **缺点: 对测试不利,不利于扩展**

> android 中需要注意的是尽量用getApplication()的Context来初始化 工具类 这样可以避免内存泄露!