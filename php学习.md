### php学习

#### **简单**的介绍

##### **1.EOF**

##### 用来定界，格式化一段文本

```php
<?php
$name="runoob";
$a= <<<EOF
        "abc"$name
        "123"
EOF;
// 结束需要独立一行且前后不能空格
echo $a;
?>
```

##### **2.PHP变量

##### **以$开始**，后面跟变量的名字/函数访问全局变量要用global//有$GLOBALS[*index*] ，php将全部存储在这一个数组之中

```php
<?php
$x=5; // 全局变量

function myTest()
{
    $y=10; // 局部变量
    echo "<p>测试函数内变量:<p>";
    echo "变量 x 为: $x";
    echo "<br>";
    echo "变量 y 为: $y";
} 

myTest();

echo "<p>测试函数外变量:<p>";
echo "变量 x 为: $x";
echo "<br>";
echo "变量 y 为: $y";
?>
```

##### **3.PHP中var_dump(**)

##### (https://www.runoob.com/php/php-var_dump-function.html) 方法，判断一个变量的类型与长度，并输出变量的数值，如果变量有值，则输出是变量的值，并返回数据类型。显示关于一个或多个表达式的结构信息，包括表达式的类型与值。数组将递归展开值，通过缩进显示其结构。

```php
<?php 
$x = 10.365;
var_dump($x);
echo "<br>"; 
$x = 2.4e3;
var_dump($x);
echo "<br>"; 
$x = 8E-5;
var_dump($x);
?>
```

##### **4.PHP数组**

```php
<?php 
$cars=array("Volvo","BMW","Toyota");
var_dump($cars);
?>
```

##### **5.PHP对象**：class声明类对象，var定义变量

```php
<?php
class Car
{
  var $color;
  function __construct($color="green") {
    $this->color = $color;
  }
  function what_color() {
    return $this->color;
  }
}
?>
```

##### **6.PHP常量**：

###### （1）使用define函数设置

```php
bool define ( string $name , mixed $value [, bool $case_insensitive = false ] )

注：case_insensitrive是对大小写敏感否false默认敏感
```

###### （2）实例

```php
<?php
// 区分大小写的常量名
define("GREETING", "欢迎访问 Runoob.com");
echo GREETING;    // 输出 "欢迎访问 Runoob.com"
echo '<br>';
echo greeting;   // 输出 "greeting"，但是有警告信息，表示该常量未定义
?>
```

##### **7.PHP字符串**:

###### （1）strlen函数，统计字符串的长度

###### （2）strops函数：用于字符串内查找一个字符或一段指定的文本

```php
<?php
echo strpos("Hello world!","world");
?>
ps：最终结果返回6
```

##### **8.PHP运算符**：

###### （1）运算符![image-20220226132314967](C:\Users\92485\AppData\Roaming\Typora\typora-user-images\image-20220226132314967.png)

###### （2）比较运算符![image-20220226132437636](C:\Users\92485\AppData\Roaming\Typora\typora-user-images\image-20220226132437636.png)注意绝对等于

###### （3）逻辑运算符![image-20220226132545904](C:\Users\92485\AppData\Roaming\Typora\typora-user-images\image-20220226132545904.png)

###### （4）数组运算符![image-20220226132737407](C:\Users\92485\AppData\Roaming\Typora\typora-user-images\image-20220226132737407.png)

###### （5）三元运算符：“（exp1）？（exp2）：（exp3）”

```php
<?php
$test = '菜鸟教程';
// 普通写法
$username = isset($test) ? $test : 'nobody';
echo $username, PHP_EOL;
 
// PHP 5.3+ 版本写法
$username = $test ?: 'nobody';
echo $username, PHP_EOL;
?>
最终判断是否有值，没有返回nobody
    
//PHP7版本
<?php
// 如果 $_GET['user'] 不存在返回 'nobody'，否则返回 $_GET['user'] 的值
$username = $_GET['user'] ?? 'nobody';
// 类似的三元运算符
$username = isset($_GET['user']) ? $_GET['user'] : 'nobody';
?>

```

###### （6）组合比较符：$c = $a <=> $b;其中<代表-1，=代表0，>代表1

