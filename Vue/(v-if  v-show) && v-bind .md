有更高的切换开销，v-show有更高的初始渲染开销。如果需要频繁切换，则使用v-show 较好，如果运行条件不太可能改变

v-bind:指令如何与style中的类进行绑定

.inLine {

​      color: darkgray;

​      text-decoration: line-through;

​    }

v-bind:class="[{inLine: item.bol}]"