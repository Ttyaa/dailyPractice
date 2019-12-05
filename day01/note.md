##可以用方括号扩起来的javascript表达式作为一个指令的参数：
    <a v-bind:[attributeName]="url"> ... </a>
    eg. vue实例中有一个data属性attributeName,其值为"href",那么这个绑定将等价于v-bind:href。
    <a v-on:[eventName]="doSomething"> ... </a>
    eg. eventName的值为"focus"时，v-on:[eventName] == v-on:focus。

##对动态参数的值的约束
    动态参数预期会求出一个字符串，异常情况下值为null。这个特殊的null值可以用于移除绑定。任何其他非字符串类型的值都将会触发一个警告。

##动态参数表达式有一些语法约束
    因为某些字符，如空格和引号，放在 HTML attribute 名里是无效的。触发编译警告。

##计算属性缓存vs方法
    计算属性是基于响应式依赖进行缓存的，只有在相关响应式依赖发生改变时才会重新求值。
    也就是说只要message还没有发生改变，多次访问reversedMessage计算属性会立即返回之前的计算结果，而不必再次执行函数。

##侦听器
    watch选项提供了更通用的方法，来响应数据的变化。当需要在数据变化时执行异步或开销较大的操作时，这个方法是最有用的。
    eg.     <div id="watch-example">
                <p>
                    ask a yes/no qusetion:
                    <input v-model="question">
                </p>
                <p>{{ answer }}</p>
            </div>

##_.debounce(func,[wait=0],[options])
    创建一个防抖动函数。该函数会在wait毫秒后调用func方法。