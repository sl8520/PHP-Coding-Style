# PHP Coding Style

## PHP標籤
PHP ==必須== 使用長標籤 <font color="#c7254e">`<?php ?>`</font> 或 <font color="#c7254e">`<?= ?>`</font> 短輸出標籤， ==不可== 使用其他自定義標籤。【PSR-1】

## 文件
- PHP文件 ==必須== 使用 `Unix LF (linefeed)` 作為行的結數符【PSR-2】
- PHP文件 ==必須== 以一個空白行作為結束。【PSR-2】
- 純PHP文件 ==必須==省 略最後的 <font color="#c7254e">`?>`</font> 標籤。【PSR-2】

## 文件命名
- 檔名長度必須小於 <font color="#c7254e">`32`</font> 個字元。
- 使用 <font color="#c7254e">`.php`</font> 作為副檔名。
- 會被引入的設定檔以 <font color="#c7254e">`.inc.php`</font> 作為結尾。

## 字元編碼
PHP ==必須== 使用<font color="#c7254e">`無BOM`</font>的<font color="#c7254e">`UTF-8`</font>編碼。【PSR-1】

## 字串
字串 ==必須== 使用單引號，2 個例外
- \n
- 字串內容包含單引號

## 縮排
程式碼 ==必須== 使用<font color="#c7254e">`4個space`</font>不使用<font color="#c7254e">`tab`</font>縮進。【PSR-2】

## 行
 - 每行的字符數建議在<font color="#c7254e">`80`</font>以內，最多不超過<font color="#c7254e">`120`</font>字，但無硬性限制。【PSR-2】
 - 非空白行後面 ==不可== 有多餘的空白符。【PSR-2】

