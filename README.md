模拟jQuery的hover事件

一、基本原理：

判断relatedTarget是否存在，或者relatedTarget是否等于绑定（mouseover、mouseout)事件的元素，或者relatedTarget位于绑定（mouseover、mouseout)事件元素的里面（内部）。

二、工具：

借助于mouseover、mouseout、relatedTarget来实现。

三、扩展：

mouseover、mouseout与mouseenter、mouseleave的本质区别是：
前者支持冒泡，后者不支持冒泡。

1、mouseover、mouseout:

如果绑定事件的元素内部不包含其它子元素时，或只有文本节点时，他们都只会被触发一次。

当包含有内部其它元素时，鼠标在内部元素及其本元素相互经过时，两个事件会被频繁多次触发。


2、relatedTarget 

指事件触发时的相关联元素。ie8及以下不支持，但可以模拟实现。

mouseover时（即移入时），它指的是移出的元素；
mouseout时（即移出时），它指的是移入的的元素；

3、ie模拟实现relatedTarget

event.relatedTarget = event.fromElement === event.target ? event.toElement : event.fromElement;

ie下：

当mouseover时，relatedTarget和target不同；

当mouseout时, relatedTarget和tageet相同 。











