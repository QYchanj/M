一、php一般的变量是不需要声明变量的（弱类型），要用的时候直接$接上参数
       但是php的函数内要用全局变量时要在函数内先用blobal声明变量
       global $x或者用$GLOBALS[ ' 参数名 ']
       参数没有赋值时运行结果是不会显示的
二、echo 和 print :可加括号也可不加，输出的字符串内容里可以包括html标签
echo - 可以输出一个或多个字符串
                   echo "这是一个", "字符串，", "使用了", "多个", "参数。"
print - 只允许输出一个字符串，返回值总为 1
echo 输出的速度比 print 快， echo 没有返回值，print有返回值1。

三、类型比较
   ==和=== ，!=和!==
松散比较：使用两个等号 == 比较，只比较值，不比较类型。
严格比较：用三个等号 === 比较，除了比较值，也比较类型。
四、字符串和数值是分开的，字符串是一种类型，可以赋值给一个变量，数组也可以
五、常量:和C的宏定义常量一样
       区别:不能在常量名前添加$ 符号，不然会将常量转换成新的未定义变量使用会报错。
       <?php
        define('LOG','OPEN');
       echo LOG;
      ?>
六、比较运算符<=>
      $c = $a <=> $b;
        如果 $a > $b, 则 $c 的值为 1。
       如果 $a == $b, 则 $c 的值为 0。
       如果 $a < $b, 则 $c 的值为 -1。
七、由于php的字符串不是归于数组而是由专门的字符串变量，所以switch语句中的变量可以是
       字符串变量，值也可以是字符串
八、同一个数组内的数组元素可以是不同类型的，数组元素甚至可以放一个对象和一个数组
             $cars=array("volvo","BMW",5,$arr);
九、关联数组：
      $age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
or:
$age['Peter']="35";
$age['Ben']="37";
$age['Joe']="43";
'peter'叫做键，关联数组就是使用分配给指定的键的数组
         foreach函数：仅能够应用于数组和对象
      该函数两种形式（as后面的参数都是类似形参的东西，前面的数组或对象的值赋给这些参数，指
        针就指向下一个单元，然后花括号里面就可以进行echo或者其他操作）：
       1.foreach(被foreach的对象（一般是数组）as 内容){ }
      foreach($a as $value){ }   $a是声明过的存在的数组，$value是一个类似形参的东西
2.foreach(被foreach的对象（一般是数组）index => 内容){ }
foreach($a as $key=>$value) 这种形式涉及遍历数组，$key对应键，$value对应键
对应的值
十、自 5.4 起可以使用短数组定义语法，直接用 [ ] 替代 array() 。
十一、 PHP 数组排序函数：
sort() - 对数组进行升序排列  字母或数字的值
rsort() - 对数组进行降序排列
asort() - 根据关联数组的值，对数组进行升序排列    
ksort() - 根据关联数组的键，对数组进行升序排列    字母的顺序
arsort() - 根据关联数组的值，对数组进行降序排列
krsort() - 根据关联数组的键，对数组进行降序排列   字母的顺序
十二、php的自定义函数:  function 函数名($a,$b){   }
        没有了函数类型，有返回值的函数直接用return函数就行了 
        调用时可以不用实参，直接将数据'XX'代替参数$a(但定义时要用形参定义)
十三、类和对象:类就是自定义框架，对象就是类的实例
 类的关键词class,类的参数关键词var,类的函数关键词funtion
 类的函数只能在该类里面调用，类的函数调用类的参数$this->参数
创建对象$A=new 类
引用对象的参数或函数$A->参数/函数
php构造函数:funtion __construct($A,$B){$this->C=$A}   构造函数用于对象内，$this引用对
              象内的参数$C，而$A是自动将对象构建时的参数传入，从而实现创建对象时直接对参数赋
              值的功能：
              $China=new country('XXX','XX')  (其中XXX是$A的内容，XX是$B的内容)
php析构函数:funtion __destruct(本函数不能带参数){  }  本函数在对象被销毁时调用
php的封装性:
      1、public 公共方法，在类的内部和实例化调用都可以使用，包括继承内部及其继承后实例化都可以使用。
      2、protected 受保护方法，在类内部可以使用，继承内部可以使用，但是实例化之后不可以调用。
      3、private 私有方法 ，只能在类内部调用，实例化后不可调用，继承内部不可调用。
接口:关键词interface，定义的函数都为空内容
interface A(接口名)
{
    public function B($name, $var);
    public function C($template);
}
类中必须实现接口中定义的所有方法，要实现一个接口，使用 implements 操作符:
class B(类名) implements A
{
    private $vars = array();
    public function setVariable($name, $var)
    {
        $this->vars[$name] = $var;
    }
    public function getHtml($template)
    {
        foreach($this->vars as $name => $value) {
            $template = str_replace('{' . $name . '}', $value, $template);
        }
        return $template;
    }
}
可以把在类中始终保持不变的值定义为常量。在定义和使用常量的时候不需要使用 $ 符号:
class MyClass
		{
    		const constant = '常量值';
   		 function showConstant() {
      		  echo  self::constant . PHP_EOL;  //(::静态调用静态参数)
    		}
		}
抽象类
类继承:(继承后可扩展)
  class Child extends parent {
   	var $category;
    	function setCate($par){
        $this->category = $par;
    	}
	function getCate(){
        echo $this->category . PHP_EOL;
   	}
	}
    类的参数、方法重写:直接按同名的重新定义就好了
static关键词:
声明类的属性或方法为 static(静态)，就可以不实例化类而直接访问:
                       (访问Foo类的参数) print Foo::$my_static . PHP_EOL;
静态属性不能通过一个类已实例化的对象来访问（但静态方法可以）:
                 				$foo = new Foo();
						print $foo->staticValue() . PHP_EOL;
由于静态方法不需要通过对象即可调用，所以伪变量 $this 在静态方法中不可用。
静态属性不可以由对象通过 -> 操作符来访问而用::
final关键词:
父类中的方法被声明为 final，则子类无法覆盖该方法。如果一个类被声明为 
final，则不能被继承。
十四、php的引用:&
$a=&$b   使$a和$b指向同一块数据  改变a同时改变b，改变b同时改变a
对象也能引用:

十五、魔术常量:
__line__  显示代码所在的行
__file__   显示文件绝对路径
__dir__   显示文件所在目录
__funtion__    显示所在方法名
__class__    显示类名
__method__  显示类的方法名
__namespace__  显示命名空间的名称
trait：
   trait A{funtion1 .....
              funtion2 .....}
   class B{use A；
               /*则B内相当于有了A的代码*/}
十六、命名空间:定义关键词namespace
namespace myproject;定义之后的代码均属于myproject空间的(一般后面接花括号)
全局非命名空间则直接namespace{}不加空间名字
子命名空间:namespace MyProject\Sub\Level就是namespaceMyProject\Sub子命名
空间 
命名空间访问的类型(涉及子命名空间)：假设有A、B文件夹里面都有C文件夹和D文件
非限定名称(类似当前文件):现在在B文件夹内，我访问B文件夹里面的D文件则直接访问D
限定名称(使用命名空间前缀):现在在B文件夹内，我访问B文件夹里面的C文件夹内的文
件，则访问C\E
完全限定名称(从根空间/全局空间开始查找):现在在B文件夹内，我访问A文件夹里面的C文
件夹内的文件，则访问\A\C\F
命名空间别名/导入:
use dog\life as dog   直接用dog相当于使用dog\life
use dog\life             相当于use dog\life as life