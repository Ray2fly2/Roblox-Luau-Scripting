<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Roblox Luau Encyclopedia</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    background: #181818;
    color: #f0f0f0;
    display: flex;
    height: 100vh;
  }
  #sidebar {
    width: 250px;
    background: #222;
    overflow-y: auto;
    border-right: 1px solid #444;
  }
  #sidebar button {
    display: block;
    width: 100%;
    padding: 12px 20px;
    background: none;
    border: none;
    color: #ccc;
    text-align: left;
    cursor: pointer;
    border-bottom: 1px solid #333;
    font-weight: 600;
    text-transform: uppercase;
  }
  #sidebar button.active,
  #sidebar button:hover {
    background: #444;
    color: #fff;
  }
  #content {
    flex-grow: 1;
    padding: 30px;
    overflow-y: auto;
    line-height: 1.5em;
    max-width: 900px;
  }
  h1, h2, h3 {
    color: #81a1c1;
  }
  pre {
    background: #2e3440;
    padding: 15px;
    border-radius: 6px;
    overflow-x: auto;
    margin-bottom: 25px;
    font-size: 14px;
    line-height: 1.3em;
  }
  code {
    font-family: Consolas, monospace;
    color: #d8dee9;
  }
  p {
    margin-bottom: 20px;
  }
  ul {
    margin-bottom: 20px;
    padding-left: 20px;
  }
  ul li {
    margin-bottom: 8px;
  }
</style>
</head>
<body>

<div id="sidebar">
  <button data-topic="variables" class="active">Variables</button>
  <button data-topic="printing">Printing</button>
  <button data-topic="controlflow">Control Flow</button>
  <button data-topic="loops">Loops</button>
  <button data-topic="functions">Functions</button>
  <button data-topic="tables">Tables</button>
  <button data-topic="events">Events</button>
  <button data-topic="remotes">Remotes</button>
  <button data-topic="modules">Modules &amp; More</button>
</div>

<div id="content"></div>

