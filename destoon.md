# destoon 
## （tag）标签调用手册

**模板语法**

* 包含模板 {template 'header'} 或 {template 'header', 'member'}

> {template 'header'} 被解析为
<?php include template('header');?> 

>表示使用 template/default/header.htm 模板文件
{template 'header', 'member'}

>被解析为 <?php include template('header', 'member');?> 
表示使用 template/default/member/header.htm 模板文件

* 变量或常量表示
> 变量 {$destoon} 被解析为 <?php echo $destoon;?>

> 常量 {DESTOON} 被解析为 <?php echo DESTOON;?>

> 对于数组，标准写法应为 例如 {$destoon['index']}，可简写为 {$destoon[index]}，模板在解析时会自动追加引号。

* 函数 {func_name($par1, $par2)}
> {func\_name($par1, $par2)} 被解析为
<?php func\_name($par1, $par2);?>

* PHP表达式 {php expression}

> {php expression} 被解析为 <?php expression ?>

* 条件语句 
> {if $a=='b'} do A {/if} 被解析为
<?php if($a=='b') { do A }?>

> {if $a=='b'} do A {else} do B {/if} 被解析为
<?php if($a=='b') { do A } else { do B } ?>

> {if $a=='b'} do A {elseif $b=='c'} do C {else} do B {/if} 被解析为
<?php if($a=='b') { do A } else if($b=='c') { do C } else { do B } ?>
* 
