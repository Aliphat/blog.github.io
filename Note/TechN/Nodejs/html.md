# HTML相关

## JS:生成img标签的3种方式（对象、方法、html）

```html
<div id="d1"></div>

<script>
//HTML
function a(){
document.getElementById("d1").innerHTML="<img src='http://baike.baidu.com/cms/rc/240x112dierzhou.jpg'>";
}
a();
//方法
function b(){
var d1=document.getElementById("d1");
var img=document.createElement("img");
img.src="http://baike.baidu.com/cms/rc/240x112dierzhou.jpg";
d1.appendChild(img);
}
b();
//对象
function c(){
var cc=new Image();
cc.src="http://baike.baidu.com/cms/rc/240x112dierzhou.jpg";
document.getElementById("d1").appendChild(cc);
}
c();
</script>
```





## HTML中6种空白的空格

> HTML提供了5种空格实体（space entity），它们拥有不同的宽度，非断行空格（&nbsp;）是常规空格的宽度，可运行于所有主流浏览器。其他几种空格（ &ensp; &emsp; &thinsp; &zwnj;&zwj;）在不同浏览器中宽度各异。

&nbsp    

它叫不换行空格，全称No-Break Space，它是最常见和我们使用最多的空格，大多数的人可能只接触了&nbsp;，它是按下space键产生的空格。在HTML中，如果你用空格键产生此空格，空格是不会累加的（只算1个）。要使用html实体表示才可累加，该空格占据宽度受字体影响明显而强烈。

&ensp

它叫“半角空格”，全称是En Space，en是字体排印学的计量单位，为em宽度的一半。根据定义，它等同于字体度的一半（如16px字体中就是8px）。名义上是小写字母n的宽度。此空格传承空格家族一贯的特性：透明的，此空格有个相当稳健的特性，就是其占据的宽度正好是1/2个中文宽度，而且基本上不受字体影响。

&emsp

它叫“全角空格”，全称是Em Space，em是字体排印学的计量单位，相当于当前指定的点数。例如，1 em在16px的字体中就是16px。此空格也传承空格家族一贯的特性：透明的，此空格也有个相当稳健的特性，就是其占据的宽度正好是1个中文宽度，而且基本上不受字体影响。

&thinsp

它叫窄空格，全称是Thin Space。我们不妨称之为“瘦弱空格”，就是该空格长得比较瘦弱，身体单薄，占据的宽度比较小。它是em之六分之一宽。

&zwnj 

它叫零宽不连字，全称是Zero Width Non Joiner，简称“ZWNJ”，是一个不打印字符，放在电子文本的两个字符之间，抑制本来会发生的连字，而是以这两个字符原本的字形来绘制。Unicode中的零宽不连字字符映射为“”（zero width non-joiner，U+200C），HTML字符值引用为： &#8204;

## &zwj

它叫零宽连字，全称是Zero Width Joiner，简称“ZWJ”，是一个不打印字符，放在某些需要复杂排版语言（如阿拉伯语、印地语）的两个字符之间，使得这两个本不会发生连字的字符产生了连字效果。零宽连字符的Unicode码位是U+200D (HTML: &#8205; &zwj;）。

此外，浏览器还会把以下字符当作空白进行解析：空格（&#x0020;）、制表位（&#x0009;）、换行（&#x000A;）和回车（&#x000D;）还有（&#12288;）等等。

出处：https://www.cnblogs.com/AllenChou/p/7137239.html