```php
<?php
// 整型
echo 1 <=> 1; // 0
echo 1 <=> 2; // -1
echo 2 <=> 1; // 1
 
// 浮点型
echo 1.5 <=> 1.5; // 0
echo 1.5 <=> 2.5; // -1
echo 2.5 <=> 1.5; // 1
 
// 字符串
echo "a" <=> "a"; // 0
echo "a" <=> "b"; // -1
echo "b" <=> "a"; // 1
?>
```

##### **9.PHP -if elseif else语句**

```
if (条件)
{
    if 条件成立时执行的代码;
}
elseif (条件)
{
    elseif 条件成立时执行的代码;
}
else
{
    条件不成立时执行的代码;
}
```

##### **10.PHP Switch语句**

```php
<?php
switch (n)
{
case label1:
    如果 n=label1，此处代码将执行;
    break;
case label2:
    如果 n=label2，此处代码将执行;
    break;
default:
    如果 n 既不等于 label1 也不等于 label2，此处代码将执行;
}
?>
```

##### **11.PHP数组**

###### （1）创建并打印

```php
`<?php`
`$cars=array("Volvo","BMW","Toyota");`
`echo "I like " . $cars[0] . ", " . $cars[1] . " and " . $cars[2] . ".";`
`?>`


```

###### （2）count函数，获取长度

```php
<?php
$cars=array("Volvo","BMW","Toyota");
echo count($cars);
?>
```

###### （3）遍历数值数组

```php
<?php
$cars=array("Volvo","BMW","Toyota");
$arrlength=count($cars);
 
for($x=0;$x<$arrlength;$x++)
{
    echo $cars[$x];
    echo "<br>";
}
?>
```

###### （4）关联数组

```php
1.创建
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
//
$age['Peter']="35";
$age['Ben']="37";
$age['Joe']="43";
```

```php
2.遍历关联数组
<?php
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");
 
foreach($age as $x=>$x_value)
{
    echo "Key=" . $x . ", Value=" . $x_value;
    echo "<br>";
}
?>
```

##### **12.PHP数组排序**

- sort() - 对数组进行升序排列
- rsort() - 对数组进行降序排列
- asort() - 根据关联数组的值，对数组进行升序排列
- ksort() - 根据关联数组的键，对数组进行升序排列
- arsort() - 根据关联数组的值，对数组进行降序排列
- krsort() - 根据关联数组的键，对数组进行降序排列

##### **13.PHP超级全局变量**

