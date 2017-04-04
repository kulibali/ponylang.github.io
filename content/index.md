+++
type = "index"
title = "Pony"
submenu = "false"
+++
Welcome! This is the website for the Pony programming language. Pony is an open-source, object-oriented, actor-model, capabilities-secure, high performance programming language. 

## Getting around

We've set up the website to be based on _who you are_. 

* New to Pony? [Start here]({{< relref "discover/index.md">}})
* Learning Pony? [Start here]({{< relref "learn/index.md">}})
* Existing Pony User looking for stuff? [Start here]({{< relref "reference/index.md">}})
* Looking to Contribute to Pony? [Start here]({{< relref "contribute/index.md">}})

## Sample

<a href="http://pony-playpen.lietar.net/?code=actor%20Printer%0A%20%20let%20_env%3A%20Env%0A%0A%20%20new%20create(env%3A%20Env)%20%3D%3E%0A%20%20%20%20_env%20%3D%20env%0A%20%20%0A%20%20be%20print(checker%3A%20Checker%2C%20n%3A%20U32)%20%3D%3E%0A%20%20%20%20_env.out.print(recover%20%20%20%20%20%0A%20%20%20%20%20%20let%20s%20%3D%20String%0A%20%20%20%20%20%20if%20(n%20%25%203)%20%3D%3D%200%20then%20s.append(%22Fizz%22)%20end%0A%20%20%20%20%20%20if%20(n%20%25%205)%20%3D%3D%200%20then%20s.append(%22Buzz%22)%20end%0A%20%20%20%20%20%20if%20s%20%3D%3D%20%22%22%20then%20s.append(n.string())%20end%0A%20%20%20%20%20%20s%20%0A%20%20%20%20end)%0A%20%20%20%20checker.next(this%2C%20n%20%2B%201)%0A%20%20%0Aactor%20Checker%0A%20%20let%20_max%3A%20U32%0A%0A%20%20new%20create(max%3A%20U32%20%3D%2020)%20%3D%3E%0A%20%20%20%20_max%20%3D%20max%0A%20%20%0A%20%20be%20next(printer%3A%20Printer%2C%20n%3A%20U32)%20%3D%3E%0A%20%20%20%20if%20n%20%3C%3D%20_max%20then%0A%20%20%20%20%20%20printer.print(this%2C%20n)%0A%20%20%20%20end%0A%0Aactor%20Main%0A%20%20new%20create(env%3A%20Env)%20%3D%3E%0A%20%20%20%20let%20printer%20%3D%20Printer(env)%0A%20%20%20%20let%20checker%20%3D%20Checker%0A%20%20%20%20checker.next(printer%2C%201)&run=1" target="_blank">Run This Code</a>

<pre><code class="language-pony">
<a href="https://tutorial.ponylang.org/types/actors.html" target="_blank">actor</a> Printer
  <a href="https://tutorial.ponylang.org/expressions/variables.html" target="_blank">let</a> _env: <a href="http://www.ponylang.org/ponyc/builtin-Env/" target="_blank">Env</a>

  <a href="https://tutorial.ponylang.org/types/classes.html#Constructors" target="_blank">new</a> <a href="https://tutorial.ponylang.org/expressions/sugar.html#Create" target="_blank">create</a>(env: <a href="http://www.ponylang.org/ponyc/builtin-Env/" target="_blank">Env</a>) =>
    _env = env
  
  <a href="https://tutorial.ponylang.org/types/actors.html#Behaviours" target="_blank">be</a> print(driver: Driver, n: <a href="http://www.ponylang.org/ponyc/builtin-U32/" target="_blank">U32</a>) =>
    _env.out.<a href="http://www.ponylang.org/ponyc/builtin-StdStream/#print" target="_blank">print</a>(<a href="https://tutorial.ponylang.org/capabilities/recovering-capabilities.html" target="_blank">recover</a>
      <a href="https://tutorial.ponylang.org/expressions/variables.html" target="_blank">let</a> s = <a href="http://www.ponylang.org/ponyc/builtin-String/" target="_blank">String</a>
      <a href="https://tutorial.ponylang.org/expressions/control-structures.html" target="_blank">if</a> (n <a href="https://tutorial.ponylang.org/expressions/infix-ops.html" target="_blank">%</a> 3) <a href="https://tutorial.ponylang.org/expressions/infix-ops.html" target="_blank">==</a> 0 then s.<a href="http://www.ponylang.org/ponyc/builtin-String/#append" target="_blank">append</a>("Fizz") end
      <a href="https://tutorial.ponylang.org/expressions/control-structures.html" target="_blank">if</a> (n <a href="https://tutorial.ponylang.org/expressions/infix-ops.html" target="_blank">%</a> 5) <a href="https://tutorial.ponylang.org/expressions/infix-ops.html" target="_blank">==</a> 0 then s.<a href="http://www.ponylang.org/ponyc/builtin-String/#append" target="_blank">append</a>("Buzz") end
      <a href="https://tutorial.ponylang.org/expressions/control-structures.html" target="_blank">if</a> s <a href="https://tutorial.ponylang.org/expressions/infix-ops.html" target="_blank">==</a> "" then s.<a href="http://www.ponylang.org/ponyc/builtin-String/#append" target="_blank">append</a>(n.string()) end
      s 
    end)
    driver.next(this, n + 1)
  
<a href="https://tutorial.ponylang.org/types/actors.html" target="_blank">actor</a> Driver
  <a href="https://tutorial.ponylang.org/expressions/variables.html" target="_blank">let</a> _max: U32

  <a href="https://tutorial.ponylang.org/types/classes.html#Constructors" target="_blank">new</a> <a href="https://tutorial.ponylang.org/expressions/sugar.html#Create" target="_blank">create</a>(max: <a href="http://www.ponylang.org/ponyc/builtin-U32/" target="_blank">U32</a> = 20) =>
    _max = max
  
  <a href="https://tutorial.ponylang.org/types/actors.html#Behaviours" target="_blank">be</a> next(printer: Printer, n: <a href="http://www.ponylang.org/ponyc/builtin-U32/" target="_blank">U32</a>) =>
    <a href="https://tutorial.ponylang.org/expressions/control-structures.html" target="_blank">if</a> n <a href="https://tutorial.ponylang.org/expressions/infix-ops.html" target="_blank"><=</a> _max then
      printer.print(this, n)
    end

<a href="https://tutorial.ponylang.org/types/actors.html" target="_blank">actor</a> Main
  <a href="https://tutorial.ponylang.org/types/classes.html#Constructors" target="_blank">new</a> create(env: <a href="http://www.ponylang.org/ponyc/builtin-Env/" target="_blank">Env</a>) =>
    <a href="https://tutorial.ponylang.org/expressions/variables.html" target="_blank">let</a> printer = Printer(env)
    <a href="https://tutorial.ponylang.org/expressions/variables.html" target="_blank">let</a> driver = Driver
    driver.next(printer, 1)
</code></pre>