## 關鍵字 及 true/false/null
 - PHP所有[關鍵字](http://php.net/manual/en/reserved.keywords.php) ==必須== 全部小寫。【PSR-2】
 - SQL所有[關鍵字](https://dev.mysql.com/doc/refman/8.0/en/keywords.html) ==必須== 全部大寫。
 - 常數 `true`、`false`、`null`也 ==必須== 全部小寫。【PSR-2】

## 變數命名
- 小寫駝峰式命名法（camelCase），小寫字母開頭，後面每個單字的第一個字母大寫。
- 迴圈變數通常使用 <font color="#c7254e">`$i`</font>、 <font color="#c7254e">`$j`</font>、<font color="#c7254e">`$k`</font>，依此類推。
- 使用描述性的命名方式。
- 盡量不要縮寫，把完整單字寫出，除非有特定領域大家都可接受的縮寫，以確保其他人一看就看得懂。
- <font color="#c7254e">`boolean`</font> 變數的開頭 ==必須== 使用<font color="#c7254e">`is`</font>、<font color="#c7254e">`can`</font>、<font color="#c7254e">`has`</font>、<font color="#c7254e">`should`</font>，但若本身形容詞就不需要，如 <font color="#c7254e">`enabled`</font>、<font color="#c7254e">`done`</font>。
- 使用介系詞 ( <font color="#c7254e">`of`</font>、<font color="#c7254e">`for`</font>、<font color="#c7254e">`from`</font>、<font color="#c7254e">`on`</font>... ) 來組合變數名稱。
- e.g.
```php
<?php

$daysSinceModification = 3; // 修改已過了3天
$workDaysPerWeek = 5; // 每週工作5天
$daysUntilDeadline = 10; // deadline前還剩10天

```

## 常數命名
- 常數名稱完全採用大寫英文字母。【PSR-1】
- 兩個單字以上時用底線 <font color="#c7254e">`_`</font> 來區隔。【PSR-1】

## Array
```php
// 索引陣列
$ary = array('apple', 'banana');
$ary = array(
    'apple',
    'banana'
);

// Laravel、Lumen
$ary = ['apple', 'banana'];
$ary = [
    'apple',
    'banana'
];

// 關聯陣列
$ary = array('one' => 'apple', 'two' => 'banana');
$ary = array(
    'one' => 'apple',
    'two' => 'banana'
);

// Laravel、Lumen
$ary = ['one' => 'apple', 'two' => 'banana'];
$ary = [
    'one' => 'apple',
    'two' => 'banana'
];
```
- 專案為 Laravel、Lumen 時 ==一律== 使用中括號縮寫。
- 元素的 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白，而 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`後`</font> ==必須== 留一個空白。
- 關聯陣列的 <font color="#c7254e">`=>`</font> 前後 ==必須== 有空白。
- 元素分成多行
    - 第一個元素 ==必須== 在新的一行，且每一行只有一個元素。
    - 元素的結束 <font color="#c7254e">`)`</font> ==必須== 在新的一行。
- 若元素低於 <font color="#c7254e">`5`</font> 個時可縮成一行。

## Namespace
```php
<?php

namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName 
{
    // class body
}
```
- 大寫駝峰式命名法（Pascal Case），大寫字母開頭，後面每個單字的第一個字母大寫。
- 所有 <font color="#c7254e">`use`</font> ==必須== 在 <font color="#c7254e">`namespace`</font> 後聲明。【PSR-2】
- 每條 <font color="#c7254e">`use`</font> 語句 ==必須== 只有一個 <font color="#c7254e">`use`</font> 關鍵字。【PSR-2】
- <font color="#c7254e">`<?php`</font> 與 <font color="#c7254e">`namespace`</font> 之間 ==必須== <font color="#c7254e">`空一行`</font>。【PSR-2】
- <font color="#c7254e">`namespace`</font> 與 <font color="#c7254e">`use`</font> 之間 ==必須== 空一行。【PSR-2】
- <font color="#c7254e">`use`</font> 與 <font color="#c7254e">`class`</font> 之間 ==必須== 空一行。【PSR-2】

## Interface
```php
<?php

interface PostRepositoryInterface
{
    public function getLatest3Posts();
}
```
- 大寫駝峰式命名法（Pascal Case），大寫字母開頭，後面每個單字的第一個字母大寫。
- 一個 <font color="#c7254e">`interface`</font> 一個檔案。【PSR-2】
- 括號 <font color="#c7254e">`{`</font> ==必須== 換行。【PSR-2】

## Class
```php
<?php

namespace Vendor\Package;

use FooClass;
use BarClass as Bar;
use OtherVendor\OtherPackage\BazClass;

class ClassName extends ParentClass implements \ArrayAccess, \Countable
{
    // class body
}
```
- 大寫駝峰式命名法（Pascal Case），大寫字母開頭，後面每個單字的第一個字母大寫。【PSR-1】
- 一個 <font color="#c7254e">`class`</font> 一個檔案。【PSR-2】
- 括號 <font color="#c7254e">`{`</font> ==必須== 換行。【PSR-2】
- <font color="#c7254e">`extends`</font> 與 <font color="#c7254e">`implements`</font> ==必須== 與 <font color="#c7254e">`class同一行`</font>。【PSR-2】
- <font color="#c7254e">`implements`</font> 的繼承列可以分成多行，每個 <font color="#c7254e">`interface`</font> 都 ==必須== 分開獨立成一行，包含第一個。【PSR-2】

## Trait
```php
<?php

trait LogTrait
{
    public function startLog()
    {
        // method body
    }

    public function stopLog()
    {
        // method body
    }
}
```
- 大寫駝峰式命名法（Pascal Case），大寫字母開頭，後面每個單字的第一個字母大寫。
- 一個 <font color="#c7254e">`trait`</font> 一個檔案。【PSR-2】
- 括號 <font color="#c7254e">`{`</font> ==必須== 換行。【PSR-2】

## Property
```php
<?php

class ClassName
{
    public $userName;
    public static $userCountry;
    private $_userPassword;
    protected $_userAddr;
}
```
- 小寫駝峰式命名法（camelCase），小寫字母開頭，後面每個單字的第一個字母大寫。
- 每個屬性都 ==必須== 加上訪問修飾詞 ( <font color="#c7254e">`public`</font>、<font color="#c7254e">`protected`</font>、<font color="#c7254e">`private`</font> )。【PSR-2】
- <font color="#c7254e">`static`</font> 必須加在訪問修飾詞之<font color="#c7254e">`後`</font>。
- 每條語句 ==不可== 定義超過一個屬性。【PSR-2】
- ==不可== 再使用<font color="#c7254e">`var`</font>宣告 public property。【PSR-2】
- 使用底線 <font color="#c7254e">`_`</font> 來宣告屬性為 <font color="#c7254e">`private`</font> 與 <font color="#c7254e">`protected`</font>。[^violation-psr2]

## Method
```php
<?php

namespace Vendor\Package;

class ClassName
{
    public function fooBar($arg1, &$arg2, array $arg3 = [])
    {
        // method body
    }
    
    public function multiLineArgument(
        $arg1,
        &$arg2,
        array $arg3 = []
    ) {
       // method body
    }
}
```
- 小寫駝峰式命名法（camelCase），小寫字母開頭，後面每個單字的第一個字母大寫。【PSR-1】
- 括號 <font color="#c7254e">`{`</font> ==必須== 換行。【PSR-2】
- 每個方法都 ==必須== 加上訪問修飾詞 ( <font color="#c7254e">`public`</font>、<font color="#c7254e">`protected`</font>、<font color="#c7254e">`private`</font> )。【PSR-2】
- 方法名稱與 <font color="#c7254e">`(`</font> 之間 ==不可== 留空白。【PSR-2】
- 第一個 <font color="#c7254e">`(`</font> 之<font color="#c7254e">`後`</font> ==不可== 有空白，最後一個 <font color="#c7254e">`)`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白。【PSR-2】
- 參數的 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白，而 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`後`</font> ==必須== 留一個空白。【PSR-2】
- 參數列若提供 <font color="#c7254e">`預設值`</font>，則 ==必須== 放在<font color="#c7254e">`最後一個`</font>參數。【PSR-2】
- 參數列可以分成多行
    - 第一個參數 ==必須== 在新的一行，且每一行只有一個參數。【PSR-2】
    - 參數列的結束 <font color="#c7254e">`)`</font> ==必須== 在新的一行，且與 <font color="#c7254e">`)`</font> 與 <font color="#c7254e">`{`</font> 同行，之間 ==必須== 留一個空白。【PSR-2】
- 使用底線 <font color="#c7254e">`_`</font> 來宣告方法為 <font color="#c7254e">`private`</font> 與 <font color="#c7254e">`protected`</font>。[^violation-psr2]
- 命名前綴使用動詞。可參考 [微軟 PowerShell 指令動詞列表](https://msdn.microsoft.com/en-us/library/ms714428.aspx)

## `abstract`、`final` 及 `static`
```php
<?php

namespace Vendor\Package;

abstract class ClassName
{
    protected static $_foo;

    abstract protected function _zim();

    final public static function bar()
    {
        // method body
    }
}
```
- <font color="#c7254e">`abstract`</font> 與 <font color="#c7254e">`final`</font> ==必須== 加在訪問修飾詞之<font color="#c7254e">`前`</font>。【PSR-2】
- <font color="#c7254e">`static`</font> ==必須== 加在訪問修飾詞之<font color="#c7254e">`後`</font>。【PSR-2】
- 

## Method and Function Calls
```php
<?php

bar();
$foo->bar($arg1);
Foo::bar($arg2, $arg3);

$foo->bar(
    $arg1,
    $arg2,
    $arg3
);
```
- 方法或函數名稱與 <font color="#c7254e">`(`</font> 之間 ==不可== 有空白。【PSR-2】
- 第一個 <font color="#c7254e">`(`</font> 之<font color="#c7254e">`後`</font> ==不可== 有空白，最後一個 <font color="#c7254e">`)`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白。【PSR-2】
- 引數的 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白，而 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`後`</font> ==必須== 留一個空白。【PSR-2】
- 引數列可以分成多行
    - 第一個引數 ==必須== 在新的一行，且每一行只有一個引數。【PSR-2】
    - 引數列的結束 <font color="#c7254e">`)`</font> ==必須== 在新的一行。【PSR-2】

## Closure
```php
<?php

$closureWithArgs = function ($arg1, $arg2) {
    // body
};

$closureWithArgsAndVars = function ($arg1, $arg2) use ($var1, $var2) {
    // body
};
```
- <font color="#c7254e">`function`</font> 與 <font color="#c7254e">`(`</font> 之間 ==必須== 留一個空白。【PSR-2】
- <font color="#c7254e">`use`</font> 前後都 ==必須== 留一個空白。【PSR-2】
- <font color="#c7254e">`{`</font> ==必須== 與 <font color="#c7254e">`function`</font> 同一行。【PSR-2】
- 第一個 <font color="#c7254e">`(`</font> 之<font color="#c7254e">`後`</font> ==不可== 有空白，最後一個 <font color="#c7254e">`)`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白。【PSR-2】
- 參數的 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白，而 <font color="#c7254e">`,`</font> 之<font color="#c7254e">`後`</font> ==必須== 留一個空白。【PSR-2】
- 參數列若提供 <font color="#c7254e">`預設值`</font>，則 ==必須== 放在<font color="#c7254e">`最後一個`</font>參數。【PSR-2】

## 控制結構【PSR-2】
控制結構的基本規範如下：
  - 控制結構關鍵詞後 ==必須== 有一個空格。
  - 左括號 <font color="#c7254e">`(`</font> 後 ==不可== 有空格。
  - 右括號 <font color="#c7254e">`)`</font> 前也 ==不可== 有空格。
  - 右括號 <font color="#c7254e">`)`</font> 與開始大括號右括號 <font color="#c7254e">`{`</font>間 ==必須== 有一個空格。
  - 結構體主體 ==必須== 要有一次的縮進。
  - 結束大括號 <font color="#c7254e">`}`</font> ==必須== 在結構體主體後單獨成新的一行。

### `if` 、 `else if` 和 `else`
```php
<?php

if ($expr1) {
    // if body
} elseif ($expr2) {
    // elseif body
} else {
    // else body;
}
```
- <font color="#c7254e">`{`</font> 與 <font color="#c7254e">`if`</font> 、 <font color="#c7254e">`else if`</font> 、 <font color="#c7254e">`else`</font> 要在同一行，不用換行。
- <font color="#c7254e">`}`</font> 與 <font color="#c7254e">`else if`</font> 要在同一行，不用換行。
- <font color="#c7254e">`}`</font> 與 <font color="#c7254e">`else`</font> 要在同一行，不用換行。

### `switch` 和 `case`
```php
<?php

switch ($expr) {
    case 0:
        echo 'First case, with a break';
        break;
    case 1:
        echo 'Second case, which falls through';
        // no break
    case 2:
    case 3:
    case 4:
        echo 'Third case, return instead of break';
        return;
    default:
        echo 'Default case';
        break;
}
```
- <font color="#c7254e">`{`</font> 與 <font color="#c7254e">`switch`</font> 在同一行。
- <font color="#c7254e">`case`</font> 後的條件與 <font color="#c7254e">`:`</font> 之間不可以有空白。
- <font color="#c7254e">`case`</font> 必須縮排於 <font color="#c7254e">`switch`</font>，而 <font color="#c7254e">`break`</font> 必須縮排於case。
- 如果存在 <font color="#c7254e">`case`</font> 內沒有 <font color="#c7254e">`break`</font> ，主體裡需加上 <font color="#c7254e">`// no break`</font> 註解。

### `while` 和 `do while`
```php
<?php

while ($expr) {
    // structure body
}
```
<font color="#c7254e">`{`</font> 與 <font color="#c7254e">`while`</font> 在同一行。
```php
<?php

do {
    // structure body;
} while ($expr);
```
- <font color="#c7254e">`do`</font>與 <font color="#c7254e">`{`</font> 在同一行。
- <font color="#c7254e">`}`</font> 與 <font color="#c7254e">`while`</font> 在同一行。

### `for`
```php
<?php

for ($i = 0; $i < 10; $i++) {
    // for body
}
```
- <font color="#c7254e">`{`</font> 與 <font color="#c7254e">`for`</font> 在同一行。
- <font color="#c7254e">`=`</font>、<font color="#c7254e">`<`</font> 或 <font color="#c7254e">`>`</font> 前後要留一個空白。
- <font color="#c7254e">`;`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白，之<font color="#c7254e">`後`</font> ==必須== 留一個空白。
- 第一個 <font color="#c7254e">`(`</font> 之<font color="#c7254e">`後`</font> ==不可== 有空白，最後一個 <font color="#c7254e">`)`</font> 之<font color="#c7254e">`前`</font> ==不可== 有空白。

### `foreach`
```php
<?php

foreach ($iterable as $key => $value) {
    // foreach body
}
```
- <font color="#c7254e">`{`</font> 與 <font color="#c7254e">`foreach`</font> 在同一行。
- <font color="#c7254e">`=>`</font> 前後要留一個空白。
- 第一個 <font color="#c7254e">`(`</font> 之後 不可以有空白，最後一個 <font color="#c7254e">`)`</font> 之前 不可以有空白。

### `try`, `catch`
```php
<?php

try {
    // try body
} catch (FirstExceptionType $e) {
    // catch body
} catch (OtherExceptionType $e) {
    // catch body
} finally {
    // finally body
}
```
- <font color="#c7254e">`{`</font> 與<font color="#c7254e">`try`</font>, <font color="#c7254e">`catch`</font> 要在同一行，不用換行。
- <font color="#c7254e">`}`</font> 與 <font color="#c7254e">`catch`</font> 要在同一行，不用換行。
- <font color="#c7254e">`}`</font> 與 <font color="#c7254e">`finally`</font> 要在同一行，不用換行。

[^violation-psr2]: 這違反了【PSR-2】，但我覺得這是有必要的。