- $GLOBALS
- $_SERVER
- $_REQUEST
- $_POST
- $_GET
- $_FILES
- $_ENV
- $_COOKIE
- $_SESSION
- [PHP 超级全局变量 | 菜鸟教程 (runoob.com)](https://www.runoob.com/php/php-superglobals.html)

##### 14.PHP 循环

###### （1）while实例，与do...while类似

```php
<?php
$i=1;
while($i<=5)
{
    echo "The number is " . $i . "<br>";
    $i++;
}
?>
```

###### （2）for实例

```php
<?php
for ($i=1; $i<=5; $i++)
{
    echo "数字为 " . $i . PHP_EOL;
}
?>
```

###### （3）foreach实例

主要用来遍历数组，$value是要用来

```php
<?php
$x=array("Google","Runoob","Taobao");
foreach ($x as $value)
{
    echo $value . PHP_EOL;
}
?>
```

##### **15.PHP函数**

###### （1）创建函数

```php
<?php
function functionName()
{
    // 要执行的代码
}
?>
```

###### （2）创建函数添加参数

```php
<?php
function writeName($fname)
{
    echo $fname . " Refsnes.<br>";
}
 
echo "My name is ";
writeName("Kai Jim");
echo "My sister's name is ";
writeName("Hege");
echo "My brother's name is ";
writeName("Stale");
?>
```

###### （3）返回值

类似c语言

```php
<?php
function add($x,$y)
{
    $total=$x+$y;
    return $total;
}
 
echo "1 + 16 = " . add(1,16);
?>
```

##### 16.PHP魔术常量

即PHP提供了大量的预先定义好的常量

```PHP
<?php
echo '该文件位于 " '  . __FILE__ . ' " ';
?>
```

即会输出该文件的路径。诸如此类的定义好的常量（均为大写）😂

##### 17.PHP命名空间

暂时不想看，以后需要再去看

##### 18.面向对象

###### （1）类定义

```PHP
<?php
class Site {
  /* 成员变量 */
  var $url;
  var $title;
  
  /* 成员函数 */
  function setUrl($par){
     $this->url = $par;//this代表自身的对象
  }
  
  function getUrl(){
     echo $this->url . PHP_EOL;
  }
  
  function setTitle($par){
     $this->title = $par;
  }
  
  function getTitle(){
     echo $this->title . PHP_EOL;
  }
}
?>
```

###### （2）创建对象

new运算符来实例化该类的对象

```
$runoob = new Site;
$taobao = new Site;
$google = new Site;
```

###### （3）调用类的函数成员

```php
// 调用成员函数，设置标题和URL
$runoob->setTitle( "菜鸟教程" );
$taobao->setTitle( "淘宝" );
$google->setTitle( "Google 搜索" );

$runoob->setUrl( 'www.runoob.com' );
$taobao->setUrl( 'www.taobao.com' );
$google->setUrl( 'www.google.com' );

// 调用成员函数，获取标题和URL
$runoob->getTitle();
$taobao->getTitle();
$google->getTitle();

$runoob->getUrl();
$taobao->getUrl();
$google->getUrl();
```

###### （4）构造函数

为初对象成员赋初始值

```php
function __construct( $par1, $par2 ) {
   $this->url = $par1;
   $this->title = $par2;
}
////
$runoob = new Site('www.runoob.com', '菜鸟教程');
$taobao = new Site('www.taobao.com', '淘宝');
$google = new Site('www.google.com', 'Google 搜索');
```

###### （5）析构函数

当对象结束其生命周期时（或是调用完毕），系统自动执行析构函数

```php
<?php
class MyDestructableClass {
   function __construct() {
       print "构造函数\n";
       $this->name = "MyDestructableClass";
   }

   function __destruct() {
       print "销毁 " . $this->name . "\n";
   }
}

$obj = new MyDestructableClass();
?>
```

###### （6）方法重写

当父类的继承无法满足子类的需求，可以改写，然后覆盖

```php
function getUrl() {
   echo $this->url . PHP_EOL;
   return $this->url;
}
   
function getTitle(){
   echo $this->title . PHP_EOL;
   return $this->title;
}
```

###### （7）访问控制

在最前面添加关键词

1.public   ：类成员在任何地方都可以被访问	

2.protected   ：受保护的类成员可以被自身以及父类和子类访问

3.private ：只能在被定义的类里面访问

###### （8）接口

通过interface定义接口，里面定义的方法必须是共有。在类中必须实现接口所定义的所有方法

###### （9）常量

把类中始终保持不变的值定义为常量。在定义和使用的时候不需要使用$符号，直接const a=1

#### PHP表单

##### 1.PHP表单和用户输入

###### （1）处理来自HTML的表单时，能够把表单元素变成PHP脚本去使用的参量（举例为POST传参）

###### （2）检验用户输入

```php
$q = isset($_POST['q'])? $_POST['q'] : '';
//检验是否已经传参
```

###### （3）表单写法

```php
<?php
$q = isset($_POST['q'])? $_POST['q'] : '';
if(is_array($q)) {
    $sites = array(
            'RUNOOB' => '菜鸟教程: http://www.runoob.com',
            'GOOGLE' => 'Google 搜索: http://www.google.com',
            'TAOBAO' => '淘宝: http://www.taobao.com',
    );
    foreach($q as $val) {
        // PHP_EOL 为常量，用于换行
        echo $sites[$val] . PHP_EOL;
    }
      
} else {
?>
//下方为表单***********************
<form action="" method="post"> 
    <select multiple="multiple" name="q[]">
    <option value="">选择一个站点:</option>
    <option value="RUNOOB">Runoob</option>
    <option value="GOOGLE">Google</option>
    <option value="TAOBAO">Taobao</option>
    </select>
    <input type="submit" value="提交">
    </form>
//上方为表单***************************
<?php
}
?>
```



###### （4）区别$_GET,$_POST,$_REQUEST

​          get:用get方式发送的请求和URL上？后面的内容

​		  post：以post发送的请求，例如一个form以method=post提交

​		  request：两种方式的请求都支持，get有字符数限制，post无

##### 2.PHP表单验证

对用户所提交的数据通过PHP的htmlspercialchars()函数处理

在用户提交表单的时候要用PHP trim函数去除不必要字符，再用stripslasher（）函数去除反斜杠

```php
<?php
// 定义变量并默认设置为空值
$name = $email = $gender = $comment = $website = "";
 
if ($_SERVER["REQUEST_METHOD"] == "POST")
{
  $name = test_input($_POST["name"]);
  $email = test_input($_POST["email"]);
  $website = test_input($_POST["website"]);
  $comment = test_input($_POST["comment"]);
  $gender = test_input($_POST["gender"]);
}
 
function test_input($data)
{
  $data = trim($data);
  $data = stripslashes($data);
  $data = htmlspecialchars($data);
  return $data;
}
?>
```

##### 3.PHP表单-必需字段

上一个实例看，输入字段可选，我会将代码加入一些新变量$nameerr,$emailerr等等设定为""

##### 4.验证邮件和URL

验证名称

```php
$name = test_input($_POST["name"]);
if (!preg_match("/^[a-zA-Z ]*$/",$name)) {
  $nameErr = "只允许字母和空格"; 
}
//验证name是否包含字母和空格
```

验证邮件

```php
$email=test_input($_POST["email"]);
if (!preg_match("/([\w\-]+\@[\w\-]+\.[\w\-]+)/",$email)) {
  $emailErr = "非法邮箱格式"; 
}
```

验证URL

```php
$website = test_input($_POST["website"]);
if (!preg_match("/\b(?:(?:https?|ftp):\/\/|www\.)[-a-z0-9+&@#\/%?=~_|!:,.;]*[-a-z0-9+&@#\/%=~_|]/i",$website)) {
  $websiteErr = "非法的 URL 的地址"; 
}
```

和客户端进行交互提取的一个代码举例

```php
if ($_SERVER["REQUEST_METHOD"] == "POST") {
   if (empty($_POST["name"])) {
      $nameErr = "Name is required";
      } else {
         $name = test_input($_POST["name"]);
         // 检测名字是否只包含字母跟空格
         if (!preg_match("/^[a-zA-Z ]*$/",$name)) {
         $nameErr = "只允许字母和空格"; 
         }
     }
```

##### 5.完整表单实例

```php
<form method="post" action="<?php echo htmlspecialchars($_SERVER["PHP_SELF"]);?>"> 
   名字: <input type="text" name="name" value="<?php echo $name;?>">
   <span class="error">* <?php echo $nameErr;?></span>
   <br><br>
       
   E-mail: <input type="text" name="email" value="<?php echo $email;?>">
   <span class="error">* <?php echo $emailErr;?></span>
   <br><br>
       
   网址: <input type="text" name="website" value="<?php echo $website;?>">
   <span class="error"><?php echo $websiteErr;?></span>
   <br><br>
       
   备注: <textarea name="comment" rows="5" cols="40"><?php echo $comment;?></textarea>
   <br><br>
       
   性别:
   <input type="radio" name="gender" <?php if (isset($gender) && $gender=="female") echo "checked";?>  value="female">女
   <input type="radio" name="gender" <?php if (isset($gender) && $gender=="male") echo "checked";?>  value="male">男
   <span class="error">* <?php echo $genderErr;?></span>
   <br><br>
   <input type="submit" name="submit" value="Submit"> 
</form>
```

##### 6._GET变量

获取是用$_GET["name"]获取到的值

在HTML文件中使用表单<form action='xxx.php' method='get'>

##### 7._POST变量

表单使用就是将method换成post。

ps：post最大传参量为8MB

预定义存在一个$_REQUEST变量包含get，post，cookie的内容，用$__REQUEST变量来收集get和post方法发送的表单数据

#### PHP高级

##### 1.多维数组

```php
<?php
$sites = array
(
    "runoob"=>array
    (
        "菜鸟教程",
        "http://www.runoob.com"
    ),
    "google"=>array
    (
        "Google 搜索",
        "http://www.google.com"
    ),
    "taobao"=>array
    (
        "淘宝",
        "http://www.taobao.com"
    )
);
print("<pre>"); // 格式化输出数组
print_r($sites);
print("</pre>");
?>
```

数组$sites['runoob'][0]表述上述数组上面的第一个值

##### 2.PHP的date函数

```php
<?php
echo date("Y/m/d") . "<br>";
echo date("Y.m.d") . "<br>";
echo date("Y-m-d");
?>
```

ps：大小写表示含义不同，尽情去百度

##### 3.PHP包含文件

include和require类似，处理错误的方式不同。include出现错误脚本继续执行，而require是中断

```php+HTML
<html>
<head>
<meta charset="utf-8">
<title>菜鸟教程(runoob.com)</title>
</head>
<body>

<?php include 'header.php'; ?>
<h1>欢迎来到我的主页!</h1>
<p>一些文本。</p>

</body>
</html>
```

##### 4.PHP文件处理

类似c语言的处理在php里面写$file=fopen("aa.txt","r)；

关闭文件则用fclose

检测文件末尾（EOF）：feof（）函数检测是否已经达到文件末尾

```php
if (feof($file)) echo "文件结尾";
```

逐行读取文件：fgets（$file）

逐字符读取文件

##### 5.文件上传

下面是一个供上传文件的HTML表单

```html
<form action="upload_file.php" method="post" enctype="multipart/form-data">
    <label for="file">文件名：</label>
    <input type="file" name="file" id="file"><br>
    <input type="submit" name="submit" value="提交">
</form>
```

下面是一个PHP脚本对文件上传的一个限制

```php
<?php
// 允许上传的图片后缀
$allowedExts = array("gif", "jpeg", "jpg", "png");
$temp = explode(".", $_FILES["file"]["name"]);
$extension = end($temp);        // 获取文件后缀名
if ((($_FILES["file"]["type"] == "image/gif")
|| ($_FILES["file"]["type"] == "image/jpeg")
|| ($_FILES["file"]["type"] == "image/jpg")
|| ($_FILES["file"]["type"] == "image/pjpeg")
|| ($_FILES["file"]["type"] == "image/x-png")
|| ($_FILES["file"]["type"] == "image/png"))
&& ($_FILES["file"]["size"] < 204800)    // 小于 200 kb
&& in_array($extension, $allowedExts))
{
    if ($_FILES["file"]["error"] > 0)
    {
        echo "错误：: " . $_FILES["file"]["error"] . "<br>";
    }
    else
    {
        echo "上传文件名: " . $_FILES["file"]["name"] . "<br>";
        echo "文件类型: " . $_FILES["file"]["type"] . "<br>";
        echo "文件大小: " . ($_FILES["file"]["size"] / 1024) . " kB<br>";
        echo "文件临时存储的位置: " . $_FILES["file"]["tmp_name"];
    }
}
else
{
    echo "非法的文件格式";
}
?>
```

##### 6.PHP的cookie

cookie常用来识别用户，PHP中用setcookie()函数来设置cookie

```php
<?php
setcookie("user", "runoob", time()+3600);
?>

```

上述代码是指创建user的cookie赋值runoob并在3600秒后过期

其中$_COOKIE变量可以用于取回变量的值

删除cookie方法叶童设置cookie

```php
<?php
// 设置 cookie 过期时间为过去 1 小时
setcookie("user", "", time()-3600);
?>
```

##### 7.PHP Session变量（会话）

将用户信息存在PHP session 中首先启动会话

这句必须写在<html>标签前面

```php
<?php session_start(); 
$_SESSION['view']=1//存储session数据
?>
```

销毁session

1.unset函数释放指定的session变量：unset($_SESSION['view'])

2.seesion_destroy()函数：会重置所有已经存储的session数据

##### 8.PHP 邮件

PHP mail()函数用于从脚本发送电子邮件

```php
//mail函数使用方法
<?php
$to = "someone@example.com";         // 邮件接收者
$subject = "参数邮件";                // 邮件标题
$message = "Hello! 这是邮件的内容。";  // 邮件正文
$from = "someonelse@example.com";   // 邮件发送者
$headers = "From:" . $from;         // 头部信息设置
mail($to,$subject,$message,$headers);
echo "邮件已发送";
?>
```

邮件反馈的PHP代码

```php
<?php
if (isset($_REQUEST['email'])) { // 如果接收到邮箱参数则发送邮件
    // 发送邮件
    $email = $_REQUEST['email'] ;
    $subject = $_REQUEST['subject'] ;
    $message = $_REQUEST['message'] ;
    mail("someone@example.com", $subject,
    $message, "From:" . $email);
    echo "邮件发送成功";
} else { // 如果没有邮箱参数则显示表单
    echo "<form method='post' action='mailform.php'>
    Email: <input name='email' type='text'><br>
    Subject: <input name='subject' type='text'><br>
    Message:<br>
    <textarea name='message' rows='15' cols='40'>
    </textarea><br>
    <input type='submit'>
    </form>";
}
?>
```

防止email的注入：如someone@example.com%0ACc:person2@example.com

加入功能函数

```php
function spamcheck($field)
{
    // filter_var() 过滤 e-mail
    // 使用 FILTER_SANITIZE_EMAIL
    $field=filter_var($field, FILTER_SANITIZE_EMAIL);

    //filter_var() 过滤 e-mail
    // 使用 FILTER_VALIDATE_EMAIL
    if(filter_var($field, FILTER_VALIDATE_EMAIL))
    {
        return TRUE;
    }
    else
    {
        return FALSE;
    }
}
```

##### 9.PHP错误处理

创建一个函数处理错误信息（函数至少能处理两个参数level和message）

```php
error_function(error_level,error_message,error_file,error_line,error_context)
```

##### 10.PHP异常处理

###### 1.处理异常要用上try，throw，catch(捕获)

```php
<?php
// 创建一个有异常处理的函数
function checkNum($number)
{
    if($number>1)
    {
        throw new Exception("变量值必须小于等于 1");
    }
        return true;
}
    
// 在 try 块 触发异常
try
{
    checkNum(2);
    // 如果抛出异常，以下文本不会输出
    echo '如果输出该内容，说明 $number 变量';
}
// 捕获异常
catch(Exception $e)
{
    echo 'Message: ' .$e->getMessage();
}
?>
```

###### 2.创建自定义的异常类

```php
class customException extends Exception
{
    public function errorMessage()
    {
        // 错误信息
        $errorMsg = '错误行号 '.$this->getLine().' in '.$this->getFile()
        .': <b>'.$this->getMessage().'</b> 不是一个合法的 E-Mail 地址';
        return $errorMsg;
    }
}
```

更多详情请看[PHP 异常处理 | 菜鸟教程 (runoob.com)](https://www.runoob.com/php/php-exception.html)

##### 11.PHP过滤器

- filter_var() - 通过一个指定的过滤器来过滤单一的变量
- filter_var_array() - 通过相同的或不同的过滤器来过滤多个变量
- filter_input - 获取一个输入变量，并对它进行过滤（删除了非法字符）
- filter_input_array - 获取多个输入变量，并通过相同的或不同的过滤器对它们进行过滤

```php

<?php
if(!filter_has_var(INPUT_GET, "email"))
{
    echo("没有 email 参数");
}
else
{
    if (!filter_input(INPUT_GET, "email", FILTER_VALIDATE_EMAIL))
    {
        echo "不是一个合法的 E-Mail";
    }
    else
    {
        echo "是一个合法的 E-Mail";
    }
}
?>
```

详情了解fliter的手册，高级过滤了解一下:[PHP 高级过滤器 | 菜鸟教程 (runoob.com)](https://www.runoob.com/php/php-filter-advanced.html)

12.PHP JSON

使用json_encode和json_decode对变量进行解码和编码进行转化

json_last_error:返回最后发生的错误

#### PHP MySQL

##### 1.连接mysqli（面向对象）

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
 
// 创建连接
$conn = new mysqli($servername, $username, $password);
 
// 检测连接
if ($conn->connect_error) {
    die("连接失败: " . $conn->connect_error);
} 
echo "连接成功";
?>
```

##### 2.创建数据库

```PHP
<?php
$servername = "localhost";
$username = "username";
$password = "password";
 
// 创建连接
$conn = new mysqli($servername, $username, $password);
// 检测连接
if ($conn->connect_error) {
    die("连接失败: " . $conn->connect_error);
} 
 
// 创建数据库
$sql = "CREATE DATABASE myDB";
if ($conn->query($sql) === TRUE) {
    echo "数据库创建成功";
} else {
    echo "Error creating database: " . $conn->error;
}
 
$conn->close();
?>
```

PHP7数据库连接编码问题

```php
mysqli_query($conn, "set character set 'utf8'");//读库 
mysqli_query($conn,"set names 'utf8'");//写库
```

##### 3.创建数据表

在检测连接后写入一段代码：

```php
// 使用 sql 创建数据表
$sql = "CREATE TABLE MyGuests (
id INT(6) UNSIGNED AUTO_INCREMENT PRIMARY KEY, //6位数的id，没有负数，自动增长，值不能重复
firstname VARCHAR(30) NOT NULL,//名字
lastname VARCHAR(30) NOT NULL,//姓氏
email VARCHAR(50),//电子邮箱
reg_date TIMESTAMP
)";
 
if ($conn->query($sql) === TRUE) {
    echo "Table MyGuests created successfully";
} else {
    echo "创建数据表错误: " . $conn->error;
}
```

##### 4.向MySQL之中插入一段数据

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "myDB";
 
// 创建连接
$conn = new mysqli($servername, $username, $password, $dbname);
// 检测连接
if ($conn->connect_error) {
    die("连接失败: " . $conn->connect_error);
} 
 
$sql = "INSERT INTO MyGuests (firstname, lastname, email)
VALUES ('John', 'Doe', 'john@example.com')";
 
if ($conn->query($sql) === TRUE) {
    echo "新记录插入成功";
} else {
    echo "Error: " . $sql . "<br>" . $conn->error;
}
 
$conn->close();
?>
```

ps：每个$sql语句要通过分号进行分开

##### 5.使用预处理语句

```php
<?php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "myDB";
 
// 创建连接
$conn = new mysqli($servername, $username, $password, $dbname);
 
// 检测连接
if ($conn->connect_error) {
    die("连接失败: " . $conn->connect_error);
}
 
// 预处理及绑定
$stmt = $conn->prepare("INSERT INTO MyGuests (firstname, lastname, email) VALUES (?, ?, ?)");
$stmt->bind_param("sss", $firstname, $lastname, $email);
 
// 设置参数并执行
$firstname = "John";
$lastname = "Doe";
$email = "john@example.com";
$stmt->execute();
 
$firstname = "Mary";
$lastname = "Moe";
$email = "mary@example.com";
$stmt->execute();
 
$firstname = "Julie";
$lastname = "Dooley";
$email = "julie@example.com";
$stmt->execute();
 
echo "新记录插入成功";
 
$stmt->close();
$conn->close();
?>
```

##### 6.处理数据

```php
$sql = "SELECT id, firstname, lastname FROM MyGuests";
$result = $conn->query($sql);
 
if ($result->num_rows > 0) {
    // 输出数据
    while($row = $result->fetch_assoc()) {
        echo "id: " . $row["id"]. " - Name: " . $row["firstname"]. " " . $row["lastname"]. "<br>";
    }
} else {
    echo "0 结果";
}
```

使用sql语句来对数据进行读取

```php
$result = mysqli_query($con,"SELECT * FROM Persons
WHERE FirstName='Peter'");
```

更新使用update

```php
mysqli_query($con,"UPDATE Persons SET Age=36
WHERE FirstName='Peter' AND LastName='Griffin'");
```

删库

```php
mysqli_query($con,"DELETE FROM Persons WHERE LastName='Griffin'");
```

7.ODBC连接

ODBC是一个API接口，连接某个数据源

```php
//连接到ODBC
$conn=odbc_connect('northwind','','');
$sql="SELECT * FROM customers";
$rs=odbc_exec($conn,$sql);
```

```php
//返回记录
odbc_fetch_row($rs)
```

```php
//返回记录中第一个字段的值
$compname=odbc_result($rs,1);
//放回CompanyName的值
$compname=odbc_result($rs,"CompanyName");
```

```php
//关闭连接
odbc_close($conn);
```