<script>
const topics = {
  variables: `
  <h2>VARIABLES</h2>
  <p>Variables store data for your program to use. Think of them as labeled boxes that hold information such as numbers, text, or true/false values.</p>

  <pre><code>-- Example Variables
local x = 5       -- stores a number
local name = "Ray" -- stores a string (text)
local isCool = true -- stores a boolean (true or false)

print(x)        -- prints 5
print("Hello "..name) -- prints "Hello Ray"
  </code></pre>

  <p>Variables let you remember things and reuse them throughout your scripts. You can name variables almost anything, but not reserved Lua keywords like <code>if</code>, <code>end</code>, etc.</p>

  <p>Variables can be updated anytime:</p>

  <pre><code>x = 10
print(x)  -- Now prints 10
  </code></pre>

  <p>This simple concept is the foundation for all programming in Roblox Luau.</p>
  `,

  printing: `
  <h2>PRINTING</h2>
  <p>Printing is how you show messages in Roblox’s output window, which helps with debugging and feedback.</p>

  <pre><code>print("Hello World")  -- Prints "Hello World" in the output
warn("Warning message") -- Prints a yellow warning message
error("Error message")  -- Stops the script and prints an error
  </code></pre>

  <p>You can also print variables or expressions:</p>

  <pre><code>local score = 100
print("Score is", score) -- Prints: Score is 100
print("5 + 5 =", 5 + 5)   -- Prints: 5 + 5 = 10
  </code></pre>

  <p>Printing is your best friend for understanding what your scripts are doing during development.</p>
  `,

  controlflow: `
  <h2>CONTROL FLOW</h2>
  <p>Control flow statements decide which parts of code run based on conditions, letting your scripts respond dynamically.</p>

  <pre><code>local health = 50

if health > 75 then
  print("You are healthy")
elseif health > 30 then
  print("You are hurt")
else
  print("You are critical")
end
  </code></pre>

  <p>Use <code>if</code>, <code>elseif</code>, and <code>else</code> blocks to check multiple cases. Conditions use comparison operators like <code>==</code>, <code>~=</code> (not equals), <code>&gt;</code>, <code>&lt;</code>, etc.</p>

  <p>You can combine conditions with logical operators <code>and</code>, <code>or</code>, and <code>not</code> for complex logic.</p>

  <pre><code>local isDay = true
local hasFlashlight = false

if isDay or hasFlashlight then
  print("You can see")
else
  print("It's dark!")
end
  </code></pre>

  <p>Mastering control flow makes your games interactive and smart.</p>
  `,

  loops: `
  <h2>LOOPS</h2>

  <p>Loops let you run code repeatedly, which is vital for tasks like updating game states, animations, timers, or repeated checks.</p>

  <h3>For Loops</h3>
  <p>The most common loop runs a block a set number of times:</p>
  <pre><code>for i = 1, 5 do
  print("Loop count:", i)
end
-- Output:
-- Loop count: 1
-- Loop count: 2
-- Loop count: 3
-- Loop count: 4
-- Loop count: 5
</code></pre>
  <p>This runs the code inside <code>do ... end</code> five times, with <code>i</code> changing each time.</p>

  <h3>While Loops</h3>
  <p>Use <code>while</code> to run code while a condition is true:</p>
  <pre><code>local count = 1
while count <= 5 do
  print("Counting:", count)
  count = count + 1
end
-- Prints numbers 1 to 5
</code></pre>
  <p>Be careful with while loops to avoid infinite loops which freeze your game.</p>

  <h3>Repeat Until Loops</h3>
  <p>Similar to <code>while</code>, but runs the block first, then checks condition after:</p>
  <pre><code>local num = 1
repeat
  print("Number:", num)
  num = num + 1
until num > 5
-- Prints numbers 1 to 5
</code></pre>

  <h3>Loop Control Statements</h3>
  <ul>
    <li><code>break</code>: exit a loop immediately</li>
    <li><code>continue</code> does not exist in Lua; use conditional statements to skip iterations</li>
  </ul>
  <pre><code>for i = 1, 10 do
  if i == 5 then
    break  -- exits loop when i == 5
  end
  print(i)
end
-- Prints 1,2,3,4 then stops
</code></pre>

  <h3>Example: Looping Through Tables</h3>
  <pre><code>local fruits = {"Apple", "Banana", "Cherry"}

for index, fruit in ipairs(fruits) do
  print("Fruit " .. index .. ": " .. fruit)
end
-- Prints:
-- Fruit 1: Apple
-- Fruit 2: Banana
-- Fruit 3: Cherry
</code></pre>

  <h3>Practical Uses</h3>
  <p>Loops let you do things like:</p>
  <ul>
    <li>Update NPC movements every frame</li>
    <li>Check player health repeatedly</li>
    <li>Process multiple objects or players</li>
    <li>Generate procedural content</li>
  </ul>
  <p>Master loops to control repetitive behavior efficiently!</p>
  `,

  functions: `
  <h2>FUNCTIONS</h2>

  <p>Functions let you package reusable code blocks. Instead of writing the same code repeatedly, define a function and call it whenever needed.</p>

  <h3>Declaring Functions</h3>
  <pre><code>function greet()
  print("Hello, Roblox!")
end

greet()  -- Calls the function and prints the message
</code></pre>
  <p>Functions can also accept parameters to customize behavior:</p>

  <pre><code>function greetPlayer(name)
  print("Hello, " .. name .. "!")
end

greetPlayer("Ray")  -- Prints: Hello, Ray!
greetPlayer("Alex") -- Prints: Hello, Alex!
</code></pre>

  <h3>Returning Values</h3>
  <p>Functions can return values to be used later:</p>
  <pre><code>function add(a, b)
  return a + b
end

local result = add(5, 7)
print(result)  -- Prints 12
</code></pre>

  <h3>Local Functions</h3>
  <p>Using <code>local</code> before a function limits its scope to where it’s declared:</p>
  <pre><code>local function secret()
  print("This is a secret function!")
end

secret()  -- Works here
</code></pre>

  <h3>Anonymous Functions</h3>
  <p>Functions can be stored in variables or passed as arguments:</p>
  <pre><code>local function sayHi()
  print("Hi!")
end

local func = sayHi
func()  -- Calls sayHi

-- Passing function as callback
game:GetService("RunService").Stepped:Connect(function(time, delta)
  print("Frame updated")
end)
</code></pre>

  <h3>Why Use Functions?</h3>
  <ul>
    <li>Organize code into logical blocks</li>
    <li>Make scripts easier to read and maintain</li>
    <li>Avoid repeating code</li>
    <li>Allow reuse and modularity</li>
  </ul>

  <h3>Practical Example: Health Update Function</h3>
  <pre><code>local playerHealth = 100

function takeDamage(amount)
  playerHealth = playerHealth - amount
  if playerHealth < 0 then
    playerHealth = 0
  end
  print("Player health now:", playerHealth)
end

takeDamage(25)  -- Health: 75
takeDamage(50)  -- Health: 25
takeDamage(30)  -- Health: 0 (can't go below 0)
</code></pre>
  `,

  tables: `
  <h2>TABLES</h2>

  <p>Tables are Luau’s powerful data structures, acting like arrays, dictionaries, or objects.</p>

  <h3>Basic Table (Array)</h3>
  <pre><code>local fruits = {"Apple", "Banana", "Cherry"}

print(fruits[1])  -- Apple (Lua indexing starts at 1)
print(#fruits)    -- 3 (length of the table)
</code></pre>

  <h3>Tables as Dictionaries</h3>
  <p>Tables can use string keys:</p>
  <pre><code>local player = {
  Name = "Ray",
  Level = 5,
  Health = 100,
}

print(player.Name)   -- Ray
print(player["Level"]) -- 5
</code></pre>

  <h3>Adding and Removing Keys</h3>
  <pre><code>player.Mana = 50       -- Adds new key
print(player.Mana)     -- 50

player.Health = nil    -- Removes the Health key
print(player.Health)   -- nil
</code></pre>

  <h3>Looping Through Tables</h3>
  <p>Use <code>pairs()</code> to loop through keys and values:</p>
  <pre><code>for key, value in pairs(player) do
  print(key, value)
end
-- Output:
-- Name Ray
-- Level 5
-- Mana 50
</code></pre>

  <h3>Nested Tables</h3>
  <pre><code>local gameData = {
  Players = {
    {Name="Ray", Score=100},
    {Name="Alex", Score=150},
  }
}

print(gameData.Players[2].Name)  -- Alex
print(gameData.Players[1].Score) -- 100
</code></pre>

  <h3>Metatables &amp; Operator Overloading (Advanced)</h3>
  <p>Metatables let you customize table behavior, like adding arithmetic or indexing magic. This is advanced, but powerful!</p>

  <h3>Why Tables Matter</h3>
  <ul>
    <li>Store collections of items or objects</li>
    <li>Manage complex game data</li>
    <li>Implement classes, modules, and much more</li>
  </ul>

  <p>Understanding tables is essential to Luau scripting mastery.</p>
  `,

  events: `
  <h2>EVENTS</h2>

  <p>Events let scripts react to things happening in the game, like player input, collisions, or timers.</p>

  <h3>Connecting to Events</h3>
  <p>Use <code>:Connect(function)</code> to listen to an event:</p>
  <pre><code>local part = workspace.Part

part.Touched:Connect(function(hit)
  print(hit.Name .. " touched the part")
end)
</code></pre>

  <p>This prints the name of any object touching the part.</p>

  <h3>Common Roblox Events</h3>
  <ul>
    <li><code>Touched</code>: Part touched by something</li>
    <li><code>Changed</code>: Property changed</li>
    <li><code>Heartbeat</code>: Every server frame (RunService)</li>
    <li><code>PlayerAdded</code>: Player joins game</li>
  </ul>

  <h3>Disconnecting Events</h3>
  <p>You can disconnect event listeners to stop them:</p>
  <pre><code>local connection = part.Touched:Connect(function(hit)
  print("Touched!")
end)

-- Later
connection:Disconnect()
</code></pre>

  <h3>Custom Events with BindableEvents</h3>
  <pre><code>local BindableEvent = Instance.new("BindableEvent")

BindableEvent.Event:Connect(function(msg)
  print("Event fired with message:", msg)
end)

BindableEvent:Fire("Hello custom event!")
</code></pre>

  <h3>Why Use Events?</h3>
  <ul>
    <li>Respond to game changes instantly</li>
    <li>Write reactive, efficient code</li>
    <li>Communicate between scripts and objects</li>
  </ul>

  <p>Events are the backbone of dynamic Roblox experiences.</p>
  `,

  remotes: `
  <h2>REMOTES</h2>

  <p>Remotes let the client and server communicate securely in Roblox games, essential for multiplayer functionality.</p>

  <h3>RemoteEvents</h3>
  <p>Used for one-way communication:</p>
  <pre><code>-- Server Script
local remoteEvent = game.ReplicatedStorage:WaitForChild("MyRemoteEvent")

remoteEvent.OnServerEvent:Connect(function(player, message)
  print(player.Name .. " says: " .. message)
end)

-- LocalScript (client)
local remoteEvent = game.ReplicatedStorage:WaitForChild("MyRemoteEvent")
remoteEvent:FireServer("Hello Server!")
</code></pre>

  <h3>RemoteFunctions</h3>
  <p>Used when client needs a response from the server:</p>
  <pre><code>-- Server Script
local remoteFunction = game.ReplicatedStorage:WaitForChild("MyRemoteFunction")

remoteFunction.OnServerInvoke = function(player, question)
  if question == "How are you?" then
    return "I'm fine, thanks!"
  else
    return "I don't understand."
  end
end

-- LocalScript (client)
local remoteFunction = game.ReplicatedStorage:WaitForChild("MyRemoteFunction")
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Roblox Luau Encyclopedia</title>
<style>
  body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    background: #1e1e2f;
    color: #ddd;
    margin: 0;
    padding: 0;
  }
  header {
    background: #27293d;
    padding: 1rem;
    text-align: center;
    font-size: 2rem;
    font-weight: bold;
    color: #76c7c0;
  }
  nav {
    background: #33354a;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  nav button {
    background: transparent;
    border: none;
    color: #ddd;
    padding: 1rem 2rem;
    cursor: pointer;
    font-size: 1rem;
    transition: background 0.3s ease;
  }
  nav button:hover,
  nav button.active {
    background: #76c7c0;
    color: #1e1e2f;
  }
  main {
    max-width: 900px;
    margin: 1rem auto;
    padding: 1rem;
    background: #27293d;
    border-radius: 8px;
  }
  section {
    margin-bottom: 3rem;
  }
  section h2 {
    border-bottom: 2px solid #76c7c0;
    padding-bottom: 0.3rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
    letter-spacing: 1.5px;
    color: #76c7c0;
  }
  pre {
    background: #1e1e2f;
    padding: 1rem;
    border-radius: 6px;
    overflow-x: auto;
    color: #a1d2ce;
  }
  code {
    font-family: Consolas, monospace;
    font-size: 0.95rem;
  }
  p {
    margin-bottom: 1rem;
  }
</style>
</head>
<body>
<header>Roblox Luau Encyclopedia</header>
<nav>
  <button onclick="showTopic('variables')" class="active">Variables</button>
  <button onclick="showTopic('local-variables')">Local Variables</button>
  <button onclick="showTopic('loops')">Loops</button>
  <button onclick="showTopic('functions')">Functions</button>
  <button onclick="showTopic('tables')">Tables</button>
  <button onclick="showTopic('events')">Events</button>
  <button onclick="showTopic('remotes')">Remotes</button>
  <button onclick="showTopic('modules')">Modules</button>
  <!-- Add more buttons as needed -->
</nav>
<main id="content">

<section id="variables" style="display:block;">
  <h2>VARIABLES</h2>
  <p>
    Variables store data like numbers, text, or boolean values (true/false). You create a variable by using the <code>local</code> keyword followed by the variable name, an equals sign, and the value you want to store.
  </p>
  <pre><code>local Variable = "Hello!" -- A variable storing the text "Hello!"
print(Variable) -- prints Hello!
print("test") -- prints test
warn("test") -- prints a warning message "test"
</code></pre>
  <p>
    You can also do math operations with numbers in variables:
  </p>
  <pre><code>local number = 5
print(number + 3) -- 8
print(number - 2) -- 3
print(number * 4) -- 20
print(number / 2) -- 2.5
</code></pre>
</section>

<section id="local-variables" style="display:none;">
  <h2>LOCAL VARIABLES</h2>
  <p>
    In Roblox Lua (Luau), <strong>local variables</strong> are variables that are limited in scope to the block or function where they are declared. This means they only exist and can be used within that specific part of the code. Using local variables is important for keeping your code clean and avoiding conflicts, especially in large scripts or when multiple scripts run simultaneously.
  </p>
  <p>
    Declaring a variable as <code>local</code> helps Roblox optimize your code performance because it doesn’t have to look outside the local scope for the variable every time. It also protects variables from being accidentally changed by other parts of the game.
  </p>
  <p>
    <strong>Example 1: Local variable inside a function</strong>
  </p>
  <pre><code>function greet()
  local message = "Hello, Roblox!"
  print(message) -- prints "Hello, Roblox!"
end

greet()
-- print(message) -- this would cause an error because 'message' is local to the function
</code></pre>
  <p>
    In this example, the variable <code>message</code> exists only inside the <code>greet</code> function. Trying to access it outside causes an error.
  </p>
  <p>
    <strong>Example 2: Local variables prevent overwriting global variables</strong>
  </p>
  <pre><code>local score = 10 -- local variable

function increaseScore()
  local score = 5 -- this 'score' is different from the one outside
  print("Inside function, score is: "..score) -- prints 5
end

increaseScore()
print("Outside function, score is: "..score) -- prints 10
</code></pre>
  <p>
    Here, the local <code>score</code> inside the function is separate from the one outside. This prevents unexpected changes to variables in other parts of your code.
  </p>
  <p>
    <strong>Example 3: Local variables in loops</strong>
  </p>
  <pre><code>for i = 1, 5 do
  local message = "Loop number "..i
  print(message) -- prints Loop number 1, then 2, up to 5
end

-- print(message) -- error, 'message' is local inside the loop
</code></pre>
  <p>
    Each loop iteration has its own local variable <code>message</code> that doesn’t exist outside the loop.
  </p>
  <p>
    <strong>Summary:</strong> Always use <code>local</code> when declaring variables unless you need to make a global variable intentionally. This helps keep your code efficient, secure, and easy to debug.
  </p>
</section>

<section id="loops" style="display:none;">
  <h2>LOOPS</h2>
  <p>
    Loops help you repeat code multiple times without writing it over and over. The main types of loops in Luau are <code>for</code>, <code>while</code>, and <code>repeat until</code>.
  </p>
  <p>
    <strong>For loop:</strong> repeats a block of code a set number of times.
  </p>
  <pre><code>for i = 1, 5 do
  print(i) -- prints numbers 1 to 5
end
</code></pre>
  <p>
    <strong>While loop:</strong> runs as long as a condition is true.
  </p>
  <pre><code>local x = 1
while x <= 5 do
  print(x)
  x = x + 1
end
</code></pre>
  <p>
    <strong>Repeat until loop:</strong> runs the block at least once and repeats until the condition is true.
  </p>
  <pre><code>local count = 1
repeat
  print(count)
  count = count + 1
until count > 5
</code></pre>
  <p>
    Loops are very useful in Roblox for things like animations, checking player stats repeatedly, or spawning multiple parts.
  </p>
</section>

<!-- Add more sections for Functions, Tables, Events, Remotes, Modules, etc. similarly -->

<script>
  function showTopic(topic) {
    const sections = document.querySelectorAll('main section');
    sections.forEach(section => {
      section.style.display = 'none';
    });
    const selected = document.getElementById(topic);
    if (selected) {
      selected.style.display = 'block';
    }
    // Update nav active
    const buttons = document.querySelectorAll('nav button');
    buttons.forEach(btn => btn.classList.remove('active'));
    const activeBtn = Array.from(buttons).find(b => b.textContent.toLowerCase().replace(/ /g, '-') === topic);
    if (activeBtn) activeBtn.classList.add('active');
  }
</script>
</body>
</html>


