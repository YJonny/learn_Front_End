### 事件机制

JavaScript事件机制简单来说是事件在DOM里面的传递顺序，以及对事件作如何的响应。

### 事件流

每个事件的触发分为三个阶段，事件捕获(从上到下document=>html>button)、目标阶段(读取事件)、事件冒泡(从下到上响应)

### 事件监听

1. HTML内联属性
类似<button onclick="alert('你点击了这个按钮');">点击这个按钮</button>的方式，这种方式会使JS与HTML高度耦合，不利于开发和维护，不推荐使用。

2. DOM属性绑定
使用DOM元素的onXXX属性设置，简单易懂，兼容性好。确定是只能绑定一个处理函数。

3. 事件监听函数
使用事件监听函数element.addEventListener(<event-name>, <callback>, <use-capture>);，在 element 这个对象上面添加一个事件监听器，当监听到有 事件发生的时候，调用 这个回调函数。至于 这个参数，表示该事件监听是在“捕获”阶段中监听（设置为 true）还是在“冒泡”阶段中监听（设置为 false）。

注：开发者可以通过addEventListener函数的第三个参数设置事件触发的阶段，默认为false,冒泡阶段。而DOM1级别的事件绑定则只能在冒泡阶段触发。

### 事件代理

事件绑定后，检测顺序就会从被绑定的DOM下滑到触发的元素，再冒泡会绑定的DOM上。也就是说，如果你监听了一个DOM节点，那也就等于你监听了其所有的后代节点。

代理的意思就是**只监听父节点**的事件触发，以来代理对其后代节点的监听，而你需要做的只是通过currentTarget属性得到触发元素并作出回应。

使用事件代理意味着你可以节省大量重复的事件监听，以减少浏览器资源消耗。还有一个好处就是让HTML独立起来，比如之后还有要加子元素的需求，也不需要再为其单独加事件监听了。

### 浏览器所提供的事件
onsearch 
onabort 
onblur 
oncancel - 
oncanplay
oncanplaythrough
onchange
onclick
onclose
oncontextmenu
oncuechange
ondblclick
ondrag
ondragend
ondragenter
ondragleave
ondragover
ondragstart
ondrop
ondurationchange
onemptied
onended
onerror
onfocus
onformdata
oninput
oninvalid
onkeydown
onkeypress
onkeyup
onload
onloadeddata
onloadedmetadata
onloadstart
onmousedown
onmouseenter
onmouseleave
onmousemove
onmouseout
onmouseover
onmouseup
onmousewheel
onpause
onplay
onplaying
onprogress
onratechange
onreset
onresize
onscroll
onseeked
onseeking
onselect
onstalled
onsubmit
onsuspend
ontimeupdate
ontoggle
onvolumechange
onwaiting
onwebkitanimationend
onwebkitanimationiteration
onwebkitanimationstart
onwebkittransitionend
onwheel
onauxclick
ongotpointercapture
onlostpointercapture
onpointerdown
onpointermove
onpointerup
onpointercancel
onpointerover
onpointerout
onpointerenter
onpointerleave
onselectstart
onselectionchange
onanimationend
onanimationiteration
onanimationstart
ontransitionend
onafterprint
onbeforeprint
onbeforeunload
onhashchange
onlanguagechange
onmessage
onmessageerror
onoffline
ononline
onpagehide
onpageshow
onpopstate
onrejectionhandled
onstorage
onunhandledrejection
onunload
onappinstalled
onbeforeinstallprompt
onpointerrawupdate
ondevicemotion
ondeviceorientation
ondeviceorientationabsolute
