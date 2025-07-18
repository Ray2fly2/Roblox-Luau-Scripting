<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Roblox Studio Handbook: Variables & Data Types Deep Dive</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { font-family: 'Segoe UI', Arial, sans-serif; background: #18181b; color: #f4f4f5; margin: 0; }
    main { max-width: 1000px; margin: auto; padding: 2rem;}
    section { background: #23232b; padding: 2rem; border-radius: 12px; box-shadow: 0 2px 18px #0002; margin-bottom: 2rem;}
    h2 { color: #fbbf24; font-size: 2rem;}
    h3 { color: #fbbf24; margin-top: 2em; font-size: 1.3rem;}
    h4 { color: #fbbf24; margin-top: 1.2em; font-size: 1.08rem;}
    pre { background: #18181b; border-radius: 5px; padding: 1.06rem; overflow-x: auto; margin: 1rem 0;}
    code { font-family: 'Fira Mono', 'Consolas', monospace; color: #fbbf24; font-size: 1.05rem;}
    .tip, .warning, .challenge, .simple, .example, .deepdive {
      background: #23232b;
      padding-left: 1rem;
      margin: 1rem 0;
      font-style: normal;
      border-left: 4px solid #10b981;
      color: #10b981;
    }
    .warning { border-color: #ef4444; color: #ef4444;}
    .challenge { border-color: #22d3ee; color: #22d3ee;}
    .simple { border-color: #fbbf24; color: #fbbf24; font-weight: 600;}
    .deepdive { border-color: #6366f1; color: #a5b4fc;}
    .example { border-color: #f59e42; color: #fbbf24;}
  </style>
</head>
<body>
<main>
<section>
  <h2>Luau Variables & Data Types</h2>
  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is a Variable?</strong>  
    A variable is a named container that holds data. You use variables to store information (numbers, text, objects, etc.) so you can reference and manipulate it later in your code. In Luau, use <code>local</code> for variables you want to keep limited in scope.
  </div>
  <div class="deepdive">
    <strong>2. Data Types in Luau</strong>  
    Luau supports several data types: <code>Number</code>, <code>String</code>, <code>Boolean</code>, <code>Table</code>, <code>Instance</code>, and <code>nil</code>. Knowing which type to use helps you write reliable, bug-free code.
  </div>
  <div class="deepdive">
    <strong>3. Best Practices for Naming Variables</strong>  
    Use descriptive names (e.g., <code>playerScore</code> not just <code>x</code>). Avoid global variables unless necessary. Stick to <code>local</code> for safety and clarity.
  </div>
  <div class="deepdive">
    <strong>4. Variable Scope</strong>  
    <code>local</code> variables only exist inside the block or function where they're declared. Globals exist everywhere, but can cause conflicts. Use <code>local</code> almost always!
  </div>
  <div class="deepdive">
    <strong>5. Tables: The Most Powerful Data Structure</strong>  
    Tables in Luau are flexible—they can be arrays, dictionaries, or even classes. You can store numbers, strings, booleans, even functions inside tables.
  </div>
  <h4>Simplified Explanations</h4>
  <div class="simple">A variable is a name for a value. Use it to remember stuff while your game runs.</div>
  <div class="simple">Numbers (like <code>10</code>) are for math. Strings (like <code>"hello"</code>) are for text.</div>
  <div class="simple">Use <code>local</code> so your variable doesn't mess up others' code.</div>
  <h3>15+ Script Examples</h3>

  <div class="example"><strong>Example 1: Basic Number</strong>
<pre><code>local health = 100
print("Player health is:", health)</code></pre></div>

  <div class="example"><strong>Example 2: String Concatenation</strong>
<pre><code>local playerName = "Ray2fly2"
print("Welcome " .. playerName .. "!")</code></pre></div>

  <div class="example"><strong>Example 3: Boolean Toggle</strong>
<pre><code>local isAlive = true
if isAlive then
    print("Player is alive!")
end</code></pre></div>

  <div class="example"><strong>Example 4: Table as Array</strong>
<pre><code>local colors = {"Red", "Blue", "Green"}
print("Color #1 is", colors[1]) -- "Red"</code></pre></div>

  <div class="example"><strong>Example 5: Table as Dictionary</strong>
<pre><code>local stats = {health = 90, mana = 40}
print("Mana:", stats.mana)</code></pre></div>

  <div class="example"><strong>Example 6: Instance Variable</strong>
<pre><code>local baseplate = workspace.Baseplate
baseplate.BrickColor = BrickColor.new("Bright blue")</code></pre></div>

  <div class="example"><strong>Example 7: nil as "no value"</strong>
<pre><code>local reward
if reward == nil then
    print("No reward yet.")
end</code></pre></div>

  <div class="example"><strong>Example 8: Changing Variable Values</strong>
<pre><code>local coins = 10
coins = coins + 5
print("Coins:", coins)</code></pre></div>

  <div class="example"><strong>Example 9: Table of Functions</strong>
<pre><code>local actions = {
  jump = function() print("Jump!") end,
  run = function() print("Run!") end
}
actions.run()</code></pre></div>

  <div class="example"><strong>Example 10: Loop Over Table</strong>
<pre><code>local enemies = {"Slime", "Goblin", "Dragon"}
for i, enemy in ipairs(enemies) do
  print("Enemy #" .. i .. ": " .. enemy)
end</code></pre></div>

  <div class="example"><strong>Example 11: Boolean Toggle</strong>
<pre><code>local isDay = true
isDay = not isDay
print(isDay)</code></pre></div>

  <div class="example"><strong>Example 12: Variable Scope Inside Function</strong>
<pre><code>local function test()
  local x = 5
  print(x)
end
test()
print(x) -- Error!</code></pre></div>

  <div class="example"><strong>Example 13: Table as Class Skeleton</strong>
<pre><code>local Player = {}
Player.__index = Player

function Player.new(name)
  local self = setmetatable({}, Player)
  self.name = name
  self.score = 0
  return self
end

local p = Player.new("Ray2fly2")
print(p.name)</code></pre></div>

  <div class="example"><strong>Example 14: Using nil to Remove Table Entry</strong>
<pre><code>local stats = {health = 100, mana = 50}
stats.mana = nil
print(stats.mana) -- nil</code></pre></div>

  <div class="example"><strong>Example 15: Instance Reference in Table</strong>
<pre><code>local objects = {
  mainPart = workspace.MainPart,
  gui = game.Players.LocalPlayer.PlayerGui
}
objects.mainPart.BrickColor = BrickColor.new("Bright yellow")</code></pre></div>

  <div class="example"><strong>Example 16: Table with Mixed Types</strong>
<pre><code>local mixed = {score = 100, alive = true, name = "Player1"}
for k, v in pairs(mixed) do
  print(k, v)
end</code></pre></div>

  <div class="example"><strong>Example 17: Using tonumber and tostring</strong>
<pre><code>local strNum = "123"
print(tonumber(strNum) + 1) -- 124
local num = 42
print(tostring(num) .. " points") -- "42 points"</code></pre></div>

  <div class="example"><strong>Example 18: Table of Tables</strong>
<pre><code>local players = {
  {name = "A", score = 10},
  {name = "B", score = 15}
}
for _, player in pairs(players) do
  print(player.name, player.score)
end</code></pre></div>

  <div class="example"><strong>Example 19: Use of type()</strong>
<pre><code>local health = 99
print(type(health)) -- "number"
local stats = {}
print(type(stats)) -- "table"</code></pre></div>

  <div class="example"><strong>Example 20: Variable Shadowing</strong>
<pre><code>local x = 5
do
  local x = 10
  print(x) -- 10
end
print(x) -- 5</code></pre></div>

  <div class="example"><strong>Example 21: Table with Functions as Values</strong>
<pre><code>local mathOps = {
  add = function(a, b) return a + b end,
  sub = function(a, b) return a - b end
}
print(mathOps.add(4, 3)) -- 7</code></pre></div>

  <div class="example"><strong>Example 22: Table Length</strong>
<pre><code>local fruits = {"apple", "banana", "cherry"}
print(#fruits) -- 3</code></pre></div>

  <div class="example"><strong>Example 23: Table as Stack</strong>
<pre><code>local stack = {}
table.insert(stack, "first")
table.insert(stack, "second")
print(stack[#stack]) -- "second"</code></pre></div>

  <div class="example"><strong>Example 24: Table as Queue</strong>
<pre><code>local queue = {}
table.insert(queue, "first")
table.insert(queue, "second")
print(table.remove(queue, 1)) -- "first"</code></pre></div>

  <div class="example"><strong>Example 25: Table with Custom Index</strong>
<pre><code>local stats = {}
setmetatable(stats, {
  __index = function(_, key)
    return key .. " not found!"
  end
})
print(stats.health) -- "health not found!"</code></pre></div>

  <div class="challenge">
    <strong>Mini Project:</strong> Build a script that tracks three player stats (health, coins, powerups) in a table. Write functions to update and print each stat. Bonus: Reset all stats to default values.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always initialize variables before using them. Uninitialized variables default to nil, which can cause errors.</div>
  <div class="warning">Don't use the same variable name in different scopes unless you intend to "shadow" it.</div>
  <div class="tip">Prefer <code>local</code> in loops to avoid polluting the global namespace.</div>
  <div class="tip">Use tables to group related data instead of many separate variables.</div>
  <div class="warning">Using <code>global</code> variables can lead to hard-to-find bugs if scripts overwrite each other's values.</div>

  <h3>Challenges and Practice</h3>
  <div class="challenge">
    <strong>Challenge 1:</strong> Build a script that creates an inventory table for a player, adds three items, removes one, and prints all items.
  </div>
  <div class="challenge">
    <strong>Challenge 2:</strong> Write a function that accepts a table of scores and returns the highest score.
  </div>
  <div class="challenge">
    <strong>Challenge 3:</strong> Design a table for a shop with item names and prices, loop over the table, and print a formatted shop catalog.
  </div>

</section>
</main>
</body>
</html> <section id="luau-variables-data-types">
  <h2>Luau Variables & Data Types</h2>
  <blockquote>
    Everything in Roblox scripting starts with variables. This section will teach you how to declare, use, and master variables and data types in Luau, with tons of examples and tips.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is a Variable?</strong><br>
    A variable is a named container for a value (like a box). You use variables to store information (numbers, text, objects, tables, functions, etc.) so your scripts can remember, compare, and change things as the game runs. In Luau, variables are declared with <code>local</code> or globally (not recommended).
  </div>
  <div class="deepdive">
    <strong>2. Data Types in Luau</strong><br>
    Luau supports several native types: <code>Number</code> (for math), <code>String</code> (for text), <code>Boolean</code> (<code>true</code>/<code>false</code>), <code>Table</code> (collections and objects), <code>Instance</code> (Roblox objects like Parts, GUIs), and <code>nil</code> (no value).
  </div>
  <div class="deepdive">
    <strong>3. Variable Scope</strong><br>
    <code>local</code> variables only exist inside the block or function where they're declared. <code>global</code> variables exist everywhere, but can cause bugs if two scripts use the same name. Use <code>local</code> almost always!
  </div>
  <div class="deepdive">
    <strong>4. Naming Variables Clearly</strong><br>
    Good variable names make your code easy to read and debug. Use <code>playerScore</code>, <code>enemyHealth</code>, or <code>coinsCollected</code> instead of <code>x</code> or <code>z</code>.
  </div>
  <div class="deepdive">
    <strong>5. Initializing and Updating Variables</strong><br>
    Always initialize variables before using them. You can update (change) a variable’s value later in your script, such as increasing <code>score</code> when a player wins.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">A variable is a "name tag" for a piece of data. You use it to remember things in your script.</div>
  <div class="simple">Numbers are for math. Strings are for words. Booleans are yes/no. Tables are lists. Instances are Roblox objects.</div>
  <div class="simple">Use <code>local</code> so your variable doesn't mess up other scripts.</div>

  <h3>15+ Script Examples</h3>

  <div class="example"><strong>Example 1: Basic Number</strong>
<pre><code>local health = 100
print("Player health is:", health)</code></pre></div>

  <div class="example"><strong>Example 2: String Concatenation</strong>
<pre><code>local playerName = "Ray2fly2"
print("Welcome " .. playerName .. "!")</code></pre></div>

  <div class="example"><strong>Example 3: Boolean Toggle</strong>
<pre><code>local isAlive = true
if isAlive then
    print("Player is alive!")
end</code></pre></div>

  <div class="example"><strong>Example 4: Table as Array</strong>
<pre><code>local colors = {"Red", "Blue", "Green"}
print("Color #1 is", colors[1]) -- "Red"</code></pre></div>

  <div class="example"><strong>Example 5: Table as Dictionary</strong>
<pre><code>local stats = {health = 90, mana = 40}
print("Mana:", stats.mana)</code></pre></div>

  <div class="example"><strong>Example 6: Instance Variable</strong>
<pre><code>local baseplate = workspace.Baseplate
baseplate.BrickColor = BrickColor.new("Bright blue")</code></pre></div>

  <div class="example"><strong>Example 7: nil as "no value"</strong>
<pre><code>local reward
if reward == nil then
    print("No reward yet.")
end</code></pre></div>

  <div class="example"><strong>Example 8: Changing Variable Values</strong>
<pre><code>local coins = 10
coins = coins + 5
print("Coins:", coins)</code></pre></div>

  <div class="example"><strong>Example 9: Table of Functions</strong>
<pre><code>local actions = {
  jump = function() print("Jump!") end,
  run = function() print("Run!") end
}
actions.run()</code></pre></div>

  <div class="example"><strong>Example 10: Loop Over Table</strong>
<pre><code>local enemies = {"Slime", "Goblin", "Dragon"}
for i, enemy in ipairs(enemies) do
  print("Enemy #" .. i .. ": " .. enemy)
end</code></pre></div>

  <div class="example"><strong>Example 11: Boolean Toggle</strong>
<pre><code>local isDay = true
isDay = not isDay
print(isDay)</code></pre></div>

  <div class="example"><strong>Example 12: Variable Scope Inside Function</strong>
<pre><code>local function test()
  local x = 5
  print(x)
end
test()
print(x) -- Error!</code></pre></div>

  <div class="example"><strong>Example 13: Table as Class Skeleton</strong>
<pre><code>local Player = {}
Player.__index = Player

function Player.new(name)
  local self = setmetatable({}, Player)
  self.name = name
  self.score = 0
  return self
end

local p = Player.new("Ray2fly2")
print(p.name)</code></pre></div>

  <div class="example"><strong>Example 14: Using nil to Remove Table Entry</strong>
<pre><code>local stats = {health = 100, mana = 50}
stats.mana = nil
print(stats.mana) -- nil</code></pre></div>

  <div class="example"><strong>Example 15: Instance Reference in Table</strong>
<pre><code>local objects = {
  mainPart = workspace.MainPart,
  gui = game.Players.LocalPlayer.PlayerGui
}
objects.mainPart.BrickColor = BrickColor.new("Bright yellow")</code></pre></div>

  <div class="example"><strong>Example 16: Table with Mixed Types</strong>
<pre><code>local mixed = {score = 100, alive = true, name = "Player1"}
for k, v in pairs(mixed) do
  print(k, v)
end</code></pre></div>

  <div class="example"><strong>Example 17: Using tonumber and tostring</strong>
<pre><code>local strNum = "123"
print(tonumber(strNum) + 1) -- 124
local num = 42
print(tostring(num) .. " points") -- "42 points"</code></pre></div>

  <div class="example"><strong>Example 18: Table of Tables</strong>
<pre><code>local players = {
  {name = "A", score = 10},
  {name = "B", score = 15}
}
for _, player in pairs(players) do
  print(player.name, player.score)
end</code></pre></div>

  <div class="example"><strong>Example 19: Use of type()</strong>
<pre><code>local health = 99
print(type(health)) -- "number"
local stats = {}
print(type(stats)) -- "table"</code></pre></div>

  <div class="example"><strong>Example 20: Variable Shadowing</strong>
<pre><code>local x = 5
do
  local x = 10
  print(x) -- 10
end
print(x) -- 5</code></pre></div>

  <div class="example"><strong>Example 21: Table with Functions as Values</strong>
<pre><code>local mathOps = {
  add = function(a, b) return a + b end,
  sub = function(a, b) return a - b end
}
print(mathOps.add(4, 3)) -- 7</code></pre></div>

  <div class="example"><strong>Example 22: Table Length</strong>
<pre><code>local fruits = {"apple", "banana", "cherry"}
print(#fruits) -- 3</code></pre></div>

  <div class="example"><strong>Example 23: Table as Stack</strong>
<pre><code>local stack = {}
table.insert(stack, "first")
table.insert(stack, "second")
print(stack[#stack]) -- "second"</code></pre></div>

  <div class="example"><strong>Example 24: Table as Queue</strong>
<pre><code>local queue = {}
table.insert(queue, "first")
table.insert(queue, "second")
print(table.remove(queue, 1)) -- "first"</code></pre></div>

  <div class="example"><strong>Example 25: Table with Custom Index</strong>
<pre><code>local stats = {}
setmetatable(stats, {
  __index = function(_, key)
    return key .. " not found!"
  end
})
print(stats.health) -- "health not found!"</code></pre></div>

  <div class="challenge">
    <strong>Mini Project:</strong> Build a script that tracks three player stats (health, coins, powerups) in a table. Write functions to update and print each stat. Bonus: Reset all stats to default values.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always initialize variables before using them. Uninitialized variables default to nil, which can cause errors.</div>
  <div class="warning">Don't use the same variable name in different scopes unless you intend to "shadow" it.</div>
  <div class="tip">Prefer <code>local</code> in loops to avoid polluting the global namespace.</div>
  <div class="tip">Use tables to group related data instead of many separate variables.</div>
  <div class="warning">Using <code>global</code> variables can lead to hard-to-find bugs if scripts overwrite each other's values.</div>

  <h3>Challenges and Practice</h3>
  <div class="challenge">
    <strong>Challenge 1:</strong> Build a script that creates an inventory table for a player, adds three items, removes one, and prints all items.
  </div>
  <div class="challenge">
    <strong>Challenge 2:</strong> Write a function that accepts a table of scores and returns the highest score.
  </div>
  <div class="challenge">
    <strong>Challenge 3:</strong> Design a table for a shop with item names and prices, loop over the table, and print a formatted shop catalog.
  </div>
</section> <section id="operators">
  <h2>Luau Operators: Math, Comparison, Logical, Concatenation</h2>
  <blockquote>
    Operators are the "tools" you use to work with variables and values. They let you add, compare, combine, and make decisions in your scripts. Mastering operators is key to logic and gameplay mechanics!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. Arithmetic Operators</strong><br>
    These perform math: <code>+</code> (add), <code>-</code> (subtract), <code>*</code> (multiply), <code>/</code> (divide), <code>%</code> (modulo/remainder). Use them for scores, health, movement, and more.
  </div>
  <div class="deepdive">
    <strong>2. Comparison Operators</strong><br>
    These check if values are equal, not equal, greater, less, or at least/as much: <code>==</code>, <code>~=</code>, <code>&lt;</code>, <code>&gt;</code>, <code>&lt;=</code>, <code>&gt;=</code>. Use them for win conditions, unlocking, and logic.
  </div>
  <div class="deepdive">
    <strong>3. Logical Operators</strong><br>
    Combine or invert booleans: <code>and</code> (both true), <code>or</code> (either true), <code>not</code> (reverse true/false). Use for checks, branching, and advanced logic.
  </div>
  <div class="deepdive">
    <strong>4. Concatenation</strong><br>
    <code>..</code> combines strings. Build messages, names, and UI labels dynamically.
  </div>
  <div class="deepdive">
    <strong>5. Operator Precedence</strong><br>
    Some operators run before others (like math order of operations). Use parentheses to control calculation order: <code>(a + b) * c</code>.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Math operators (+, -, *, /) help you add, subtract, multiply, or divide numbers.</div>
  <div class="simple">Comparison operators (==, ~=, <, >) help you check if something is equal or bigger/smaller.</div>
  <div class="simple">Logical operators (and, or, not) let you combine yes/no checks for smarter decisions.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Addition</strong>
<pre><code>local score = 10 + 5
print(score) -- 15</code></pre></div>

  <div class="example"><strong>Example 2: Subtraction</strong>
<pre><code>local lives = 3
lives = lives - 1
print("Lives left:", lives)</code></pre></div>

  <div class="example"><strong>Example 3: Multiplication</strong>
<pre><code>local damage = 10 * 2
print("Double Damage:", damage)</code></pre></div>

  <div class="example"><strong>Example 4: Division</strong>
<pre><code>local coins = 100
local players = 4
local coinsPerPlayer = coins / players
print("Coins per player:", coinsPerPlayer)</code></pre></div>

  <div class="example"><strong>Example 5: Modulo (Remainder)</strong>
<pre><code>local turns = 7
print(turns % 2) -- 1 (odd/even check)</code></pre></div>

  <div class="example"><strong>Example 6: Equality Check</strong>
<pre><code>local key = "gold"
if key == "gold" then
  print("Door unlocks!")
end</code></pre></div>

  <div class="example"><strong>Example 7: Not Equal</strong>
<pre><code>local mode = "easy"
if mode ~= "hard" then
  print("Not hard mode!")
end</code></pre></div>

  <div class="example"><strong>Example 8: Greater Than</strong>
<pre><code>local score = 120
if score > 100 then
  print("High Score!")
end</code></pre></div>

  <div class="example"><strong>Example 9: Less Than</strong>
<pre><code>local health = 20
if health < 50 then
  print("Warning: Low health!")
end</code></pre></div>

  <div class="example"><strong>Example 10: Greater or Equal</strong>
<pre><code>local coins = 10
if coins >= 10 then
  print("You can buy the item!")
end</code></pre></div>

  <div class="example"><strong>Example 11: Logical AND</strong>
<pre><code>local hasKey = true
local doorOpen = false
if hasKey and not doorOpen then
  print("You can open the door!")
end</code></pre></div>

  <div class="example"><strong>Example 12: Logical OR</strong>
<pre><code>local isAdmin = false
local isVIP = true
if isAdmin or isVIP then
  print("Special access granted!")
end</code></pre></div>

  <div class="example"><strong>Example 13: NOT operator</strong>
<pre><code>local isDead = false
if not isDead then
  print("Keep playing!")
end</code></pre></div>

  <div class="example"><strong>Example 14: String Concatenation</strong>
<pre><code>local playerName = "Ray2fly2"
local greeting = "Hello, " .. playerName .. "!"
print(greeting)</code></pre></div>

  <div class="example"><strong>Example 15: Math Precedence</strong>
<pre><code>local result = 2 + 3 * 4 -- 2 + (3*4) = 14
local result2 = (2 + 3) * 4 -- (2+3)*4 = 20
print(result, result2)</code></pre></div>

  <div class="example"><strong>Example 16: Chained Logic</strong>
<pre><code>local coins = 25
local level = 7
if coins > 20 and level >= 5 then
  print("Unlock special item!")
end</code></pre></div>

  <div class="example"><strong>Example 17: Odd/Even Checker</strong>
<pre><code>local n = 8
if n % 2 == 0 then
  print("Even number")
else
  print("Odd number")
end</code></pre></div>

  <div class="example"><strong>Example 18: Checking Multiple Conditions</strong>
<pre><code>local score = 75
local health = 50
if score >= 70 or health >= 80 then
  print("You win bonus!")
end</code></pre></div>

  <div class="example"><strong>Example 19: Building a Message</strong>
<pre><code>local kills = 5
local msg = "You defeated " .. kills .. " enemies!"
print(msg)</code></pre></div>

  <div class="example"><strong>Example 20: Logical NOT with Comparison</strong>
<pre><code>local isPaused = false
if not isPaused then
  print("Game running!")
end</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong>
    1. Write a function that checks if a player's score is divisible by 10, and prints "Bonus!" if true.<br>
    2. Create a script that prints "Game Over" only if health is 0 and lives are 0.<br>
    3. Build a message that combines a player's name, score, and rank into a single string.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use parentheses <code>()</code> to control the order of math and logic. <code>2 + 3 * 4</code> is not the same as <code>(2+3)*4</code>.</div>
  <div class="warning">Don't use <code>=</code> for comparison—use <code>==</code>!</div>
  <div class="tip">Remember Lua/Luau counts <code>0</code> as <code>true</code> in logical checks (unlike some languages).</div>
  <div class="warning">String concatenation only works with strings! Use <code>tostring()</code> if needed: <code>"Score: " .. tostring(score)</code>.</div>
  <div class="tip">Modulo <code>%</code> is great for looping, cycling, or checking odd/even.</div>
</section> <section id="if-statements">
  <h2>If Statements: Decision Making in Luau</h2>
  <blockquote>
    If statements let your code make decisions! Use them to check conditions, branch your logic, and create interactive gameplay. Understanding if/else/elseif is essential for all scripting.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is an If Statement?</strong><br>
    An if statement checks if something is true. If it is, your code inside runs; otherwise, it skips. This is how you make your game react to player actions, game state, and more.
  </div>
  <div class="deepdive">
    <strong>2. Using Else and Elseif</strong><br>
    <code>else</code> runs code if the <code>if</code> isn’t true. <code>elseif</code> lets you check multiple conditions in order, giving you more control and complexity.
  </div>
  <div class="deepdive">
    <strong>3. Condition Types</strong><br>
    Conditions can use comparison (<code>==</code>, <code>&gt;</code>, etc.), logical operators (<code>and</code>, <code>or</code>), or even function calls that return true/false.
  </div>
  <div class="deepdive">
    <strong>4. Nesting If Statements</strong><br>
    You can put if statements inside other if statements (“nesting”) to build complex logic trees.
  </div>
  <div class="deepdive">
    <strong>5. Truthiness & Falsehood</strong><br>
    In Luau, anything that isn’t <code>false</code> or <code>nil</code> counts as “true”! Beware: <code>0</code> and empty strings <code>""</code> are still true.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">If statements ask “Is this true?” If yes, do something. If not, skip it.</div>
  <div class="simple">Else is your “otherwise”—it’s what happens when the first thing isn’t true.</div>
  <div class="simple">Elseif lets you check lots of things, one after the other.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Basic If</strong>
<pre><code>local health = 80
if health > 50 then
  print("You're healthy!")
end</code></pre></div>

  <div class="example"><strong>Example 2: If/Else</strong>
<pre><code>local coins = 5
if coins >= 10 then
  print("You can buy the sword!")
else
  print("Not enough coins.")
end</code></pre></div>

  <div class="example"><strong>Example 3: Elseif Chain</strong>
<pre><code>local score = 75
if score >= 100 then
  print("Gold Medal!")
elseif score >= 70 then
  print("Silver Medal!")
else
  print("Try again!")
end</code></pre></div>

  <div class="example"><strong>Example 4: Comparing Strings</strong>
<pre><code>local playerClass = "Mage"
if playerClass == "Mage" then
  print("Cast spells!")
elseif playerClass == "Warrior" then
  print("Swing sword!")
end</code></pre></div>

  <div class="example"><strong>Example 5: Multiple Conditions</strong>
<pre><code>local hasKey = true
local doorUnlocked = false
if hasKey and not doorUnlocked then
  print("Open the door!")
end</code></pre></div>

  <div class="example"><strong>Example 6: OR Condition</strong>
<pre><code>local isAdmin = false
local isVIP = true
if isAdmin or isVIP then
  print("Special access!")
end</code></pre></div>

  <div class="example"><strong>Example 7: Checking nil</strong>
<pre><code>local prize
if prize == nil then
  print("No prize awarded yet.")
end</code></pre></div>

  <div class="example"><strong>Example 8: Nested If</strong>
<pre><code>local level = 10
local hasBadge = true
if level >= 10 then
  if hasBadge then
    print("Unlocked secret area!")
  else
    print("Earn the badge first!")
  end
end</code></pre></div>

  <div class="example"><strong>Example 9: Function as Condition</strong>
<pre><code>function isAlive(hp)
  return hp > 0
end
if isAlive(50) then
  print("Keep fighting!")
end</code></pre></div>

  <div class="example"><strong>Example 10: Empty String Truthiness</strong>
<pre><code>local username = ""
if username then
  print("This will print!") -- Empty string is true
end</code></pre></div>

  <div class="example"><strong>Example 11: 0 Truthiness</strong>
<pre><code>local n = 0
if n then
  print("Zero is true!") -- In Lua/Luau, zero is true!
end</code></pre></div>

  <div class="example"><strong>Example 12: Inverting with NOT</strong>
<pre><code>local isPaused = false
if not isPaused then
  print("Game is running!")
end</code></pre></div>

  <div class="example"><strong>Example 13: Checking Table Key</strong>
<pre><code>local inventory = {sword = true}
if inventory.sword then
  print("You have a sword!")
end</code></pre></div>

  <div class="example"><strong>Example 14: If with Math</strong>
<pre><code>local coins = 13
if coins % 2 == 0 then
  print("Even number of coins!")
else
  print("Odd number of coins!")
end</code></pre></div>

  <div class="example"><strong>Example 15: Multi-Level Nesting</strong>
<pre><code>local health = 50
local armor = 20
if health > 0 then
  if armor > 0 then
    print("Protected!")
  else
    print("Vulnerable!")
  end
else
  print("Dead!")
end</code></pre></div>

  <div class="example"><strong>Example 16: Short-Circuit Evaluation</strong>
<pre><code>local x = nil
if x and x.value then
  print(x.value)
else
  print("x or x.value is nil")
end</code></pre></div>

  <div class="example"><strong>Example 17: Using elseif for Player Levels</strong>
<pre><code>local level = 7
if level < 5 then
  print("Beginner")
elseif level < 10 then
  print("Intermediate")
else
  print("Expert")
end</code></pre></div>

  <div class="example"><strong>Example 18: Checking for Item in Table</strong>
<pre><code>local shop = {sword = 50, shield = 30}
local item = "sword"
if shop[item] then
  print("Price is:", shop[item])
else
  print("Item not sold!")
end</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Write a script to check if a player’s health is &lt;= 0 and print “Game Over” if so.<br>
    2. Create a function that returns a rank (“Bronze”, “Silver”, “Gold”, “Platinum”) based on score using if/elseif/else.<br>
    3. Build a nested if to check if a player has both a key and a badge before unlocking a door.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always close your <code>if</code> statements with <code>end</code>!</div>
  <div class="warning">Don’t use <code>=</code> instead of <code>==</code> for comparison.</div>
  <div class="tip">Start with <code>if</code>, add <code>elseif</code> for more checks, end with <code>else</code> for “catch-all.”</div>
  <div class="tip">Beware: <code>nil</code> and <code>false</code> are the only false values in Luau. Everything else (numbers, strings, tables) is considered true!</div>
  <div class="warning">Don’t put assignment (<code>=</code>) inside a condition—use comparison.</div>
</section><section id="loops">
  <h2>Loops: Repeating Actions in Luau</h2>
  <blockquote>
    Loops let your scripts repeat actions many times, process lists, and automate tasks. Mastering loops is crucial for managing collections, timers, and game logic!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is a Loop?</strong><br>
    A loop runs the same block of code multiple times. Use loops to process tables, update objects, run timers, or create effects.
  </div>
  <div class="deepdive">
    <strong>2. For Loops</strong><br>
    <code>for</code> loops run a set number of times (e.g., <code>for i = 1, 10 do</code>). Perfect for counting, iterating through lists, and repeating tasks.
  </div>
  <div class="deepdive">
    <strong>3. While Loops</strong><br>
    <code>while</code> loops continue as long as a condition is true. Great for timers, waiting, or running until something changes.
  </div>
  <div class="deepdive">
    <strong>4. Repeat-Until Loops</strong><br>
    <code>repeat ... until</code> loops run at least once, and stop when a condition becomes true. Use for situations where you want to check after running.
  </div>
  <div class="deepdive">
    <strong>5. Looping Over Tables</strong><br>
    Use <code>pairs()</code> or <code>ipairs()</code> to loop through all values in a table, whether it’s an array or a dictionary.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">A loop is like a robot doing the same thing over and over, until you tell it to stop.</div>
  <div class="simple">For loops count up or down. While loops keep going if something is true. Repeat-until always runs once.</div>
  <div class="simple">Loop through lists to work with every item automatically.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Basic For Loop</strong>
<pre><code>for i = 1, 5 do
  print("Step:", i)
end</code></pre></div>

  <div class="example"><strong>Example 2: For Loop Counting Down</strong>
<pre><code>for i = 10, 1, -1 do
  print("Countdown:", i)
end</code></pre></div>

  <div class="example"><strong>Example 3: While Loop</strong>
<pre><code>local timer = 5
while timer > 0 do
  print("Time left:", timer)
  timer = timer - 1
end</code></pre></div>

  <div class="example"><strong>Example 4: Repeat-Until Loop</strong>
<pre><code>local tries = 0
repeat
  tries = tries + 1
until tries == 3
print("Done trying:", tries)</code></pre></div>

  <div class="example"><strong>Example 5: Loop Over Array with ipairs</strong>
<pre><code>local enemies = {"Slime", "Goblin", "Dragon"}
for i, enemy in ipairs(enemies) do
  print("Enemy #" .. i .. ": " .. enemy)
end</code></pre></div>

  <div class="example"><strong>Example 6: Loop Over Dictionary with pairs</strong>
<pre><code>local stats = {health = 100, mana = 50}
for key, value in pairs(stats) do
  print(key .. ":", value)
end</code></pre></div>

  <div class="example"><strong>Example 7: Break Statement</strong>
<pre><code>for i = 1, 10 do
  if i == 5 then
    print("Stopping early!")
    break
  end
end</code></pre></div>

  <div class="example"><strong>Example 8: Continue Statement</strong>
<pre><code>for i = 1, 5 do
  if i == 3 then
    continue -- skip this round (Luau only!)
  end
  print(i)
end</code></pre></div>

  <div class="example"><strong>Example 9: Loop Over Players</strong>
<pre><code>for _, player in pairs(game.Players:GetPlayers()) do
  print("Player:", player.Name)
end</code></pre></div>

  <div class="example"><strong>Example 10: Nested Loops</strong>
<pre><code>for i = 1, 3 do
  for j = 1, 2 do
    print("i:", i, "j:", j)
  end
end</code></pre></div>

  <div class="example"><strong>Example 11: Loop With Condition</strong>
<pre><code>local coins = {10, 25, 50, 100}
for _, coin in ipairs(coins) do
  if coin >= 50 then
    print("Big coin:", coin)
  end
end</code></pre></div>

  <div class="example"><strong>Example 12: Early Exit from While Loop</strong>
<pre><code>local health = 100
while health > 0 do
  health = health - 15
  if health <= 40 then
    print("Low health, exiting loop!")
    break
  end
end</code></pre></div>

  <div class="example"><strong>Example 13: Repeat-Until With Condition</strong>
<pre><code>local input
repeat
  input = math.random(1,10)
  print("Random number:", input)
until input == 7
print("Got lucky 7!")</code></pre></div>

  <div class="example"><strong>Example 14: Table Manipulation in Loop</strong>
<pre><code>local scores = {5, 10, 15}
for i, value in ipairs(scores) do
  scores[i] = value * 2
end
print(scores[1], scores[2], scores[3]) -- 10, 20, 30</code></pre></div>

  <div class="example"><strong>Example 15: Looping Through Workspace Parts</strong>
<pre><code>for _, obj in ipairs(workspace:GetChildren()) do
  if obj:IsA("Part") then
    print("Found part:", obj.Name)
  end
end</code></pre></div>

  <div class="example"><strong>Example 16: Timer Countdown With While</strong>
<pre><code>local countdown = 10
while countdown > 0 do
  print(countdown)
  wait(1)
  countdown = countdown - 1
end
print("Timer finished!")</code></pre></div>

  <div class="example"><strong>Example 17: Looping With Function Calls</strong>
<pre><code>local enemies = {"A", "B", "C"}
function defeat(name)
  print(name .. " defeated!")
end
for _, enemy in ipairs(enemies) do
  defeat(enemy)
end</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Write a loop to print every player's name and score in a table.<br>
    2. Build a timer that counts down from 5 and prints "Go!" when finished.<br>
    3. Use a for loop to create 10 parts in Workspace, each with a unique color.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">For loops are fastest for counting. Use pairs/ipairs for tables. While loops are best for unknown lengths.</div>
  <div class="warning">Don’t create infinite loops that never end! Always include a way to stop.</div>
  <div class="tip">Break exits a loop early. Continue skips to the next round (Luau only).</div>
  <div class="warning">Don’t modify the table you’re looping through in a way that changes its length, unless you know what you’re doing!</div>
  <div class="tip">Nested loops let you work with grids, pairs, combos, etc.</div>
</section><section id="functions">
  <h2>Functions: Reusable Code Blocks in Luau</h2>
  <blockquote>
    Functions help you organize your code, avoid repetition, and make your scripts more readable and powerful. Mastering functions is essential for building scalable Roblox games!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is a Function?</strong><br>
    A function is a named block of code that you can run (call) whenever you want. Functions let you reuse logic, handle events, and break up complex scripts into simpler parts.
  </div>
  <div class="deepdive">
    <strong>2. Parameters and Arguments</strong><br>
    Functions can accept inputs, called <code>parameters</code>. When you call the function, you provide <code>arguments</code> (real values) for those parameters.
  </div>
  <div class="deepdive">
    <strong>3. Returning Values</strong><br>
    Functions can use <code>return</code> to give back a value. This lets you process data inside the function and use the result elsewhere.
  </div>
  <div class="deepdive">
    <strong>4. Anonymous Functions</strong><br>
    Luau supports anonymous (nameless) functions. These are useful for event callbacks, quick logic, or passing a function as a value.
  </div>
  <div class="deepdive">
    <strong>5. Scope and Closures</strong><br>
    Functions create their own scope. Inner functions can “remember” variables from their parent context (closure). This is powerful for timers, counters, and custom event handlers.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">A function is a named list of instructions. Call it whenever you want!</div>
  <div class="simple">Give inputs to functions, get results back. Like a math machine!</div>
  <div class="simple">Functions help you organize your code and avoid repeating yourself.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Basic Function</strong>
<pre><code>function greet()
  print("Hello, Roblox!")
end
greet()</code></pre></div>

  <div class="example"><strong>Example 2: Function with Parameters</strong>
<pre><code>function greetPlayer(name)
  print("Hello, " .. name .. "!")
end
greetPlayer("Ray2fly2")</code></pre></div>

  <div class="example"><strong>Example 3: Function Returning Value</strong>
<pre><code>function add(a, b)
  return a + b
end
local sum = add(5, 8)
print("Sum:", sum)</code></pre></div>

  <div class="example"><strong>Example 4: Function with Multiple Parameters</strong>
<pre><code>function printStats(health, mana, coins)
  print("Health:", health, "Mana:", mana, "Coins:", coins)
end
printStats(90, 50, 30)</code></pre></div>

  <div class="example"><strong>Example 5: Anonymous Function</strong>
<pre><code>local sayBye = function()
  print("Goodbye!")
end
sayBye()</code></pre></div>

  <div class="example"><strong>Example 6: Function Callback for Event</strong>
<pre><code>local function onJoin(player)
  print(player.Name .. " joined!")
end
game.Players.PlayerAdded:Connect(onJoin)</code></pre></div>

  <div class="example"><strong>Example 7: Function as Table Value</strong>
<pre><code>local actions = {
  jump = function() print("Jump!") end,
  run = function() print("Run!") end
}
actions.jump()</code></pre></div>

  <div class="example"><strong>Example 8: Function with Default Parameter</strong>
<pre><code>function heal(amount)
  amount = amount or 10
  print("Healed by", amount)
end
heal()       -- 10
heal(25)     -- 25</code></pre></div>

  <div class="example"><strong>Example 9: Returning Multiple Values</strong>
<pre><code>function stats()
  return 100, 50, 25 -- health, mana, coins
end
local h, m, c = stats()
print(h, m, c)</code></pre></div>

  <div class="example"><strong>Example 10: Closure (Remembering State)</strong>
<pre><code>function makeCounter()
  local count = 0
  return function()
    count = count + 1
    return count
  end
end
local counter = makeCounter()
print(counter()) -- 1
print(counter()) -- 2</code></pre></div>

  <div class="example"><strong>Example 11: Function Used in Loop</strong>
<pre><code>function double(x)
  return x * 2
end
for i = 1, 3 do
  print(double(i))
end</code></pre></div>

  <div class="example"><strong>Example 12: Function Returns Boolean</strong>
<pre><code>function isEven(n)
  return n % 2 == 0
end
print(isEven(4)) -- true
print(isEven(5)) -- false</code></pre></div>

  <div class="example"><strong>Example 13: Table of Functions for Actions</strong>
<pre><code>local commands = {
  attack = function() print("Attack!") end,
  defend = function() print("Defend!") end
}
commands["attack"]()</code></pre></div>

  <div class="example"><strong>Example 14: Function with Table Parameter</strong>
<pre><code>function printInventory(items)
  for _, item in pairs(items) do
    print("Item:", item)
  end
end
printInventory({"Sword", "Potion", "Shield"})</code></pre></div>

  <div class="example"><strong>Example 15: Recursive Function</strong>
<pre><code>function factorial(n)
  if n == 0 then return 1 end
  return n * factorial(n-1)
end
print(factorial(5)) -- 120</code></pre></div>

  <div class="example"><strong>Example 16: Function for Data Validation</strong>
<pre><code>function validName(name)
  return #name > 2 and #name < 16
end
print(validName("Ra"))      -- false
print(validName("Ray2fly2"))-- true</code></pre></div>

  <div class="example"><strong>Example 17: Function for Filtering Table</strong>
<pre><code>function filterEven(tbl)
  local result = {}
  for _, num in ipairs(tbl) do
    if num % 2 == 0 then
      table.insert(result, num)
    end
  end
  return result
end
local evens = filterEven({1,2,3,4,5,6})
print(table.concat(evens, ", ")) -- 2, 4, 6</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Write a function to calculate a player's level from their XP.<br>
    2. Create a function that prints every item in a player's inventory.<br>
    3. Build a closure that counts how many times a button is clicked.<br>
    4. Write a recursive function to print all children of a Model (tree structure).
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always use <code>local</code> for functions unless you need them globally.</div>
  <div class="warning">Don’t forget to call your function (<code>myFunc()</code>)! Defining it isn’t enough.</div>
  <div class="tip">Use parameters to make your functions flexible and reusable.</div>
  <div class="warning">Remember to use <code>return</code> to give back values; otherwise, functions default to <code>nil</code>.</div>
  <div class="tip">Closures are powerful for event handlers and keeping track of state between calls.</div>
</section><section id="scope">
  <h2>Scope: Where Variables and Functions Exist in Luau</h2>
  <blockquote>
    Scope controls where variables and functions are visible and usable within your scripts. Understanding scope is essential for avoiding bugs, keeping code clean, and writing reusable functions and modules!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. Local vs. Global Scope</strong><br>
    <code>local</code> variables exist only inside the block, loop, or function where they're declared. Global variables are accessible anywhere in the script and can even be accessed by other scripts—this can lead to naming conflicts and bugs!
  </div>
  <div class="deepdive">
    <strong>2. Block Scope</strong><br>
    In Luau, any code between <code>do ... end</code> or inside a loop or function is a block. A variable declared with <code>local</code> inside a block is not accessible outside that block.
  </div>
  <div class="deepdive">
    <strong>3. Function Scope</strong><br>
    Variables declared inside a function (with <code>local</code>) are only accessible within that function. This allows you to write functions that don't interfere with outside code.
  </div>
  <div class="deepdive">
    <strong>4. Upvalues & Closures</strong><br>
    Functions can access variables in their parent scope (these are called "upvalues"). This is useful for callbacks and keeping state between function calls.
  </div>
  <div class="deepdive">
    <strong>5. Avoiding Pollution</strong><br>
    Always prefer <code>local</code> for variables and functions unless you absolutely need globals. This keeps your code modular, bug-free, and easier to debug.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">"Scope" is where your variable or function "lives" and can be seen.</div>
  <div class="simple">Local means only inside this spot. Global means everywhere (be careful!).</div>
  <div class="simple">Use <code>local</code> to avoid mixing up your code with other scripts.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Local Variable in Function</strong>
<pre><code>function show()
  local msg = "Hi"
  print(msg)
end
show()
print(msg) -- Error: msg is not defined here</code></pre></div>

  <div class="example"><strong>Example 2: Global Variable</strong>
<pre><code>score = 10 -- global variable (not recommended)
function add()
  score = score + 5
end
add()
print(score) -- 15</code></pre></div>

  <div class="example"><strong>Example 3: Local in Block</strong>
<pre><code>do
  local secret = 42
  print(secret)
end
print(secret) -- Error: secret is not defined here</code></pre></div>

  <div class="example"><strong>Example 4: Local in For Loop</strong>
<pre><code>for i = 1, 3 do
  local temp = i * 10
  print(temp)
end
print(temp) -- Error: temp is not defined here</code></pre></div>

  <div class="example"><strong>Example 5: Upvalue Access (Closure)</strong>
<pre><code>local count = 0
function increment()
  count = count + 1
  return count
end
print(increment()) -- 1
print(increment()) -- 2</code></pre></div>

  <div class="example"><strong>Example 6: Nested Functions and Scope</strong>
<pre><code>function outer()
  local outerVar = "outside"
  function inner()
    print(outerVar)
  end
  inner()
end
outer()</code></pre></div>

  <div class="example"><strong>Example 7: Variable Shadowing</strong>
<pre><code>local x = 5
do
  local x = 10
  print(x) -- 10
end
print(x) -- 5</code></pre></div>

  <div class="example"><strong>Example 8: Table Scope</strong>
<pre><code>local stats = {health = 100}
function changeStats()
  stats.health = stats.health + 10
end
changeStats()
print(stats.health) -- 110</code></pre></div>

  <div class="example"><strong>Example 9: Scope Across Scripts (Global)</strong>
<pre><code>-- Script 1
shared.value = 99
-- Script 2
print(shared.value) -- 99</code></pre></div>

  <div class="example"><strong>Example 10: Function as Upvalue</strong>
<pre><code>local function makeMultiplier(n)
  return function(x)
    return n * x
  end
end
local times5 = makeMultiplier(5)
print(times5(3)) -- 15</code></pre></div>

  <div class="example"><strong>Example 11: Local Function</strong>
<pre><code>local function hello()
  print("Hello!")
end
hello()
-- hello is not global</code></pre></div>

  <div class="example"><strong>Example 12: Scope in Loops</strong>
<pre><code>for i = 1, 2 do
  local temp = i * 2
  print(temp)
end
-- temp is not accessible here</code></pre></div>

  <div class="example"><strong>Example 13: Accessing Parent Scope</strong>
<pre><code>local bonus = 100
function showBonus()
  print("Bonus:", bonus)
end
showBonus()</code></pre></div>

  <div class="example"><strong>Example 14: Scope in ModuleScripts</strong>
<pre><code>-- In ModuleScript
local M = {}
local secret = "hidden"
function M.reveal()
  return secret
end
return M

-- In another Script
local mod = require(game.ReplicatedStorage.ModuleScript)
print(mod.reveal()) -- "hidden"</code></pre></div>

  <div class="example"><strong>Example 15: Accidental Global Variable</strong>
<pre><code>function foo()
  x = 123 -- global: bad practice!
end
foo()
print(x) -- 123</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Create a function that keeps its own score using a local variable.<br>
    2. Demonstrate variable shadowing by declaring the same variable name in two different blocks.<br>
    3. Write a module that has a local secret value and a function to reveal it.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always use <code>local</code> for variables and functions unless you need global access.</div>
  <div class="warning">Accidental globals can lead to hard-to-find bugs and conflicts between scripts.</div>
  <div class="tip">Use closures to keep state between function calls.</div>
  <div class="warning">Don't rely on the order of variable declarations—declare variables before you use them!</div>
  <div class="tip">ModuleScripts let you encapsulate logic and keep variables private to the module.</div>
</section><section id="oop-modules-metatables">
  <h2>Object-Oriented Programming (OOP) with ModuleScripts & Metatables</h2>
  <blockquote>
    OOP lets you organize game logic as reusable objects: players, enemies, items, abilities, and more. In Roblox, you use ModuleScripts and metatables to build OOP systems. This section will teach you how to structure code for scalability, flexibility, and teamwork!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is OOP?</strong><br>
    OOP (Object-Oriented Programming) is a way of organizing code as "objects" with data (properties) and actions (methods). These objects model real-world things and can interact, inherit features, and be extended.
  </div>
  <div class="deepdive">
    <strong>2. ModuleScripts for Classes</strong><br>
    In Roblox, you use ModuleScripts to define reusable "classes." You return a table with functions and properties, then require it from other scripts to create new objects.
  </div>
  <div class="deepdive">
    <strong>3. Metatables and __index</strong><br>
    Metatables let you customize how tables behave. The <code>__index</code> field is used to enable inheritance—so your objects reference their "class" table for shared methods.
  </div>
  <div class="deepdive">
    <strong>4. Constructors and Factories</strong><br>
    A "constructor" is a function (often <code>.new()</code>) that creates and initializes objects. You use it to set up properties, link metatables, and return new instances.
  </div>
  <div class="deepdive">
    <strong>5. Encapsulation and Reusability</strong><br>
    OOP lets you hide implementation details and expose only what matters. Use <code>local</code> variables inside modules for "private" data, and public methods for interaction.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">OOP is like making blueprints (classes) for things, then building many copies (objects) from them.</div>
  <div class="simple">ModuleScripts are your toolboxes for objects. Metatables help objects share code.</div>
  <div class="simple">Use <code>MyClass.new()</code> to make new things with their own data and actions.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Basic ModuleScript Class</strong>
<pre><code>-- In ModuleScript "PlayerClass"
local Player = {}
Player.__index = Player

function Player.new(name)
  local self = setmetatable({}, Player)
  self.name = name
  self.score = 0
  return self
end

function Player:addScore(points)
  self.score = self.score + points
end

return Player

-- In another script
local PlayerClass = require(game.ReplicatedStorage.PlayerClass)
local p1 = PlayerClass.new("Ray2fly2")
p1:addScore(10)
print(p1.name, p1.score) -- "Ray2fly2", 10</code></pre></div>

  <div class="example"><strong>Example 2: Enemy Class with Methods</strong>
<pre><code>-- ModuleScript "Enemy"
local Enemy = {}
Enemy.__index = Enemy

function Enemy.new(type)
  local self = setmetatable({}, Enemy)
  self.type = type
  self.health = 100
  return self
end

function Enemy:takeDamage(amount)
  self.health = self.health - amount
end

return Enemy

-- Script
local EnemyClass = require(game.ReplicatedStorage.Enemy)
local goblin = EnemyClass.new("Goblin")
goblin:takeDamage(30)
print(goblin.type, goblin.health) -- "Goblin", 70</code></pre></div>

  <div class="example"><strong>Example 3: Item Class with Private Data</strong>
<pre><code>-- ModuleScript "Item"
local Item = {}
Item.__index = Item

local itemCount = 0 -- private!

function Item.new(name)
  local self = setmetatable({}, Item)
  self.name = name
  itemCount = itemCount + 1
  self.id = itemCount
  return self
end

return Item

-- Script
local ItemClass = require(game.ReplicatedStorage.Item)
local sword = ItemClass.new("Sword")
print(sword.name, sword.id)</code></pre></div>

  <div class="example"><strong>Example 4: Inheritance with __index</strong>
<pre><code>-- Base "Character"
local Character = {}
Character.__index = Character
function Character:new(name)
  local self = setmetatable({}, Character)
  self.name = name
  return self
end

-- Subclass "NPC"
local NPC = setmetatable({}, {__index = Character})
NPC.__index = NPC

function NPC:new(name, role)
  local self = setmetatable(Character:new(name), NPC)
  self.role = role
  return self
end

-- Script
local villager = NPC:new("Bob", "Shopkeeper")
print(villager.name, villager.role)</code></pre></div>

  <div class="example"><strong>Example 5: Factory Pattern for Bullets</strong>
<pre><code>-- ModuleScript "BulletFactory"
local Bullet = {}
Bullet.__index = Bullet

function Bullet.new(speed, damage)
  local self = setmetatable({}, Bullet)
  self.speed = speed
  self.damage = damage
  return self
end

return Bullet

-- Script
local BulletFactory = require(game.ReplicatedStorage.BulletFactory)
local b1 = BulletFactory.new(100, 25)
local b2 = BulletFactory.new(150, 40)
print(b1.damage, b2.speed)</code></pre></div>

  <div class="example"><strong>Example 6: Shared Methods</strong>
<pre><code>-- ModuleScript "PowerUp"
local PowerUp = {}
PowerUp.__index = PowerUp

function PowerUp.new(type)
  local self = setmetatable({}, PowerUp)
  self.type = type
  return self
end

function PowerUp:activate(target)
  print("Activated " .. self.type .. " for " .. target.name)
end

return PowerUp</code></pre></div>

  <div class="example"><strong>Example 7: Metatable Magic</strong>
<pre><code>local MyTable = {}
setmetatable(MyTable, {
  __index = function(tbl, key)
    return "No value for " .. key
  end
})
print(MyTable.apple) -- "No value for apple"</code></pre></div>

  <div class="example"><strong>Example 8: Player Inventory OOP</strong>
<pre><code>-- ModuleScript "Inventory"
local Inventory = {}
Inventory.__index = Inventory

function Inventory.new()
  local self = setmetatable({}, Inventory)
  self.items = {}
  return self
end

function Inventory:addItem(item)
  table.insert(self.items, item)
end

return Inventory

-- Script
local InventoryClass = require(game.ReplicatedStorage.Inventory)
local inv = InventoryClass.new()
inv:addItem("Potion")
print(inv.items[1]) -- "Potion"</code></pre></div>

  <div class="example"><strong>Example 9: Polymorphism with Methods</strong>
<pre><code>local Shape = {}
Shape.__index = Shape
function Shape:area() return 0 end

local Circle = {}
Circle.__index = Circle
setmetatable(Circle, {__index = Shape})

function Circle.new(radius)
  local self = setmetatable({}, Circle)
  self.radius = radius
  return self
end

function Circle:area()
  return math.pi * self.radius * self.radius
end

local c = Circle.new(5)
print(c:area())</code></pre></div>

  <div class="example"><strong>Example 10: Encapsulation with Local Data</strong>
<pre><code>-- ModuleScript "BankAccount"
local BankAccount = {}
BankAccount.__index = BankAccount

local totalAccounts = 0

function BankAccount.new(owner, balance)
  local self = setmetatable({}, BankAccount)
  self.owner = owner
  self.balance = balance
  totalAccounts = totalAccounts + 1
  self.id = totalAccounts
  return self
end

function BankAccount:getID()
  return self.id
end

return BankAccount</code></pre></div>

  <div class="example"><strong>Example 11: Static Methods (Class Functions)</strong>
<pre><code>local MathHelper = {}
function MathHelper.add(a, b)
  return a + b
end
function MathHelper.sub(a, b)
  return a - b
end
print(MathHelper.add(3, 7))</code></pre></div>

  <div class="example"><strong>Example 12: Object Methods vs Table Functions</strong>
<pre><code>local Car = {}
Car.__index = Car
function Car.new(name)
  local self = setmetatable({}, Car)
  self.name = name
  return self
end
function Car:drive()
  print(self.name .. " is driving!")
end
local myCar = Car.new("Speedster")
myCar:drive()</code></pre></div>

  <div class="example"><strong>Example 13: Overriding Methods</strong>
<pre><code>local Animal = {}
Animal.__index = Animal
function Animal:speak()
  print("Animal sound")
end

local Dog = setmetatable({}, {__index = Animal})
Dog.__index = Dog
function Dog:speak()
  print("Woof!")
end

local pet = setmetatable({}, Dog)
pet:speak() -- "Woof!"</code></pre></div>

  <div class="example"><strong>Example 14: Custom __tostring Metamethod</strong>
<pre><code>local Hero = {}
Hero.__index = Hero
function Hero.new(name)
  local self = setmetatable({}, Hero)
  self.name = name
  return self
end

setmetatable(Hero, {
  __tostring = function(tbl)
    return "Hero Class"
  end
})

local h = Hero.new("Max")
print(h) -- table address, but you can use __tostring on instances too</code></pre></div>

  <div class="example"><strong>Example 15: Simple Singleton Module</strong>
<pre><code>-- ModuleScript "GameSettings"
local Settings = {
  maxPlayers = 10,
  roundTime = 60
}
return Settings

-- Script
local GameSettings = require(game.ReplicatedStorage.GameSettings)
print(GameSettings.roundTime)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Create a ModuleScript for a "Pet" class with name, type, and a feed() method.<br>
    2. Use inheritance to make a "FlyingPet" subclass with a fly() method.<br>
    3. Make a module for "ShopItem" that tracks price and purchase count, with a buy() method.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always use <code>__index</code> in metatables for inheritance and method sharing.</div>
  <div class="warning">If you forget <code>setmetatable()</code>, your methods won’t work!</div>
  <div class="tip">Use <code>local</code> for private data inside ModuleScripts.</div>
  <div class="tip">Return your class table at the end of ModuleScripts so other scripts can require them.</div>
  <div class="warning">Don’t accidentally overwrite built-in keys (like __index, __tostring) unless you mean to customize them!</div>
</section><section id="events-connections">
  <h2>Events & Connections: Making Your Game React!</h2>
  <blockquote>
    Events let your game react to the world—players joining, parts being touched, buttons clicked, timers firing, and more. Connecting code to events is essential for interactive gameplay and dynamic worlds!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is an Event?</strong><br>
    An event is a signal sent out when something happens (like a player joining or a part being touched). You can connect code to run when that event fires.
  </div>
  <div class="deepdive">
    <strong>2. Connecting Functions to Events</strong><br>
    Use <code>:Connect()</code> to link a function to an event. When the event happens, your function runs automatically.
  </div>
  <div class="deepdive">
    <strong>3. Common Roblox Events</strong><br>
    Popular events include <code>.Touched</code> (when a part is touched), <code>.Clicked</code> (with <code>ClickDetector</code>), <code>.PlayerAdded</code> (when a player joins), <code>.Changed</code> (when a property changes), and <code>.ChildAdded</code> (when something is added to a parent).
  </div>
  <div class="deepdive">
    <strong>4. Disconnecting Events</strong><br>
    Connections can be disabled with <code>:Disconnect()</code> to stop your function from running when the event fires.
  </div>
  <div class="deepdive">
    <strong>5. Event Arguments</strong><br>
    Most events pass values (arguments) to your function: the object touched, the player joining, or the new value. Always check event documentation for what arguments are sent.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Events let your code "listen" for things happening and react right away!</div>
  <div class="simple">Use <code>:Connect()</code> to attach your function to an event, like plugging in a lamp.</div>
  <div class="simple">Some events give you extra info, like which player touched a part.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Part Touched Event</strong>
<pre><code>workspace.Part.Touched:Connect(function(hit)
  print("Part was touched by:", hit.Name)
end)</code></pre></div>

  <div class="example"><strong>Example 2: ClickDetector Clicked</strong>
<pre><code>local detector = Instance.new("ClickDetector", workspace.Part)
detector.MouseClick:Connect(function(player)
  print(player.Name .. " clicked the part!")
end)</code></pre></div>

  <div class="example"><strong>Example 3: PlayerAdded Event</strong>
<pre><code>game.Players.PlayerAdded:Connect(function(player)
  print(player.Name .. " has joined the game!")
end)</code></pre></div>

  <div class="example"><strong>Example 4: ChildAdded to Workspace</strong>
<pre><code>workspace.ChildAdded:Connect(function(child)
  print("New object added:", child.Name)
end)</code></pre></div>

  <div class="example"><strong>Example 5: Property Changed Event</strong>
<pre><code>workspace.Part.Changed:Connect(function(property)
  print("Part property changed:", property)
end)</code></pre></div>

  <div class="example"><strong>Example 6: Disconnecting an Event</strong>
<pre><code>local connection
connection = workspace.Part.Touched:Connect(function(hit)
  print("Touched once!")
  connection:Disconnect()
end)</code></pre></div>

  <div class="example"><strong>Example 7: Button Clicked Event (GUI)</strong>
<pre><code>local button = script.Parent
button.MouseButton1Click:Connect(function()
  print("Button was clicked!")
end)</code></pre></div>

  <div class="example"><strong>Example 8: Event with Multiple Arguments</strong>
<pre><code>game.ReplicatedStorage.RemoteEvent.OnServerEvent:Connect(function(player, data)
  print(player.Name .. " triggered remote with data:", data)
end)</code></pre></div>

  <div class="example"><strong>Example 9: Touching Specific Object</strong>
<pre><code>workspace.Part.Touched:Connect(function(hit)
  if hit.Name == "PlayerPart" then
    print("Player touched the part!")
  end
end)</code></pre></div>

  <div class="example"><strong>Example 10: Connecting Multiple Functions</strong>
<pre><code>local function greet()
  print("Hello!")
end
local function warn()
  print("Warning!")
end
workspace.Part.Touched:Connect(greet)
workspace.Part.Touched:Connect(warn)</code></pre></div>

  <div class="example"><strong>Example 11: Debounce with Events</strong>
<pre><code>local debounce = false
workspace.Part.Touched:Connect(function(hit)
  if not debounce then
    debounce = true
    print("Touched!")
    wait(1)
    debounce = false
  end
end)</code></pre></div>

  <div class="example"><strong>Example 12: GUI Event Passing Arguments</strong>
<pre><code>local btn = script.Parent
btn.MouseButton1Click:Connect(function(x, y)
  print("Clicked at:", x, y)
end)</code></pre></div>

  <div class="example"><strong>Example 13: ChildRemoved Event</strong>
<pre><code>workspace.ChildRemoved:Connect(function(child)
  print("Object removed:", child.Name)
end)</code></pre></div>

  <div class="example"><strong>Example 14: RemoteEvent for Cross-Script Communication</strong>
<pre><code>game.ReplicatedStorage.MyRemoteEvent.OnServerEvent:Connect(function(player, message)
  print(player.Name .. " sent:", message)
end)</code></pre></div>

  <div class="example"><strong>Example 15: Event Connection with Custom Function</strong>
<pre><code>function onTouch(hit)
  print("Touched by:", hit.Name)
end
workspace.Part.Touched:Connect(onTouch)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Make a part print a message only the first time it is touched.<br>
    2. Connect a GUI button to grant coins when clicked.<br>
    3. Track every time a child is added to Workspace and keep a running count.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always check what arguments an event provides—use them to make your code smarter!</div>
  <div class="warning">Forget to <code>:Disconnect()</code>? Your code could run multiple times or cause memory leaks.</div>
  <div class="tip">Use debounce patterns to prevent repeated triggers from rapid events.</div>
  <div class="tip">You can connect multiple functions to a single event—great for modular code!</div>
  <div class="warning">Don’t assume events fire only once—most fire every time the action occurs!</div>
</section><section id="remotes-bindables">
  <h2>RemoteEvents, RemoteFunctions, BindableEvents, BindableFunctions: Messaging Between Scripts</h2>
  <blockquote>
    Roblox separates scripts by context—server and client. Remotes and bindables let you communicate and trigger actions across scripts, making multiplayer and modular features possible!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. RemoteEvents</strong><br>
    RemoteEvents let you send signals and data between the client and server (and vice versa). Use <code>:FireServer()</code> and <code>:FireClient()</code> to trigger events across boundaries.
  </div>
  <div class="deepdive">
    <strong>2. RemoteFunctions</strong><br>
    RemoteFunctions are similar, but let you ask for a response (return value) from the other side. Use <code>:InvokeServer()</code> and <code>:InvokeClient()</code>.
  </div>
  <div class="deepdive">
    <strong>3. BindableEvents</strong><br>
    BindableEvents work only within the same context (server-to-server or client-to-client). Great for modular code that needs to send signals between scripts on the same side.
  </div>
  <div class="deepdive">
    <strong>4. BindableFunctions</strong><br>
    BindableFunctions work like BindableEvents, but expect a return value. Use these for local function calls between scripts.
  </div>
  <div class="deepdive">
    <strong>5. Safe Communication</strong><br>
    Always validate data sent between scripts! Never trust the client blindly—always check permissions and expected values on the server.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">RemoteEvents let your scripts "talk" between server and client, like sending a message.</div>
  <div class="simple">RemoteFunctions ask for a reply, not just a signal.</div>
  <div class="simple">Bindables work inside one side only—no server/client crossing.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Fire RemoteEvent from Client to Server</strong>
<pre><code>-- Client Script
game.ReplicatedStorage.MyRemoteEvent:FireServer("Hello from client!")

-- Server Script
game.ReplicatedStorage.MyRemoteEvent.OnServerEvent:Connect(function(player, msg)
  print(player.Name .. " says:", msg)
end)</code></pre></div>

  <div class="example"><strong>Example 2: Fire RemoteEvent from Server to Client</strong>
<pre><code>-- Server Script
game.ReplicatedStorage.MyRemoteEvent:FireClient(game.Players.SomePlayer, "Hello client!")

-- Client Script
game.ReplicatedStorage.MyRemoteEvent.OnClientEvent:Connect(function(msg)
  print("Server says:", msg)
end)</code></pre></div>

  <div class="example"><strong>Example 3: Fire RemoteEvent to All Clients</strong>
<pre><code>-- Server Script
game.ReplicatedStorage.MyRemoteEvent:FireAllClients("Global message!")</code></pre></div>

  <div class="example"><strong>Example 4: RemoteFunction InvokeServer/Return Value</strong>
<pre><code>-- Client Script
local result = game.ReplicatedStorage.MyRemoteFunction:InvokeServer(42)
print("Server replied:", result)

-- Server Script
game.ReplicatedStorage.MyRemoteFunction.OnServerInvoke = function(player, number)
  return number * 2
end</code></pre></div>

  <div class="example"><strong>Example 5: RemoteFunction InvokeClient/Return Value</strong>
<pre><code>-- Server Script
local reply = game.ReplicatedStorage.MyRemoteFunction:InvokeClient(game.Players.SomePlayer, "Ping")
print("Client replied:", reply)

-- Client Script
game.ReplicatedStorage.MyRemoteFunction.OnClientInvoke = function(msg)
  return msg .. " Pong"
end</code></pre></div>

  <div class="example"><strong>Example 6: BindableEvent—One-way Signal</strong>
<pre><code>-- Script A
local event = Instance.new("BindableEvent", game.ReplicatedStorage)
event.Name = "MyBindableEvent"
event:Fire("Hi from A!")

-- Script B
game.ReplicatedStorage.MyBindableEvent.Event:Connect(function(msg)
  print("Received:", msg)
end)</code></pre></div>

  <div class="example"><strong>Example 7: BindableFunction—Request/Response</strong>
<pre><code>-- Script A
local func = Instance.new("BindableFunction", game.ReplicatedStorage)
func.Name = "MyBindableFunction"

-- Script B
game.ReplicatedStorage.MyBindableFunction.OnInvoke = function(x)
  return x * 100
end

-- Script A
local result = func:Invoke(7)
print("Result:", result)</code></pre></div>

  <div class="example"><strong>Example 8: Passing Tables with Remotes</strong>
<pre><code>-- Client
game.ReplicatedStorage.MyRemoteEvent:FireServer({score=50, coins=10})

-- Server
game.ReplicatedStorage.MyRemoteEvent.OnServerEvent:Connect(function(player, data)
  print("Score:", data.score, "Coins:", data.coins)
end)</code></pre></div>

  <div class="example"><strong>Example 9: Security—Validating Data</strong>
<pre><code>-- Server
game.ReplicatedStorage.MyRemoteEvent.OnServerEvent:Connect(function(player, coins)
  if typeof(coins) == "number" and coins > 0 and coins < 1000 then
    print("Valid coins:", coins)
  else
    warn("Suspicious coins value from", player.Name)
  end
end)</code></pre></div>

  <div class="example"><strong>Example 10: RemoteEvent for GUI Actions</strong>
<pre><code>-- Client: Button click calls FireServer
button.MouseButton1Click:Connect(function()
  game.ReplicatedStorage.ButtonEvent:FireServer()
end)

-- Server
game.ReplicatedStorage.ButtonEvent.OnServerEvent:Connect(function(player)
  print(player.Name .. " clicked the button!")
end)</code></pre></div>

  <div class="example"><strong>Example 11: RemoteEvent—Multiple Arguments</strong>
<pre><code>game.ReplicatedStorage.MyRemoteEvent:FireServer("BuyItem", "Sword", 100)</code></pre></div>

  <div class="example"><strong>Example 12: BindableEvent for Modular Scripts</strong>
<pre><code>-- Module A fires BindableEvent
game.ReplicatedStorage.MyBindableEvent:Fire("Hello from Module A")

-- Module B listens and reacts
game.ReplicatedStorage.MyBindableEvent.Event:Connect(function(msg)
  print("Received:", msg)
end)</code></pre></div>

  <div class="example"><strong>Example 13: RemoteFunction—Returning Table</strong>
<pre><code>-- Server
game.ReplicatedStorage.GetStats.OnServerInvoke = function(player)
  return {score=100, rank="Gold"}
end

-- Client
local stats = game.ReplicatedStorage.GetStats:InvokeServer()
print(stats.score, stats.rank)</code></pre></div>

  <div class="example"><strong>Example 14: Disconnecting RemoteEvent Listeners</strong>
<pre><code>local conn = game.ReplicatedStorage.MyRemoteEvent.OnServerEvent:Connect(function(player)
  print("Fired!")
  conn:Disconnect()
end)</code></pre></div>

  <div class="example"><strong>Example 15: RemoteEvent for Sound Effects</strong>
<pre><code>-- Server
game.ReplicatedStorage.PlaySound:FireAllClients("rbxassetid://123456")

-- Client
game.ReplicatedStorage.PlaySound.OnClientEvent:Connect(function(soundId)
  local sound = Instance.new("Sound", workspace)
  sound.SoundId = soundId
  sound:Play()
end)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Make a RemoteEvent that awards points when a client triggers it.<br>
    2. Use a RemoteFunction to get a player’s current stats from the server.<br>
    3. Create a BindableEvent that triggers a message between two local scripts.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always check and validate remote data on the server for security!</div>
  <div class="warning">Never trust client data for critical game logic—always confirm and sanitize.</div>
  <div class="tip">Use Bindables for intra-server or intra-client communication, not for crossing boundaries.</div>
  <div class="tip">RemoteFunctions must return a value—don’t forget!</div>
  <div class="warning">Don’t spam remotes; excessive usage can cause lag or be exploited.</div>
</section><section id="guis">
  <h2>GUIs: Making Interactive Interfaces (ScreenGui, Frame, TextLabel, TextButton, ImageLabel, ImageButton)</h2>
  <blockquote>
    GUIs (Graphical User Interfaces) let you create buttons, menus, labels, and more—everything your players see and click! Mastering GUIs is essential for interactive games, shops, inventories, popups, and user feedback.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. ScreenGui Container</strong><br>
    ScreenGui is the root object for all UI elements. Place it in a player’s <code>PlayerGui</code> folder to display GUIs on their screen.
  </div>
  <div class="deepdive">
    <strong>2. Frames</strong><br>
    Frames are rectangular containers for other GUI elements. Use them for panels, windows, backgrounds, or to group controls together.
  </div>
  <div class="deepdive">
    <strong>3. TextLabel & TextButton</strong><br>
    TextLabels display static or dynamic text. TextButtons are clickable and run code when pressed—great for menus, confirmations, or actions.
  </div>
  <div class="deepdive">
    <strong>4. ImageLabel & ImageButton</strong><br>
    ImageLabels show images (icons, sprites, avatars). ImageButtons do the same, but can be clicked for actions.
  </div>
  <div class="deepdive">
    <strong>5. Scripting & Styling GUIs</strong><br>
    You can change GUIs with scripts: update text, move frames, change colors, show/hide elements, and connect events for interactivity. Use properties like <code>Position</code>, <code>Size</code>, <code>Visible</code>, <code>BackgroundColor3</code>, <code>TextColor3</code>.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">ScreenGui is the "TV screen" for your player’s interface.</div>
  <div class="simple">Frames are boxes you can fill with text, images, or buttons.</div>
  <div class="simple">Buttons let players click to do things—labels show info, images make it look cool.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Create a ScreenGui</strong>
<pre><code>local gui = Instance.new("ScreenGui")
gui.Parent = game.Players.LocalPlayer.PlayerGui</code></pre></div>

  <div class="example"><strong>Example 2: Add a Frame</strong>
<pre><code>local frame = Instance.new("Frame")
frame.Size = UDim2.new(0.5, 0, 0.5, 0)
frame.Position = UDim2.new(0.25, 0, 0.25, 0)
frame.BackgroundColor3 = Color3.fromRGB(60, 60, 200)
frame.Parent = gui</code></pre></div>

  <div class="example"><strong>Example 3: Add a TextLabel</strong>
<pre><code>local label = Instance.new("TextLabel")
label.Text = "Welcome!"
label.Size = UDim2.new(1, 0, 0.2, 0)
label.Position = UDim2.new(0, 0, 0, 0)
label.TextColor3 = Color3.new(1, 1, 1)
label.Parent = frame</code></pre></div>

  <div class="example"><strong>Example 4: Add a TextButton</strong>
<pre><code>local button = Instance.new("TextButton")
button.Text = "Play"
button.Size = UDim2.new(0.5, 0, 0.2, 0)
button.Position = UDim2.new(0.25, 0, 0.7, 0)
button.BackgroundColor3 = Color3.fromRGB(40, 200, 40)
button.Parent = frame
button.MouseButton1Click:Connect(function()
  print("Button clicked!")
end)</code></pre></div>

  <div class="example"><strong>Example 5: Add an ImageLabel</strong>
<pre><code>local img = Instance.new("ImageLabel")
img.Image = "rbxassetid://123456789"
img.Size = UDim2.new(0.3, 0, 0.3, 0)
img.Position = UDim2.new(0.35, 0, 0.35, 0)
img.Parent = frame</code></pre></div>

  <div class="example"><strong>Example 6: Add an ImageButton</strong>
<pre><code>local imgBtn = Instance.new("ImageButton")
imgBtn.Image = "rbxassetid://987654321"
imgBtn.Size = UDim2.new(0.2, 0, 0.2, 0)
imgBtn.Position = UDim2.new(0.7, 0, 0.1, 0)
imgBtn.Parent = frame
imgBtn.MouseButton1Click:Connect(function()
  print("Image button clicked!")
end)</code></pre></div>

  <div class="example"><strong>Example 7: Dynamically Update Text</strong>
<pre><code>label.Text = "Score: " .. tostring(100)</code></pre></div>

  <div class="example"><strong>Example 8: Show/Hide Frame</strong>
<pre><code>frame.Visible = false -- Hide
wait(2)
frame.Visible = true -- Show</code></pre></div>

  <div class="example"><strong>Example 9: Change Button Color on Click</strong>
<pre><code>button.MouseButton1Click:Connect(function()
  button.BackgroundColor3 = Color3.fromRGB(200, 40, 40)
end)</code></pre></div>

  <div class="example"><strong>Example 10: Resize GUI Element</strong>
<pre><code>frame.Size = UDim2.new(0.7, 0, 0.3, 0)</code></pre></div>

  <div class="example"><strong>Example 11: Move GUI Element</strong>
<pre><code>frame.Position = UDim2.new(0.1, 0, 0.1, 0)</code></pre></div>

  <div class="example"><strong>Example 12: Add Multiple Buttons in Loop</strong>
<pre><code>for i = 1, 3 do
  local btn = Instance.new("TextButton")
  btn.Text = "Option " .. i
  btn.Size = UDim2.new(0.3, 0, 0.1, 0)
  btn.Position = UDim2.new(0.1, 0, 0.1 * i, 0)
  btn.Parent = frame
end</code></pre></div>

  <div class="example"><strong>Example 13: Detect Which Button Was Clicked</strong>
<pre><code>button.MouseButton1Click:Connect(function()
  print("You clicked:", button.Text)
end)</code></pre></div>

  <div class="example"><strong>Example 14: Animate GUI Element</strong>
<pre><code>for i = 1, 10 do
  frame.Position = UDim2.new(0.25 + i*0.05, 0, 0.25, 0)
  wait(0.05)
end</code></pre></div>

  <div class="example"><strong>Example 15: Responsive Layout</strong>
<pre><code>frame.Size = UDim2.new(0.5, 0, 0, 100) -- Half screen width, 100px tall
frame.AnchorPoint = Vector2.new(0.5, 0.5)
frame.Position = UDim2.new(0.5, 0, 0.5, 0)</code></pre></div>

  <div class="example"><strong>Example 16: Change Label Font & Size</strong>
<pre><code>label.Font = Enum.Font.GothamBold
label.TextSize = 32</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Make a menu with three buttons—Play, Shop, and Quit—that print their name when clicked.<br>
    2. Add a TextLabel that updates with the player’s score.<br>
    3. Show a Frame only when the player presses a key (use <code>UserInputService</code>).
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always parent ScreenGui to <code>PlayerGui</code> for local GUIs.</div>
  <div class="tip">Use UDim2 for flexible sizing and positioning—works on all screen sizes!</div>
  <div class="tip">Connect <code>MouseButton1Click</code> for button actions.</div>
  <div class="tip">Use <code>Visible</code> to show/hide panels, menus, popups.</div>
  <div class="warning">Don’t parent GUIs to <code>StarterGui</code> during runtime—use <code>PlayerGui</code>!</div>
</section><section id="userinputservice">
  <h2>UserInputService: Detecting Keyboard, Mouse, Touch, and Gamepad Input</h2>
  <blockquote>
    UserInputService lets your game react to player input—keyboard, mouse, touchscreen, and gamepad. This is essential for custom controls, shortcuts, keybinds, mobile support, and more interactive experiences!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is UserInputService?</strong><br>
    UserInputService is a Roblox service that detects player input from all devices. You can listen for key presses, mouse clicks, touch events, and gamepad actions.
  </div>
  <div class="deepdive">
    <strong>2. Input Types & UserInputType</strong><br>
    Every input event includes a <code>UserInputType</code> (Keyboard, MouseButton1, Touch, Gamepad1, etc.) so you can customize responses for different devices.
  </div>
  <div class="deepdive">
    <strong>3. KeyCode & InputObject</strong><br>
    Keyboard and gamepad inputs include a <code>KeyCode</code> (like <code>Enum.KeyCode.Space</code>). The <code>InputObject</code> includes all relevant info for the input event.
  </div>
  <div class="deepdive">
    <strong>4. Events: InputBegan, InputEnded, InputChanged</strong><br>
    <code>InputBegan</code> fires when input starts, <code>InputEnded</code> when it stops, <code>InputChanged</code> for things like mouse movement or touch drag.
  </div>
  <div class="deepdive">
    <strong>5. Mobile & Gamepad Support</strong><br>
    UserInputService lets you detect if a player is on a mobile device or using a gamepad, so you can adapt controls and UI.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">UserInputService listens for player actions—press keys, click, tap, or use a controller.</div>
  <div class="simple">Check <code>UserInputType</code> to know what device or button was used.</div>
  <div class="simple">Use <code>InputBegan</code> and <code>InputEnded</code> to run code when input starts or stops.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Detect Keyboard Input</strong>
<pre><code>local UIS = game:GetService("UserInputService")
UIS.InputBegan:Connect(function(input, gameProcessed)
  if input.UserInputType == Enum.UserInputType.Keyboard then
    print("Key pressed:", input.KeyCode)
  end
end)</code></pre></div>

  <div class="example"><strong>Example 2: Detect Mouse Click</strong>
<pre><code>UIS.InputBegan:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.MouseButton1 then
    print("Mouse left click!")
  end
end)</code></pre></div>

  <div class="example"><strong>Example 3: Detect Touch Tap</strong>
<pre><code>UIS.InputBegan:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.Touch then
    print("Screen tapped!")
  end
end)</code></pre></div>

  <div class="example"><strong>Example 4: Detect Gamepad Button</strong>
<pre><code>UIS.InputBegan:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.Gamepad1 then
    print("Gamepad button pressed:", input.KeyCode)
  end
end)</code></pre></div>

  <div class="example"><strong>Example 5: KeyCode for Specific Key</strong>
<pre><code>UIS.InputBegan:Connect(function(input)
  if input.KeyCode == Enum.KeyCode.Space then
    print("Spacebar pressed!")
  end
end)</code></pre></div>

  <div class="example"><strong>Example 6: InputEnded Event</strong>
<pre><code>UIS.InputEnded:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.Keyboard then
    print("Key released:", input.KeyCode)
  end
end)</code></pre></div>

  <div class="example"><strong>Example 7: InputChanged for Mouse Movement</strong>
<pre><code>UIS.InputChanged:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.MouseMovement then
    print("Mouse moved!")
  end
end)</code></pre></div>

  <div class="example"><strong>Example 8: Prevent GameProcessed Input</strong>
<pre><code>UIS.InputBegan:Connect(function(input, gameProcessed)
  if gameProcessed then return end
  print("Raw input detected!")
end)</code></pre></div>

  <div class="example"><strong>Example 9: Detect Mobile vs. Desktop</strong>
<pre><code>if UIS.TouchEnabled then
  print("Player is on mobile!")
elseif UIS.KeyboardEnabled then
  print("Player is on desktop!")
end</code></pre></div>

  <div class="example"><strong>Example 10: Detect Gamepad</strong>
<pre><code>if UIS.GamepadEnabled then
  print("Player using gamepad!")
end</code></pre></div>

  <div class="example"><strong>Example 11: Custom Keybinds</strong>
<pre><code>local keybinds = {Jump = Enum.KeyCode.Space, Fire = Enum.KeyCode.F}
UIS.InputBegan:Connect(function(input)
  if input.KeyCode == keybinds.Jump then print("Jump!") end
  if input.KeyCode == keybinds.Fire then print("Fire!") end
end)</code></pre></div>

  <div class="example"><strong>Example 12: Dragging with InputChanged</strong>
<pre><code>local isDragging = false
UIS.InputBegan:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.MouseButton1 then
    isDragging = true
  end
end)
UIS.InputEnded:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.MouseButton1 then
    isDragging = false
  end
end)
UIS.InputChanged:Connect(function(input)
  if isDragging and input.UserInputType == Enum.UserInputType.MouseMovement then
    print("Dragging...")
  end
end)</code></pre></div>

  <div class="example"><strong>Example 13: Touch Swipe Detection</strong>
<pre><code>UIS.TouchMoved:Connect(function(input)
  print("Finger moved to:", input.Position)
end)</code></pre></div>

  <div class="example"><strong>Example 14: Key Combination (Shift+F)</strong>
<pre><code>UIS.InputBegan:Connect(function(input)
  if UIS:IsKeyDown(Enum.KeyCode.LeftShift) and input.KeyCode == Enum.KeyCode.F then
    print("Shift+F pressed!")
  end
end)</code></pre></div>

  <div class="example"><strong>Example 15: Gamepad Thumbstick Movement</strong>
<pre><code>UIS.InputChanged:Connect(function(input)
  if input.UserInputType == Enum.UserInputType.Gamepad1 and input.KeyCode == Enum.KeyCode.Thumbstick1 then
    print("Thumbstick moved:", input.Position)
  end
end)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Make a script that prints "Jump!" when Spacebar is pressed, and "Fire!" when F is pressed.<br>
    2. Detect and print whether the player is using a keyboard, mouse, touch, or gamepad.<br>
    3. Make a draggable Frame that follows the mouse or finger movement.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always check <code>gameProcessed</code> to avoid interfering with default controls.</div>
  <div class="tip">Use <code>UserInputType</code> and <code>KeyCode</code> for precise input handling.</div>
  <div class="tip">Support mobile and gamepad as well as desktop for best accessibility!</div>
  <div class="warning">Don’t block essential controls (like ESC or chat); always respect Roblox defaults.</div>
  <div class="tip">Listen for <code>InputChanged</code> for dragging, swiping, or analog stick input.</div>
</section><section id="tweenservice">
  <h2>TweenService: Animating Properties, Transitions, and Effects</h2>
  <blockquote>
    TweenService is Roblox’s built-in way to smoothly animate properties—move, resize, fade, color, rotate, and more. Mastering TweenService lets you add polish, feedback, and excitement to your games!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is TweenService?</strong><br>
    TweenService lets you animate properties of objects (parts, GUIs, models, lights, etc.) over time with smooth transitions.
  </div>
  <div class="deepdive">
    <strong>2. Tween Creation</strong><br>
    To create a tween, call <code>TweenService:Create()</code> with the target object, tween info (duration, style, direction), and the goal properties.
  </div>
  <div class="deepdive">
    <strong>3. TweenInfo</strong><br>
    TweenInfo sets duration, easing style (<code>Enum.EasingStyle</code>), direction (<code>Enum.EasingDirection</code>), repeat count, reverses, and delay.
  </div>
  <div class="deepdive">
    <strong>4. Playing & Controlling Tweens</strong><br>
    Use <code>:Play()</code> to start a tween, <code>:Pause()</code> to stop, <code>:Cancel()</code> to end instantly, and <code>.Completed</code> to run code after it finishes.
  </div>
  <div class="deepdive">
    <strong>5. Tweening Multiple Properties</strong><br>
    You can tween several properties at once—position, color, transparency, size, rotation, and more.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">TweenService lets things move, fade, or change smoothly instead of suddenly.</div>
  <div class="simple">You set a goal (like new position or color), then TweenService animates to it.</div>
  <div class="simple">Tweens can be paused, cancelled, and restarted—and you can run code after they're done!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Tween a Part’s Position</strong>
<pre><code>local TweenService = game:GetService("TweenService")
local part = workspace.Part
local goal = {Position = Vector3.new(10, 5, 0)}
local info = TweenInfo.new(2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out)
local tween = TweenService:Create(part, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 2: Tween a GUI’s Transparency</strong>
<pre><code>local frame = script.Parent
local goal = {BackgroundTransparency = 1}
local info = TweenInfo.new(1)
local tween = TweenService:Create(frame, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 3: Tween a Part’s Color</strong>
<pre><code>local goal = {Color = Color3.fromRGB(255, 0, 0)}
local info = TweenInfo.new(0.5)
local tween = TweenService:Create(part, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 4: Tween GUI Size</strong>
<pre><code>local goal = {Size = UDim2.new(1,0,1,0)}
local info = TweenInfo.new(0.7, Enum.EasingStyle.Back, Enum.EasingDirection.Out)
local tween = TweenService:Create(frame, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 5: Tween Rotation</strong>
<pre><code>local goal = {Orientation = Vector3.new(0, 180, 0)}
local info = TweenInfo.new(1, Enum.EasingStyle.Linear)
local tween = TweenService:Create(part, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 6: Tween Multiple Properties</strong>
<pre><code>local goal = {Position = Vector3.new(0,5,0), Transparency = 0.5, Color = Color3.new(1,0,0)}
local info = TweenInfo.new(2)
local tween = TweenService:Create(part, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 7: Play, Pause, Cancel Tween</strong>
<pre><code>tween:Play()
wait(0.5)
tween:Pause()
wait(0.5)
tween:Play()
wait(0.2)
tween:Cancel()</code></pre></div>

  <div class="example"><strong>Example 8: Tween Completed Event</strong>
<pre><code>tween.Completed:Connect(function()
  print("Tween finished!")
end)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 9: Tween Looping & Reversing</strong>
<pre><code>local info = TweenInfo.new(1, Enum.EasingStyle.Bounce, Enum.EasingDirection.Out, 3, true, 0.2)
local tween = TweenService:Create(part, info, {Transparency = 1})
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 10: Tween Delay</strong>
<pre><code>local info = TweenInfo.new(1, Enum.EasingStyle.Sine, Enum.EasingDirection.Out, 0, false, 2)
local tween = TweenService:Create(part, info, {Color = Color3.new(0,1,0)})
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 11: Tween GUI Color</strong>
<pre><code>local goal = {BackgroundColor3 = Color3.fromRGB(0, 255, 0)}
local info = TweenInfo.new(1)
local tween = TweenService:Create(frame, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 12: Tween Model’s PrimaryPart</strong>
<pre><code>local model = workspace.Model
local part = model.PrimaryPart
local goal = {Position = Vector3.new(10,10,10)}
local info = TweenInfo.new(1)
local tween = TweenService:Create(part, info, goal)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 13: TweenService in a Function</strong>
<pre><code>function fadeOut(part)
  local goal = {Transparency = 1}
  local info = TweenInfo.new(0.5)
  local tween = TweenService:Create(part, info, goal)
  tween:Play()
end
fadeOut(workspace.Part)</code></pre></div>

  <div class="example"><strong>Example 14: Tween GUI Out, Then Remove</strong>
<pre><code>local goal = {BackgroundTransparency = 1}
local info = TweenInfo.new(1)
local tween = TweenService:Create(frame, info, goal)
tween.Completed:Connect(function()
  frame:Destroy()
end)
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 15: TweenService for Effects</strong>
<pre><code>function flash(part)
  local goal = {Color = Color3.new(1,1,0)}
  local info = TweenInfo.new(0.2)
  local tween = TweenService:Create(part, info, goal)
  tween:Play()
end
flash(workspace.Part)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Tween a part’s color from red to green in 2 seconds.<br>
    2. Animate a GUI button growing larger and fading out.<br>
    3. Make a part bounce up and down repeatedly using TweenInfo loops.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">TweenService works on almost any property—Position, Size, Color, Transparency, Orientation, etc.</div>
  <div class="tip">Use <code>TweenInfo</code> for control over speed, style, direction, repeats, reverses, and delays.</div>
  <div class="warning">Don’t tween properties that aren’t supported—check docs for what you can animate!</div>
  <div class="tip">Connect to <code>.Completed</code> to chain tweens or run code after animation ends.</div>
  <div class="warning">Tweens don’t affect physics—parts will move visually, but collisions may not update until finished.</div>
</section><section id="physics">
  <h2>Physics: BodyMovers, Constraints, Collisions, and Touch Events</h2>
  <blockquote>
    Roblox physics make your world interactive and dynamic—objects move, fall, collide, and respond to forces! BodyMovers and Constraints power vehicles, puzzles, traps, and more. Mastering physics lets you build immersive, realistic games.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. BodyMovers (Legacy)</strong><br>
    BodyMovers like <code>BodyPosition</code>, <code>BodyVelocity</code>, and <code>BodyGyro</code> apply forces to parts, letting you move, spin, or hover objects. They’re being replaced by Constraints but are still useful for simple effects.
  </div>
  <div class="deepdive">
    <strong>2. Constraints (Modern)</strong><br>
    Constraints are the new way to connect, move, and control physics objects: <code>HingeConstraint</code>, <code>SpringConstraint</code>, <code>RodConstraint</code>, <code>PrismaticConstraint</code>, etc. They let you build doors, vehicles, ropes, rotating platforms, and more.
  </div>
  <div class="deepdive">
    <strong>3. Collisions</strong><br>
    Collisions happen when parts touch or overlap. You can control collisions using properties like <code>CanCollide</code>, <code>CollisionGroup</code>, and <code>Anchored</code>. Use collision groups for advanced behaviors (e.g., players walk through ghosts).
  </div>
  <div class="deepdive">
    <strong>4. Touch Events</strong><br>
    The <code>Touched</code> event fires whenever a part comes into contact with another part. Use this for triggers, pickups, damage zones, and interactive objects.
  </div>
  <div class="deepdive">
    <strong>5. Physics Properties</strong><br>
    Every part has properties like <code>Mass</code>, <code>Velocity</code>, <code>RotVelocity</code>, <code>Friction</code>, <code>Elasticity</code>, and <code>CustomPhysicalProperties</code>. Tuning these lets you create ice, rubber, sticky, or bouncy surfaces.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Physics makes objects move, fall, bounce, and collide just like in the real world.</div>
  <div class="simple">BodyMovers and Constraints let you push, pull, spin, or link parts together.</div>
  <div class="simple">Touch events let you run code when things bump into each other.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: BodyVelocity to Push a Part</strong>
<pre><code>local bv = Instance.new("BodyVelocity")
bv.Velocity = Vector3.new(0,50,0)
bv.Parent = workspace.Part</code></pre></div>

  <div class="example"><strong>Example 2: BodyPosition for Floating Object</strong>
<pre><code>local bp = Instance.new("BodyPosition")
bp.Position = Vector3.new(0,20,0)
bp.Parent = workspace.Part</code></pre></div>

  <div class="example"><strong>Example 3: BodyGyro for Rotation</strong>
<pre><code>local bg = Instance.new("BodyGyro")
bg.CFrame = CFrame.Angles(0, math.rad(90), 0)
bg.Parent = workspace.Part</code></pre></div>

  <div class="example"><strong>Example 4: HingeConstraint for a Door</strong>
<pre><code>local hinge = Instance.new("HingeConstraint")
hinge.Parent = workspace.Door
hinge.Attachment0 = workspace.Door.HingeAttachment
hinge.Attachment1 = workspace.DoorFrame.HingeAttachment</code></pre></div>

  <div class="example"><strong>Example 5: SpringConstraint for Bouncy Platform</strong>
<pre><code>local spring = Instance.new("SpringConstraint")
spring.Parent = workspace.Platform
spring.Attachment0 = workspace.Platform.SpringAttachment
spring.Attachment1 = workspace.Base.SpringAttachment
spring.Stiffness = 100
spring.Damping = 20</code></pre></div>

  <div class="example"><strong>Example 6: Collision Groups</strong>
<pre><code>local PhysicsService = game:GetService("PhysicsService")
PhysicsService:CreateCollisionGroup("Ghosts")
PhysicsService:SetPartCollisionGroup(workspace.Ghost, "Ghosts")
PhysicsService:CollisionGroupSetCollidable("Ghosts", "Players", false)</code></pre></div>

  <div class="example"><strong>Example 7: Disable Collisions on Part</strong>
<pre><code>workspace.Part.CanCollide = false</code></pre></div>

  <div class="example"><strong>Example 8: Anchored Part (No Physics)</strong>
<pre><code>workspace.Part.Anchored = true</code></pre></div>

  <div class="example"><strong>Example 9: Touched Event for Pickup</strong>
<pre><code>workspace.Coin.Touched:Connect(function(hit)
  print(hit.Name .. " touched the coin!")
  workspace.Coin:Destroy()
end)</code></pre></div>

  <div class="example"><strong>Example 10: Touched Event—Damage Zone</strong>
<pre><code>workspace.Lava.Touched:Connect(function(hit)
  local human = hit.Parent:FindFirstChild("Humanoid")
  if human then
    human.Health = human.Health - 20
  end
end)</code></pre></div>

  <div class="example"><strong>Example 11: CustomPhysicalProperties</strong>
<pre><code>local props = PhysicalProperties.new(1, 0.2, 0.5)
workspace.Ice.CustomPhysicalProperties = props</code></pre></div>

  <div class="example"><strong>Example 12: Velocity for Launch</strong>
<pre><code>workspace.Ball.Velocity = Vector3.new(50, 100, 0)</code></pre></div>

  <div class="example"><strong>Example 13: Detecting Collision with Debounce</strong>
<pre><code>local debounce = false
workspace.PowerUp.Touched:Connect(function(hit)
  if not debounce then
    debounce = true
    print("PowerUp collected!")
    wait(1)
    debounce = false
  end
end)</code></pre></div>

  <div class="example"><strong>Example 14: RopeConstraint for Swinging</strong>
<pre><code>local rope = Instance.new("RopeConstraint")
rope.Parent = workspace.Swing
rope.Attachment0 = workspace.Swing.AttachmentA
rope.Attachment1 = workspace.Swing.AttachmentB
rope.Length = 15</code></pre></div>

  <div class="example"><strong>Example 15: PrismaticConstraint (Sliding Platform)</strong>
<pre><code>local prism = Instance.new("PrismaticConstraint")
prism.Parent = workspace.Platform
prism.Attachment0 = workspace.Platform.AttachmentA
prism.Attachment1 = workspace.Platform.AttachmentB
prism.LimitsEnabled = true
prism.UpperLimit = 10
prism.LowerLimit = -10</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Build a script that launches a ball when a button is clicked (use BodyVelocity or Velocity).<br>
    2. Use a HingeConstraint to make a door that swings open when touched.<br>
    3. Create a pickup part that disappears and increases score when touched.<br>
    4. Set up a collision group that allows only specific objects to collide.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use Constraints for advanced physics behaviors—hinges, springs, ropes, sliders.</div>
  <div class="tip">BodyMovers are simple, but Constraints are more powerful and modern.</div>
  <div class="tip">Always debounce touch events to avoid running code too many times.</div>
  <div class="warning">Don’t forget to connect both attachments for Constraints!</div>
  <div class="tip">Use collision groups for team-based games, puzzles, or special interactions.</div>
  <div class="warning">Parts with <code>Anchored = true</code> won’t move or fall!</div>
</section><section id="roblox_services">
  <h2>Roblox Services: Workspace, Lighting, ReplicatedStorage, ServerStorage, StarterPack, StarterGui, StarterPlayer</h2>
  <blockquote>
    Roblox services are special containers and systems that organize your game’s objects, assets, scripts, and settings. Understanding each service lets you build efficient, secure, and interactive experiences!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. Workspace</strong><br>
    Workspace is where all physical parts, models, and moving objects live. Everything visible and interactive in the 3D world is a child of Workspace.
  </div>
  <div class="deepdive">
    <strong>2. Lighting</strong><br>
    Lighting controls the atmosphere, time of day, fog, bloom, sun rays, and other effects. Use it for day/night cycles, environmental effects, and mood.
  </div>
  <div class="deepdive">
    <strong>3. ReplicatedStorage</strong><br>
    ReplicatedStorage lets you store shared assets (modules, events, models) that both client and server scripts can access. Use it for items, remotes, and modules.
  </div>
  <div class="deepdive">
    <strong>4. ServerStorage</strong><br>
    ServerStorage is only accessible to server scripts. Store sensitive models, data, and scripts here that you don’t want clients to see or modify.
  </div>
  <div class="deepdive">
    <strong>5. StarterPack</strong><br>
    StarterPack holds tools and gear that are automatically given to players when they join the game. Place swords, guns, or gadgets here for automatic delivery.
  </div>
  <div class="deepdive">
    <strong>6. StarterGui</strong><br>
    StarterGui contains GUIs that are copied to each player’s PlayerGui when they join. Use it for menus, HUDs, and popups.
  </div>
  <div class="deepdive">
    <strong>7. StarterPlayer</strong><br>
    StarterPlayer holds scripts that run on each player’s character (StarterCharacterScripts) or client (StarterPlayerScripts). Use it for custom controls, camera, or character logic.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Workspace is the main play area—where all parts and players exist.</div>
  <div class="simple">Lighting sets the mood—day, night, fog, and effects.</div>
  <div class="simple">ReplicatedStorage shares stuff. ServerStorage hides stuff from players.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Accessing Workspace Parts</strong>
<pre><code>local part = workspace.Part
part.Position = Vector3.new(0, 10, 0)</code></pre></div>

  <div class="example"><strong>Example 2: Change Lighting Time of Day</strong>
<pre><code>game.Lighting.TimeOfDay = "18:00:00"</code></pre></div>

  <div class="example"><strong>Example 3: Store and Clone Model from ReplicatedStorage</strong>
<pre><code>local model = game.ReplicatedStorage.EnemyModel:Clone()
model.Parent = workspace</code></pre></div>

  <div class="example"><strong>Example 4: Hide Asset in ServerStorage</strong>
<pre><code>local secret = game.ServerStorage.SecretItem
-- Only server scripts can reach this!</code></pre></div>

  <div class="example"><strong>Example 5: Add Tool to StarterPack</strong>
<pre><code>local sword = Instance.new("Tool")
sword.Name = "Sword"
sword.Parent = game.StarterPack</code></pre></div>

  <div class="example"><strong>Example 6: StarterGui Menu Example</strong>
<pre><code>local menu = Instance.new("ScreenGui")
menu.Parent = game.StarterGui</code></pre></div>

  <div class="example"><strong>Example 7: Custom Character Script in StarterPlayer</strong>
<pre><code>local script = Instance.new("Script")
script.Source = 'print("Hello, character!")'
script.Parent = game.StarterPlayer.StarterCharacterScripts</code></pre></div>

  <div class="example"><strong>Example 8: Store RemoteEvent in ReplicatedStorage</strong>
<pre><code>local remote = Instance.new("RemoteEvent")
remote.Name = "MyEvent"
remote.Parent = game.ReplicatedStorage</code></pre></div>

  <div class="example"><strong>Example 9: Change Lighting Fog</strong>
<pre><code>game.Lighting.FogEnd = 100
game.Lighting.FogColor = Color3.fromRGB(200,200,255)</code></pre></div>

  <div class="example"><strong>Example 10: Clone Tool from ServerStorage to Player</strong>
<pre><code>local tool = game.ServerStorage.Wand:Clone()
tool.Parent = player.Backpack</code></pre></div>

  <div class="example"><strong>Example 11: StarterGui Button Click</strong>
<pre><code>local gui = game.StarterGui.Menu
local button = gui.Frame.PlayButton
button.MouseButton1Click:Connect(function()
  print("Play clicked!")
end)</code></pre></div>

  <div class="example"><strong>Example 12: ReplicatedStorage Module Usage</strong>
<pre><code>local mod = require(game.ReplicatedStorage.MyModule)
mod.doSomething()</code></pre></div>

  <div class="example"><strong>Example 13: StarterPlayerScripts for Custom Camera</strong>
<pre><code>local script = Instance.new("LocalScript")
script.Source = 'workspace.CurrentCamera.FieldOfView = 100'
script.Parent = game.StarterPlayer.StarterPlayerScripts</code></pre></div>

  <div class="example"><strong>Example 14: Give All Players a Tool from StarterPack</strong>
<pre><code>for _, player in pairs(game.Players:GetPlayers()) do
  local tool = game.StarterPack.Sword:Clone()
  tool.Parent = player.Backpack
end</code></pre></div>

  <div class="example"><strong>Example 15: Secure Asset (not visible to client)</strong>
<pre><code>-- Place valuable items or scripts in ServerStorage to prevent exploits
local asset = game.ServerStorage.ValuableData</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Clone a model from ReplicatedStorage and spawn it in Workspace when a button is clicked.<br>
    2. Store a secret tool in ServerStorage and give it to a player only after they finish a quest.<br>
    3. Make a GUI in StarterGui that displays the current time of day from Lighting.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use ReplicatedStorage for assets shared between client and server—never for sensitive data!</div>
  <div class="warning">Never store secret scripts, data, or assets in ReplicatedStorage—use ServerStorage!</div>
  <div class="tip">StarterPack auto-gives all tools to new players—great for default gear.</div>
  <div class="tip">GUIs in StarterGui are copied to PlayerGui; always script local GUIs in PlayerGui.</div>
  <div class="warning">StarterPlayerScripts and StarterCharacterScripts run on each player; use for controls, camera, and local logic.</div>
</section><section id="datastores">
  <h2>DataStores & Saving Data: Persistent Player Progress</h2>
  <blockquote>
    DataStores let you save and load data (coins, levels, stats, inventory) between play sessions. Mastering DataStores is essential for persistent games, leaderboards, shops, and player progression!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is a DataStore?</strong><br>
    DataStores are Roblox’s way to save and retrieve key-value data on the cloud. Data is persistent—players keep their stats even after leaving and rejoining.
  </div>
  <div class="deepdive">
    <strong>2. Get & Set Data</strong><br>
    Use <code>:GetAsync(key)</code> to read, <code>:SetAsync(key, value)</code> to write, and <code>:UpdateAsync(key, callback)</code> to update data safely.
  </div>
  <div class="deepdive">
    <strong>3. DataStore Limits & Errors</strong><br>
    DataStores have limits: request throttling, value sizes, and possible failures. Always use <code>pcall</code> to handle errors and avoid losing data.
  </div>
  <div class="deepdive">
    <strong>4. Player Data Patterns</strong><br>
    Commonly, use player.UserId as the key. Save stats when players leave, load when they join. Cache data in memory for speed, and only write to DataStore when needed.
  </div>
  <div class="deepdive">
    <strong>5. OrderedDataStores & Leaderboards</strong><br>
    OrderedDataStores let you sort data (like scores), perfect for leaderboards and rankings.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">DataStores save player info (coins, levels, etc.) so it’s there next time they play.</div>
  <div class="simple">Use GetAsync to load, SetAsync to save, and always check for errors!</div>
  <div class="simple">OrderedDataStores sort data for leaderboards, top scores, and ranking.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Get DataStore and Save Data</strong>
<pre><code>local DataStoreService = game:GetService("DataStoreService")
local coinsStore = DataStoreService:GetDataStore("Coins")
local success, err = pcall(function()
  coinsStore:SetAsync("Player_123", 50)
end)
if not success then print("Error saving:", err) end</code></pre></div>

  <div class="example"><strong>Example 2: Load Data</strong>
<pre><code>local coins
local success, err = pcall(function()
  coins = coinsStore:GetAsync("Player_123")
end)
if success then print("Coins:", coins) else print("Error:", err) end</code></pre></div>

  <div class="example"><strong>Example 3: Save Player Data on Leave</strong>
<pre><code>game.Players.PlayerRemoving:Connect(function(player)
  local key = "Player_" .. player.UserId
  local data = player.leaderstats.Coins.Value
  pcall(function()
    coinsStore:SetAsync(key, data)
  end)
end)</code></pre></div>

  <div class="example"><strong>Example 4: Load Player Data on Join</strong>
<pre><code>game.Players.PlayerAdded:Connect(function(player)
  local key = "Player_" .. player.UserId
  local coins = 0
  local success = pcall(function()
    coins = coinsStore:GetAsync(key) or 0
  end)
  local stats = Instance.new("Folder")
  stats.Name = "leaderstats"
  stats.Parent = player
  local coinVal = Instance.new("IntValue")
  coinVal.Name = "Coins"
  coinVal.Value = coins
  coinVal.Parent = stats
end)</code></pre></div>

  <div class="example"><strong>Example 5: UpdateAsync for Safe Updates</strong>
<pre><code>local function addCoins(player, amount)
  local key = "Player_" .. player.UserId
  pcall(function()
    coinsStore:UpdateAsync(key, function(old)
      return (old or 0) + amount
    end)
  end)
end</code></pre></div>

  <div class="example"><strong>Example 6: OrderedDataStore for Leaderboard</strong>
<pre><code>local scoreStore = DataStoreService:GetOrderedDataStore("Scores")
scoreStore:SetAsync("Player_123", 200)
-- Get top scores
local pages = scoreStore:GetSortedAsync(false, 10)
for _, data in ipairs(pages:GetCurrentPage()) do
  print(data.key, data.value)
end</code></pre></div>

  <div class="example"><strong>Example 7: pcall Error Handling</strong>
<pre><code>local success, result = pcall(function()
  return coinsStore:GetAsync(key)
end)
if not success then print("DataStore error:", result) end</code></pre></div>

  <div class="example"><strong>Example 8: DataStore Limits</strong>
<pre><code>-- DataStores limit requests per minute and size per value
-- Save only when needed, not every second!
</code></pre></div>

  <div class="example"><strong>Example 9: Table Data</strong>
<pre><code>local inventoryStore = DataStoreService:GetDataStore("Inventory")
local items = {"Sword", "Potion", "Shield"}
pcall(function()
  inventoryStore:SetAsync(key, items)
end)</code></pre></div>

  <div class="example"><strong>Example 10: Load Table Data</strong>
<pre><code>local items = {}
pcall(function()
  items = inventoryStore:GetAsync(key) or {}
end)
for _, item in ipairs(items) do
  print(item)
end</code></pre></div>

  <div class="example"><strong>Example 11: Cache Data in Memory</strong>
<pre><code>local cache = {}
game.Players.PlayerAdded:Connect(function(player)
  local key = "Player_" .. player.UserId
  local coins = coinsStore:GetAsync(key) or 0
  cache[key] = coins
end)
game.Players.PlayerRemoving:Connect(function(player)
  local key = "Player_" .. player.UserId
  coinsStore:SetAsync(key, cache[key])
end)</code></pre></div>

  <div class="example"><strong>Example 12: Retry on Failure</strong>
<pre><code>local function saveData(key, value)
  for i = 1, 3 do
    local success, err = pcall(function()
      coinsStore:SetAsync(key, value)
    end)
    if success then return true end
    wait(2)
  end
  print("Failed to save after retries!")
end</code></pre></div>

  <div class="example"><strong>Example 13: OnUpdate Leaderboard</strong>
<pre><code>scoreStore:UpdateAsync("Player_123", function(old)
  return math.max(old or 0, newScore)
end)</code></pre></div>

  <div class="example"><strong>Example 14: Player Key Pattern</strong>
<pre><code>local key = "Player_" .. player.UserId</code></pre></div>

  <div class="example"><strong>Example 15: Multi-Stat Data Table</strong>
<pre><code>local statsStore = DataStoreService:GetDataStore("Stats")
local stats = {coins = 100, level = 5, xp = 400}
statsStore:SetAsync(key, stats)
-- Load:
local loadedStats = statsStore:GetAsync(key) or {coins=0,level=1,xp=0}</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Save and load a player’s inventory using DataStore.<br>
    2. Make a leaderboard using OrderedDataStore that shows top 10 scores.<br>
    3. Use UpdateAsync to safely add coins and avoid overwriting other changes.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always use <code>pcall</code> for DataStore calls—never risk crashing your game!</div>
  <div class="warning">Don’t save too often; obey DataStore limits and cache values in memory.</div>
  <div class="tip">Use UpdateAsync for concurrent changes (multiple servers or scripts).</div>
  <div class="warning">Never trust client data—always validate and sanitize before saving!</div>
  <div class="tip">Use player.UserId as DataStore key, not player.Name (names can change).</div>
</section><section id="leaderboards-badges-gamepasses">
  <h2>Leaderboards, Badges, and GamePasses: Progression, Rewards, and Monetization</h2>
  <blockquote>
    Leaderboards track and display top players. Badges reward achievements. GamePasses enable special powers and monetization. Mastering these systems drives competition, engagement, and revenue!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. Leaderboards</strong><br>
    Use <code>OrderedDataStore</code> to sort and display scores, coins, wins, or any stat. Update when players achieve something, then show top players in GUIs or in-game.
  </div>
  <div class="deepdive">
    <strong>2. BadgeService</strong><br>
    Badges are special rewards for achievements. Use <code>BadgeService:AwardBadge()</code> to grant a badge by ID. Players see badges on their profile and in-game.
  </div>
  <div class="deepdive">
    <strong>3. GamePasses</strong><br>
    GamePasses are paid items that unlock features. Use <code>MarketplaceService:UserOwnsGamePassAsync()</code> to check ownership and <code>PromptGamePassPurchase()</code> to sell.
  </div>
  <div class="deepdive">
    <strong>4. GUI Display & Updating</strong><br>
    Display leaderboards in GUIs using <code>TextLabels</code> and tables. Update live or when players ask. Show badges and GamePasses in profile menus and shop screens.
  </div>
  <div class="deepdive">
    <strong>5. Security & Validation</strong><br>
    Always check server-side for badge and GamePass ownership. Never trust client data for rewards or purchases!
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Leaderboards show top players. Badges are rewards for cool achievements. GamePasses unlock special powers (for Robux).</div>
  <div class="simple">Award badges with BadgeService. Check GamePasses with MarketplaceService.</div>
  <div class="simple">Always check and update stats on the server for fairness and security.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Create Leaderboard with OrderedDataStore</strong>
<pre><code>local ds = game:GetService("DataStoreService"):GetOrderedDataStore("Scores")
ds:SetAsync("Player_123", 500)
local pages = ds:GetSortedAsync(false, 10)
for _, data in ipairs(pages:GetCurrentPage()) do
  print(data.key, data.value)
end</code></pre></div>

  <div class="example"><strong>Example 2: Award a Badge</strong>
<pre><code>local BadgeService = game:GetService("BadgeService")
local badgeId = 123456789
BadgeService:AwardBadge(player.UserId, badgeId)</code></pre></div>

  <div class="example"><strong>Example 3: Check if Player Owns Badge</strong>
<pre><code>local hasBadge = false
local success = pcall(function()
  hasBadge = BadgeService:UserHasBadgeAsync(player.UserId, badgeId)
end)
if hasBadge then print("Player already has badge!") end</code></pre></div>

  <div class="example"><strong>Example 4: Prompt GamePass Purchase</strong>
<pre><code>local MarketplaceService = game:GetService("MarketplaceService")
local gamePassId = 987654321
MarketplaceService:PromptGamePassPurchase(player, gamePassId)</code></pre></div>

  <div class="example"><strong>Example 5: Check if Player Owns GamePass</strong>
<pre><code>local owns = false
local success = pcall(function()
  owns = MarketplaceService:UserOwnsGamePassAsync(player.UserId, gamePassId)
end)
if owns then print("Player has the GamePass!") end</code></pre></div>

  <div class="example"><strong>Example 6: Leaderboard GUI Example</strong>
<pre><code>local gui = Instance.new("ScreenGui")
local frame = Instance.new("Frame")
frame.Parent = gui
for i, entry in ipairs(scores) do
  local label = Instance.new("TextLabel")
  label.Text = entry.name .. ": " .. entry.score
  label.Parent = frame
end
gui.Parent = player.PlayerGui</code></pre></div>

  <div class="example"><strong>Example 7: Award Badge When Level Up</strong>
<pre><code>if player.leaderstats.Level.Value >= 10 then
  BadgeService:AwardBadge(player.UserId, badgeId)
end</code></pre></div>

  <div class="example"><strong>Example 8: GamePass-Gated Ability</strong>
<pre><code>if MarketplaceService:UserOwnsGamePassAsync(player.UserId, gamePassId) then
  -- Unlock special ability
end</code></pre></div>

  <div class="example"><strong>Example 9: Secure Badge Award (pcall)</strong>
<pre><code>local success, err = pcall(function()
  BadgeService:AwardBadge(player.UserId, badgeId)
end)
if not success then print("Error awarding badge:", err) end</code></pre></div>

  <div class="example"><strong>Example 10: Update Leaderboard on Score Change</strong>
<pre><code>player.leaderstats.Score.Changed:Connect(function(newScore)
  ds:SetAsync("Player_" .. player.UserId, newScore)
end)</code></pre></div>

  <div class="example"><strong>Example 11: Display Badges in GUI</strong>
<pre><code>for _, badgeId in ipairs(player.Badges) do
  local icon = Instance.new("ImageLabel")
  icon.Image = "rbxassetid://" .. badgeId
  icon.Parent = gui.Frame
end</code></pre></div>

  <div class="example"><strong>Example 12: Leaderboard Paging</strong>
<pre><code>local nextPage = pages:GetNextPageAsync()
for _, data in ipairs(nextPage) do
  print(data.key, data.value)
end</code></pre></div>

  <div class="example"><strong>Example 13: Only Award Badge Once</strong>
<pre><code>if not BadgeService:UserHasBadgeAsync(player.UserId, badgeId) then
  BadgeService:AwardBadge(player.UserId, badgeId)
end</code></pre></div>

  <div class="example"><strong>Example 14: GamePass Shop GUI</strong>
<pre><code>local btn = Instance.new("TextButton")
btn.Text = "Buy VIP"
btn.MouseButton1Click:Connect(function()
  MarketplaceService:PromptGamePassPurchase(player, vipGamePassId)
end)</code></pre></div>

  <div class="example"><strong>Example 15: Remove Player from Leaderboard</strong>
<pre><code>ds:RemoveAsync("Player_" .. player.UserId)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Create a leaderboard that updates when a player earns coins.<br>
    2. Award a badge for reaching a high score.<br>
    3. Check if a player owns a GamePass before letting them use a special tool.<br>
    4. Display top 10 scores in a GUI.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always use <code>pcall</code> when awarding badges or checking GamePasses.</div>
  <div class="warning">Never trust client data for leaderboards, badges, or GamePasses—validate on the server.</div>
  <div class="tip">Use OrderedDataStore for sorting and paging leaderboards.</div>
  <div class="tip">Display badge icons and GamePasses in GUIs for engagement and sales.</div>
  <div class="warning">Don’t award badges more than once—always check ownership first.</div>
</section><section id="animation">
  <h2>Animation: AnimationController, Animator, and Custom Animations</h2>
  <blockquote>
    Animations bring characters, NPCs, and objects to life. Roblox uses Animation objects, AnimationController, and Animator to play, blend, and control custom movements and poses. Mastering animation is essential for making immersive, expressive games!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. Animation Objects</strong><br>
    Animation objects store the asset ID of a custom animation created in Roblox Studio or uploaded online. You reference these in scripts to play them.
  </div>
  <div class="deepdive">
    <strong>2. AnimationController vs. Animator</strong><br>
    AnimationController is used for non-Humanoid models (like animals, doors, machines). Animator is used in Humanoids (players, NPCs). Both load and play animations.
  </div>
  <div class="deepdive">
    <strong>3. Loading and Playing Animations</strong><br>
    Use <code>Animator:LoadAnimation()</code> to prepare an animation, then <code>:Play()</code> to start it. You can pause, stop, resume, or adjust speed.
  </div>
  <div class="deepdive">
    <strong>4. Animation Events & Blending</strong><br>
    Animations can trigger events with <code>GetMarkerReachedSignal</code>. You can blend animations, set priority (Idle, Movement, Action), and adjust looping.
  </div>
  <div class="deepdive">
    <strong>5. Custom Animation Creation & Upload</strong><br>
    Create animations in Roblox Studio’s Animation Editor, then publish to get an asset ID. Use this ID in your scripts and Animation objects.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Animations are like movies for your characters—walk, jump, dance, celebrate!</div>
  <div class="simple">Animator is for players/NPCs, AnimationController is for non-humanoid models.</div>
  <div class="simple">Load animations with asset IDs, play them with scripts, and control speed, looping, and blending.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Play Animation on Humanoid</strong>
<pre><code>local humanoid = workspace.Character.Humanoid
local anim = Instance.new("Animation")
anim.AnimationId = "rbxassetid://123456789"
local track = humanoid:LoadAnimation(anim)
track:Play()</code></pre></div>

  <div class="example"><strong>Example 2: Play Animation on Non-Humanoid Model</strong>
<pre><code>local controller = Instance.new("AnimationController")
controller.Parent = workspace.Dog
local animator = Instance.new("Animator")
animator.Parent = controller
local anim = Instance.new("Animation")
anim.AnimationId = "rbxassetid://987654321"
local track = animator:LoadAnimation(anim)
track:Play()</code></pre></div>

  <div class="example"><strong>Example 3: Play Animation with Animator</strong>
<pre><code>local animator = workspace.Character.Humanoid.Animator
local anim = Instance.new("Animation")
anim.AnimationId = "rbxassetid://246810121"
local track = animator:LoadAnimation(anim)
track:Play()</code></pre></div>

  <div class="example"><strong>Example 4: Stop Animation</strong>
<pre><code>track:Stop()</code></pre></div>

  <div class="example"><strong>Example 5: Set Animation Speed</strong>
<pre><code>track:AdjustSpeed(2) -- Double speed
track:AdjustSpeed(0.5) -- Half speed</code></pre></div>

  <div class="example"><strong>Example 6: Loop Animations</strong>
<pre><code>track.Looped = true
track:Play()</code></pre></div>

  <div class="example"><strong>Example 7: Animation Priority</strong>
<pre><code>track.Priority = Enum.AnimationPriority.Action -- Overrides lower-priority animations</code></pre></div>

  <div class="example"><strong>Example 8: Detect Animation Events</strong>
<pre><code>track:GetMarkerReachedSignal("Jump"):Connect(function()
  print("Jump event reached!")
end)</code></pre></div>

  <div class="example"><strong>Example 9: Blend Multiple Animations</strong>
<pre><code>local walkAnim = animator:LoadAnimation(walk)
local idleAnim = animator:LoadAnimation(idle)
idleAnim:Play()
walkAnim:Play()
walkAnim:AdjustWeight(0.5) -- Blend with idle</code></pre></div>

  <div class="example"><strong>Example 10: Pause/Resume Animation</strong>
<pre><code>track:AdjustSpeed(0) -- Pause
track:AdjustSpeed(1) -- Resume</code></pre></div>

  <div class="example"><strong>Example 11: Play Animation on All Players</strong>
<pre><code>for _, player in pairs(game.Players:GetPlayers()) do
  local humanoid = player.Character and player.Character:FindFirstChild("Humanoid")
  if humanoid then
    local anim = Instance.new("Animation")
    anim.AnimationId = "rbxassetid://123456789"
    local track = humanoid:LoadAnimation(anim)
    track:Play()
  end
end</code></pre></div>

  <div class="example"><strong>Example 12: Create and Upload Animation</strong>
<pre><code>-- Use the Animation Editor in Roblox Studio
-- Export and copy the asset ID for use in scripts
</code></pre></div>

  <div class="example"><strong>Example 13: Animator in StarterCharacterScripts</strong>
<pre><code>local player = game.Players.LocalPlayer
local humanoid = player.Character:WaitForChild("Humanoid")
local animator = humanoid:FindFirstChildOfClass("Animator")
-- Now use animator to play custom animations
</code></pre></div>

  <div class="example"><strong>Example 14: Check if Animation is Playing</strong>
<pre><code>if track.IsPlaying then
  print("Animation is running!")
end</code></pre></div>

  <div class="example"><strong>Example 15: Remove All Animations</strong>
<pre><code>for _, track in pairs(animator:GetPlayingAnimationTracks()) do
  track:Stop()
end</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Play a dance animation when a player presses "D".<br>
    2. Make a non-humanoid animal run a custom animation when touched.<br>
    3. Blend idle and walk animations for smooth transitions.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always use AnimationController for non-humanoid models—Animator for Humanoids.</div>
  <div class="tip">Use Animation Editor in Studio to create and export custom animations.</div>
  <div class="tip">Set priorities to prevent unwanted animation overrides.</div>
  <div class="warning">Don’t forget to set AnimationId to the correct asset ID!</div>
  <div class="tip">Use marker signals for animation-driven events (sound, effects, logic).</div>
</section><section id="sounds-music">
  <h2>Sounds & Music: Sound, SoundService, Playback, and Effects</h2>
  <blockquote>
    Sounds and music add immersion, feedback, and excitement to your game. Mastering sound lets you create ambiance, effects, and custom audio experiences for players!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. Sound Objects</strong><br>
    The <code>Sound</code> object plays audio from Roblox or custom uploads. Parent sounds to parts, GUIs, or <code>SoundService</code> for global playback.
  </div>
  <div class="deepdive">
    <strong>2. SoundService</strong><br>
    <code>SoundService</code> manages global sounds, music, and ambient effects. Use it for background music, global volume, and environmental sounds.
  </div>
  <div class="deepdive">
    <strong>3. Playback Controls</strong><br>
    Control sounds with <code>:Play()</code>, <code>:Pause()</code>, <code>:Stop()</code>, and properties like <code>Looped</code>, <code>Volume</code>, <code>Pitch</code>, <code>TimePosition</code>.
  </div>
  <div class="deepdive">
    <strong>4. Sound Effects & Properties</strong><br>
    Use <code>EqualizerSoundEffect</code>, <code>ReverbSoundEffect</code>, <code>DistortionSoundEffect</code>, and <code>PitchShiftSoundEffect</code> to customize audio.
  </div>
  <div class="deepdive">
    <strong>5. Triggering Sounds in Scripts</strong><br>
    Play sounds on events—touches, clicks, wins, losses, background music, ambient loops, and more!
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Sounds make your game fun—play music, effects, and feedback!</div>
  <div class="simple">Use <code>:Play()</code> to start sounds, <code>Looped</code> for music, and adjust <code>Volume</code> for loudness.</div>
  <div class="simple">SoundService is for background music and global effects.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Play Sound on Part</strong>
<pre><code>local sound = Instance.new("Sound")
sound.SoundId = "rbxassetid://123456789"
sound.Parent = workspace.Part
sound:Play()</code></pre></div>

  <div class="example"><strong>Example 2: Play Sound Globally</strong>
<pre><code>local sound = Instance.new("Sound")
sound.SoundId = "rbxassetid://987654321"
sound.Parent = game.SoundService
sound:Play()</code></pre></div>

  <div class="example"><strong>Example 3: Loop Background Music</strong>
<pre><code>local music = Instance.new("Sound")
music.SoundId = "rbxassetid://246810121"
music.Looped = true
music.Volume = 0.5
music.Parent = game.SoundService
music:Play()</code></pre></div>

  <div class="example"><strong>Example 4: Pause and Resume Sound</strong>
<pre><code>sound:Pause()
sound:Play()</code></pre></div>

  <div class="example"><strong>Example 5: Stop Sound Playback</strong>
<pre><code>sound:Stop()</code></pre></div>

  <div class="example"><strong>Example 6: Adjust Sound Volume</strong>
<pre><code>sound.Volume = 1 -- Loud
sound.Volume = 0.2 -- Quiet</code></pre></div>

  <div class="example"><strong>Example 7: Change Sound Pitch</strong>
<pre><code>sound.Pitch = 2 -- Higher
sound.Pitch = 0.5 -- Lower</code></pre></div>

  <div class="example"><strong>Example 8: Sound Effects</strong>
<pre><code>local effect = Instance.new("ReverbSoundEffect")
effect.Parent = sound
effect.Level = 0.8</code></pre></div>

  <div class="example"><strong>Example 9: Play Sound on GUI Button Click</strong>
<pre><code>button.MouseButton1Click:Connect(function()
  sound:Play()
end)</code></pre></div>

  <div class="example"><strong>Example 10: Play Sound on Touch Event</strong>
<pre><code>workspace.Part.Touched:Connect(function()
  sound:Play()
end)</code></pre></div>

  <div class="example"><strong>Example 11: Fade In Music</strong>
<pre><code>for i = 0, 1, 0.1 do
  music.Volume = i
  wait(0.1)
end</code></pre></div>

  <div class="example"><strong>Example 12: Play Random Sound from List</strong>
<pre><code>local sounds = {sound1, sound2, sound3}
local pick = sounds[math.random(1,#sounds)]
pick:Play()</code></pre></div>

  <div class="example"><strong>Example 13: Ambient Loop in SoundService</strong>
<pre><code>local ambient = Instance.new("Sound")
ambient.SoundId = "rbxassetid://111222333"
ambient.Looped = true
ambient.Parent = game.SoundService
ambient:Play()</code></pre></div>

  <div class="example"><strong>Example 14: Check if Sound is Playing</strong>
<pre><code>if sound.IsPlaying then
  print("Sound is on!")
end</code></pre></div>

  <div class="example"><strong>Example 15: Set Playback Position</strong>
<pre><code>sound.TimePosition = 10 -- Start at 10 seconds</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Play a sound when a player collects a coin.<br>
    2. Loop background music in SoundService.<br>
    3. Add a reverb effect to a sound and play it on touch.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use <code>SoundService</code> for music and global sounds, parts for local/world sounds.</div>
  <div class="tip">Looped music needs <code>Looped = true</code> and <code>:Play()</code>.</div>
  <div class="tip">Use effects (reverb, equalizer, etc.) for immersive sound.</div>
  <div class="warning">Don’t play too many sounds at once—can cause lag or audio glitches!</div>
  <div class="tip">Check <code>IsPlaying</code> before playing/pausing to avoid errors.</div>
</section><section id="particles-effects">
  <h2>Particles & Effects: ParticleEmitter, Trail, Beam, Explosion</h2>
  <blockquote>
    Particles and effects add visual flair—fire, smoke, sparks, magic, trails, beams, and explosions. Mastering these systems makes your games dazzling, expressive, and fun!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. ParticleEmitter</strong><br>
    Emit particles from a part—fire, smoke, magic, etc. Control color, speed, size, direction, texture, lifetime, rate, and spread for endless effects.
  </div>
  <div class="deepdive">
    <strong>2. Trail</strong><br>
    Attach Trail to two attachments on a model or part. Creates a streak that follows movement—great for swords, cars, projectiles, and more.
  </div>
  <div class="deepdive">
    <strong>3. Beam</strong><br>
    Connects two attachments with a visual beam. Use for lasers, links, energy, or wires. Customize color, width, curve, texture, and transparency.
  </div>
  <div class="deepdive">
    <strong>4. Explosion</strong><br>
    Instantly creates a blast effect at a position, damaging nearby objects and applying force. Use for bombs, spells, and destruction.
  </div>
  <div class="deepdive">
    <strong>5. Scripting Dynamic Effects</strong><br>
    You can adjust properties in scripts for animated, triggered, or interactive effects (change color, size, rate, enable/disable, etc.).
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Particles make fire, smoke, sparkles, and magic in your game.</div>
  <div class="simple">Trails and Beams create streaks and lasers—attach to moving objects!</div>
  <div class="simple">Explosions blast, hurt, and push things—great for bombs and effects!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Create a ParticleEmitter</strong>
<pre><code>local emitter = Instance.new("ParticleEmitter")
emitter.Parent = workspace.Part
emitter.Texture = "rbxassetid://1234567"
emitter.Color = ColorSequence.new(Color3.new(1,0,0), Color3.new(1,1,0)) -- Red to yellow
emitter.Rate = 50
emitter.Lifetime = NumberRange.new(1,3)
emitter.Speed = NumberRange.new(10,20)</code></pre></div>

  <div class="example"><strong>Example 2: Attach a Trail</strong>
<pre><code>local trail = Instance.new("Trail")
trail.Attachment0 = workspace.Sword.AttachmentA
trail.Attachment1 = workspace.Sword.AttachmentB
trail.Parent = workspace.Sword
trail.Color = ColorSequence.new(Color3.new(1,1,1), Color3.new(1,0,0)) -- White to red</code></pre></div>

  <div class="example"><strong>Example 3: Create Beam Between Attachments</strong>
<pre><code>local beam = Instance.new("Beam")
beam.Attachment0 = workspace.Laser.StartAttachment
beam.Attachment1 = workspace.Laser.EndAttachment
beam.Parent = workspace.Laser
beam.Color = ColorSequence.new(Color3.new(0,1,1), Color3.new(0,0,1)) -- Cyan to blue
beam.Width0 = 0.2
beam.Width1 = 0.5</code></pre></div>

  <div class="example"><strong>Example 4: Make an Explosion</strong>
<pre><code>local explosion = Instance.new("Explosion")
explosion.Position = Vector3.new(0, 10, 0)
explosion.BlastRadius = 10
explosion.BlastPressure = 500000
explosion.Parent = workspace</code></pre></div>

  <div class="example"><strong>Example 5: Enable/Disable ParticleEmitter</strong>
<pre><code>emitter.Enabled = false
wait(1)
emitter.Enabled = true</code></pre></div>

  <div class="example"><strong>Example 6: Change ParticleEmitter Properties in Script</strong>
<pre><code>emitter.Rate = 100
emitter.Speed = NumberRange.new(20,40)
emitter.Color = ColorSequence.new(Color3.new(0,1,0), Color3.new(0,0,1)) -- Green to blue</code></pre></div>

  <div class="example"><strong>Example 7: Trail Transparency and Lifetime</strong>
<pre><code>trail.Transparency = NumberSequence.new(0,1)
trail.Lifetime = 1.5</code></pre></div>

  <div class="example"><strong>Example 8: Beam Curve and Texture</strong>
<pre><code>beam.CurveSize0 = 2
beam.Texture = "rbxassetid://7654321"
beam.TextureLength = 5</code></pre></div>

  <div class="example"><strong>Example 9: Explosion Damage Event</strong>
<pre><code>explosion.Hit:Connect(function(part, distance)
  local humanoid = part.Parent:FindFirstChild("Humanoid")
  if humanoid then
    humanoid.Health = humanoid.Health - (30 / distance)
  end
end)</code></pre></div>

  <div class="example"><strong>Example 10: Parenting Effects to Moving Objects</strong>
<pre><code>emitter.Parent = workspace.Car
trail.Parent = workspace.Car
beam.Parent = workspace.Car</code></pre></div>

  <div class="example"><strong>Example 11: Emit Particles on Touch</strong>
<pre><code>workspace.Part.Touched:Connect(function()
  emitter:Emit(30)
end)</code></pre></div>

  <div class="example"><strong>Example 12: Add Multiple Emitters for Complex Effects</strong>
<pre><code>local smoke = Instance.new("ParticleEmitter")
smoke.Texture = "rbxassetid://8888888"
smoke.Color = ColorSequence.new(Color3.new(0.5,0.5,0.5))
smoke.Rate = 20
smoke.Parent = workspace.FirePart
local sparks = Instance.new("ParticleEmitter")
sparks.Texture = "rbxassetid://9999999"
sparks.Color = ColorSequence.new(Color3.new(1,1,0))
sparks.Rate = 10
sparks.Parent = workspace.FirePart</code></pre></div>

  <div class="example"><strong>Example 13: Beam Transparency Animation</strong>
<pre><code>beam.Transparency = NumberSequence.new(0, 0.5, 1)</code></pre></div>

  <div class="example"><strong>Example 14: Particle Lifetime & Spread</strong>
<pre><code>emitter.Lifetime = NumberRange.new(0.5,2)
emitter.SpreadAngle = Vector2.new(45,45)</code></pre></div>

  <div class="example"><strong>Example 15: Remove Effect After Delay</strong>
<pre><code>wait(2)
emitter:Destroy()</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Create a fire particle effect that changes color over time.<br>
    2. Make a sword leave a colored trail when swung.<br>
    3. Trigger an explosion with damage on a button press.<br>
    4. Use a beam to make a laser between two points.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Parent ParticleEmitters, Trails, and Beams to moving parts for dynamic effects.</div>
  <div class="tip">Use Attachments for Trails and Beams—don’t forget to add them!</div>
  <div class="tip">Adjust Rate, Lifetime, Speed, and Color for endless particle effects.</div>
  <div class="warning">Too many emitters or high rates can cause lag—optimize for performance!</div>
  <div class="tip">Use scripting to enable, disable, or change effects for interactive gameplay.</div>
</section><section id="pathfinding-ai">
  <h2>Pathfinding & AI: PathfindingService, AI Movement, Obstacles</h2>
  <blockquote>
    Pathfinding & AI let NPCs move intelligently around obstacles. Use PathfindingService to navigate mazes, chase players, patrol areas, and create engaging, lifelike enemies and companions!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. What is PathfindingService?</strong><br>
    PathfindingService computes paths for moving models and NPCs around obstacles. It finds the best route from point A to point B, avoiding walls, pits, and other objects.
  </div>
  <div class="deepdive">
    <strong>2. Creating Paths</strong><br>
    Call <code>:CreatePath()</code> with a start and end position to generate a path. The path contains waypoints—points to follow step-by-step.
  </div>
  <div class="deepdive">
    <strong>3. Following Paths</strong><br>
    Use <code>MoveTo()</code> on Humanoids to walk to each waypoint. Detect arrival with <code>MoveToFinished</code> to move to the next, and handle stuck or blocked states.
  </div>
  <div class="deepdive">
    <strong>4. Dynamic Obstacles</strong><br>
    If obstacles appear or disappear, the path may become blocked. Recompute paths in scripts to adapt your NPC’s movement in real time.
  </div>
  <div class="deepdive">
    <strong>5. AI Behaviors</strong><br>
    Combine pathfinding with states (patrol, chase, flee, idle) for smart, lifelike AI. You can detect players, change targets, or switch paths based on game logic.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Pathfinding lets NPCs walk around mazes and obstacles automatically.</div>
  <div class="simple">AI uses paths to chase, patrol, or avoid things—makes enemies smart!</div>
  <div class="simple">Recompute paths when the world changes, so NPCs don’t get stuck.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Create a Path</strong>
<pre><code>local PathfindingService = game:GetService("PathfindingService")
local path = PathfindingService:CreatePath({
  AgentRadius = 2,
  AgentHeight = 5,
  AgentCanJump = true,
  AgentJumpHeight = 10,
  AgentMaxSlope = 45,
  Start = workspace.NPC.Position,
  End = workspace.Target.Position
})
path:ComputeAsync(workspace.NPC.Position, workspace.Target.Position)</code></pre></div>

  <div class="example"><strong>Example 2: Follow Path Waypoints</strong>
<pre><code>local humanoid = workspace.NPC.Humanoid
for _, waypoint in ipairs(path:GetWaypoints()) do
  humanoid:MoveTo(waypoint.Position)
  humanoid.MoveToFinished:Wait()
end</code></pre></div>

  <div class="example"><strong>Example 3: Detect Blocked Path</strong>
<pre><code>path.Blocked:Connect(function(blockedWaypointIdx)
  print("Path blocked at:", blockedWaypointIdx)
  -- Recompute or choose new target
end)</code></pre></div>

  <div class="example"><strong>Example 4: AI Patrol Between Points</strong>
<pre><code>local patrolPoints = {Vector3.new(10,0,10), Vector3.new(-10,0,-10)}
local current = 1
while true do
  humanoid:MoveTo(patrolPoints[current])
  humanoid.MoveToFinished:Wait()
  current = current % #patrolPoints + 1
end</code></pre></div>

  <div class="example"><strong>Example 5: Chase Player with Pathfinding</strong>
<pre><code>local player = game.Players:GetPlayers()[1]
local path = PathfindingService:CreatePath({
  Start = npc.Position,
  End = player.Character.HumanoidRootPart.Position
})
path:ComputeAsync(npc.Position, player.Character.HumanoidRootPart.Position)
for _, waypoint in ipairs(path:GetWaypoints()) do
  npc.Humanoid:MoveTo(waypoint.Position)
  npc.Humanoid.MoveToFinished:Wait()
end</code></pre></div>

  <div class="example"><strong>Example 6: Dynamic Repath if Target Moves</strong>
<pre><code>while true do
  local targetPos = workspace.Target.Position
  path:ComputeAsync(npc.Position, targetPos)
  -- Follow waypoints
  wait(1)
end</code></pre></div>

  <div class="example"><strong>Example 7: Detect Arrival at Waypoint</strong>
<pre><code>humanoid.MoveToFinished:Connect(function(reached)
  if reached then print("Arrived!") end
end)</code></pre></div>

  <div class="example"><strong>Example 8: Pathfinding with Jump</strong>
<pre><code>local path = PathfindingService:CreatePath({AgentCanJump = true, AgentJumpHeight = 15})
path:ComputeAsync(npc.Position, workspace.Target.Position)</code></pre></div>

  <div class="example"><strong>Example 9: Avoid Obstacles with Custom Parameters</strong>
<pre><code>local path = PathfindingService:CreatePath({AgentRadius = 4, AgentMaxSlope = 30})
path:ComputeAsync(npc.Position, workspace.Finish.Position)</code></pre></div>

  <div class="example"><strong>Example 10: Pathfinding for Vehicles (no jump)</strong>
<pre><code>local path = PathfindingService:CreatePath({AgentCanJump = false})
path:ComputeAsync(car.Position, workspace.Finish.Position)</code></pre></div>

  <div class="example"><strong>Example 11: NPC Flee from Player</strong>
<pre><code>local safeSpot = Vector3.new(0,0,50)
path:ComputeAsync(npc.Position, safeSpot)
for _, waypoint in ipairs(path:GetWaypoints()) do
  npc.Humanoid:MoveTo(waypoint.Position)
  npc.Humanoid.MoveToFinished:Wait()
end</code></pre></div>

  <div class="example"><strong>Example 12: Use Pathfinding for Multiple NPCs</strong>
<pre><code>for _, npc in pairs(workspace.NPCs:GetChildren()) do
  local path = PathfindingService:CreatePath({Start=npc.Position,End=workspace.Goal.Position})
  path:ComputeAsync(npc.Position, workspace.Goal.Position)
  for _, waypoint in ipairs(path:GetWaypoints()) do
    npc.Humanoid:MoveTo(waypoint.Position)
    npc.Humanoid.MoveToFinished:Wait()
  end
end</code></pre></div>

  <div class="example"><strong>Example 13: React to PathFailure</strong>
<pre><code>path.Failed:Connect(function()
  print("No valid path found!")
end)</code></pre></div>

  <div class="example"><strong>Example 14: Mix Pathfinding with AI States</strong>
<pre><code>local state = "idle"
if playerDetected then
  state = "chase"
  -- Compute path to player
elseif health < 20 then
  state = "flee"
  -- Path to safe spot
end</code></pre></div>

  <div class="example"><strong>Example 15: Draw Path for Debugging</strong>
<pre><code>for _, waypoint in ipairs(path:GetWaypoints()) do
  local marker = Instance.new("Part")
  marker.Position = waypoint.Position
  marker.Size = Vector3.new(1,1,1)
  marker.Anchored = true
  marker.Parent = workspace
end</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Make an NPC patrol between three points using pathfinding.<br>
    2. Make an enemy chase the nearest player, updating its path as the player moves.<br>
    3. Handle blocked paths and retry with new routes.<br>
    4. Use AI states to switch between idle, chase, and flee behaviors.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always recompute paths if obstacles or targets change!</div>
  <div class="tip">Use waypoints for smooth movement—check arrival with <code>MoveToFinished</code>.</div>
  <div class="tip">Handle blocked or failed paths—don’t let NPCs get stuck!</div>
  <div class="warning">Pathfinding only works for models with Humanoids (or custom movement logic that follows waypoints).</div>
  <div class="tip">Combine pathfinding with AI state machines for smart, lifelike NPCs!</div>
</section><section id="modules-code-org">
  <h2>Modules & Code Organization: ModuleScript, require, OOP</h2>
  <blockquote>
    Modules make your code clean, reusable, and organized. Use ModuleScripts to share functions, data, and classes across scripts. Master code organization for scalable, maintainable games!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. ModuleScript</strong><br>
    A <code>ModuleScript</code> returns a table of functions, values, or classes. Place in ReplicatedStorage, ServerScriptService, or local folders for easy sharing.
  </div>
  <div class="deepdive">
    <strong>2. require()</strong><br>
    Use <code>require(module)</code> to load and use a ModuleScript in any other script. Changes in one place update everywhere.
  </div>
  <div class="deepdive">
    <strong>3. Organizing Functions & Data</strong><br>
    Store utility functions, shared data, or configuration in modules. This avoids repeating code and keeps scripts manageable.
  </div>
  <div class="deepdive">
    <strong>4. Object-Oriented Programming (OOP)</strong><br>
    Use ModuleScripts to build classes, methods, and objects. Create constructor functions (<code>new()</code>) and use metatables for inheritance and encapsulation.
  </div>
  <div class="deepdive">
    <strong>5. Cross-Script Communication</strong><br>
    Modules let server/client scripts share logic. But remember: scripts run in different contexts—sync only what’s appropriate!
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">ModuleScript lets you share code—like tools in a toolbox—for any script to use.</div>
  <div class="simple">Use <code>require()</code> to load modules anywhere you need.</div>
  <div class="simple">OOP means making custom objects with properties and functions, organized in modules.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Basic ModuleScript</strong>
<pre><code>-- MyModule (ModuleScript)
local M = {}
function M.sayHello()
  print("Hello from module!")
end
return M</code></pre></div>

  <div class="example"><strong>Example 2: require a Module</strong>
<pre><code>local MyModule = require(game.ReplicatedStorage.MyModule)
MyModule.sayHello()</code></pre></div>

  <div class="example"><strong>Example 3: Utility Functions in Module</strong>
<pre><code>local Util = {}
function Util.add(a, b) return a + b end
function Util.sub(a, b) return a - b end
return Util</code></pre></div>

  <div class="example"><strong>Example 4: Shared Data Table</strong>
<pre><code>local Data = {coins = 0, level = 1}
return Data</code></pre></div>

  <div class="example"><strong>Example 5: OOP Class Pattern</strong>
<pre><code>local PlayerClass = {}
PlayerClass.__index = PlayerClass
function PlayerClass.new(name)
  local self = setmetatable({}, PlayerClass)
  self.name = name
  self.score = 0
  return self
end
function PlayerClass:addScore(amount)
  self.score = self.score + amount
end
return PlayerClass</code></pre></div>

  <div class="example"><strong>Example 6: Instantiate and Use Class</strong>
<pre><code>local PlayerClass = require(game.ReplicatedStorage.PlayerClass)
local player = PlayerClass.new("Ray")
player:addScore(10)
print(player.score)</code></pre></div>

  <div class="example"><strong>Example 7: Config Module</strong>
<pre><code>local Config = {MaxHealth = 100, Speed = 16}
return Config</code></pre></div>

  <div class="example"><strong>Example 8: Module with Events</strong>
<pre><code>local M = {}
M.Event = Instance.new("BindableEvent")
function M.fire(msg)
  M.Event:Fire(msg)
end
return M</code></pre></div>

  <div class="example"><strong>Example 9: Client/Server Shared Logic</strong>
<pre><code>local Shared = require(game.ReplicatedStorage.Shared)
Shared.doSomething()</code></pre></div>

  <div class="example"><strong>Example 10: Metatable Inheritance</strong>
<pre><code>local Animal = {}
function Animal.new(type)
  return setmetatable({type = type}, {__index = Animal})
end
function Animal:speak()
  print("Animal sound!")
end
local Dog = setmetatable({}, {__index = Animal})
function Dog:speak()
  print("Woof!")
end
return {Animal=Animal,Dog=Dog}</code></pre></div>

  <div class="example"><strong>Example 11: Module with Private Function</strong>
<pre><code>local M = {}
local function secret()
  print("Hidden!")
end
function M.reveal()
  secret()
end
return M</code></pre></div>

  <div class="example"><strong>Example 12: Reload Module (debugging)</strong>
<pre><code>package.loaded[script] = nil
local M = require(script)</code></pre></div>

  <div class="example"><strong>Example 13: Module Returning Constructor</strong>
<pre><code>local function newEnemy(name)
  return {name=name,health=100}
end
return newEnemy</code></pre></div>

  <div class="example"><strong>Example 14: Module for StarterPlayerScripts</strong>
<pre><code>local InputUtil = require(game.ReplicatedStorage.InputUtil)
InputUtil.bindKeys()</code></pre></div>

  <div class="example"><strong>Example 15: Organizing Folders</strong>
<pre><code>-- Place ModuleScripts in ReplicatedStorage, ServerScriptService, or StarterPlayerScripts for easy access
</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Make a ModuleScript for math utilities, use it in two scripts.<br>
    2. Create a "Player" class with name and score, supporting addScore.<br>
    3. Organize modules in folders and access them with require().
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always return a table from ModuleScript—never call require() inside the module itself!</div>
  <div class="tip">Use ReplicatedStorage for shared modules, ServerScriptService for server-only logic.</div>
  <div class="tip">Organize modules for easy access and scalability—think ahead!</div>
  <div class="warning">Never store sensitive data in ReplicatedStorage—only in server-only containers!</div>
  <div class="tip">Use OOP patterns for custom objects, NPCs, and reusable code.</div>
</section><section id="remote-events-functions">
  <h2>RemoteEvents, RemoteFunctions, FilteringEnabled, Secure Server-Client Communication</h2>
  <blockquote>
    RemoteEvents and RemoteFunctions allow scripts on the server and client to talk to each other securely. FilteringEnabled protects your game from exploits—master these tools to create safe, interactive multiplayer experiences!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. RemoteEvents</strong><br>
    RemoteEvents are used for fire-and-forget communication between server and client. Server can <code>:FireClient()</code>/<code>:FireAllClients()</code>, client can <code>:FireServer()</code>—no return value.
  </div>
  <div class="deepdive">
    <strong>2. RemoteFunctions</strong><br>
    RemoteFunctions are for request/response communication. Server and client can call each other and wait for a reply with <code>:InvokeServer()</code> and <code>:OnServerInvoke()</code> (and vice versa).
  </div>
  <div class="deepdive">
    <strong>3. FilteringEnabled</strong><br>
    FilteringEnabled is always ON and enforces that client-side changes don’t replicate to other players or the server. Only server can change the true game state—clients just send requests.
  </div>
  <div class="deepdive">
    <strong>4. Secure Communication Patterns</strong><br>
    Always validate and sanitize data from clients on the server. Never trust client input for points, purchases, or critical game logic!
  </div>
  <div class="deepdive">
    <strong>5. ReplicatedStorage for Remotes</strong><br>
    Store RemoteEvents and RemoteFunctions in ReplicatedStorage for easy access by both server and client scripts.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">RemoteEvents let scripts send messages—like "player jumped" or "show effect"—between server and client.</div>
  <div class="simple">RemoteFunctions let scripts ask for info and get a reply—like "what’s my score?"</div>
  <div class="simple">FilteringEnabled protects your game—only the server can make real changes. Always check and clean client data!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Fire RemoteEvent from Client to Server</strong>
<pre><code>-- LocalScript (Client)
game.ReplicatedStorage.MyEvent:FireServer("Hello!")</code></pre></div>

  <div class="example"><strong>Example 2: Listen for RemoteEvent on Server</strong>
<pre><code>-- Script (Server)
game.ReplicatedStorage.MyEvent.OnServerEvent:Connect(function(player, message)
  print(player.Name .. " says: " .. message)
end)</code></pre></div>

  <div class="example"><strong>Example 3: Fire RemoteEvent from Server to All Clients</strong>
<pre><code>game.ReplicatedStorage.MyEvent:FireAllClients("Game Started!")</code></pre></div>

  <div class="example"><strong>Example 4: Listen for RemoteEvent on Client</strong>
<pre><code>game.ReplicatedStorage.MyEvent.OnClientEvent:Connect(function(msg)
  print("Server said: " .. msg)
end)</code></pre></div>

  <div class="example"><strong>Example 5: RemoteFunction Client Requests Data</strong>
<pre><code>-- LocalScript (Client)
local result = game.ReplicatedStorage.MyFunction:InvokeServer("Score")
print("My score:", result)</code></pre></div>

  <div class="example"><strong>Example 6: RemoteFunction Server Handles Request</strong>
<pre><code>-- Script (Server)
game.ReplicatedStorage.MyFunction.OnServerInvoke = function(player, request)
  if request == "Score" then
    return player.leaderstats.Score.Value
  end
end</code></pre></div>

  <div class="example"><strong>Example 7: RemoteFunction Server Requests from Client</strong>
<pre><code>-- Script (Server)
local answer = game.ReplicatedStorage.MyFunction:InvokeClient(player, "Question?")
print("Client said:", answer)</code></pre></div>

  <div class="example"><strong>Example 8: RemoteFunction Client Handles Request</strong>
<pre><code>-- LocalScript (Client)
game.ReplicatedStorage.MyFunction.OnClientInvoke = function(question)
  return "42"
end</code></pre></div>

  <div class="example"><strong>Example 9: Validating Client Data</strong>
<pre><code>-- Always check input!
game.ReplicatedStorage.MyEvent.OnServerEvent:Connect(function(player, points)
  if type(points) ~= "number" or points < 0 then return end
  -- Safe to add points
end)</code></pre></div>

  <div class="example"><strong>Example 10: Block Exploits with Server Checks</strong>
<pre><code>game.ReplicatedStorage.BuyItem.OnServerEvent:Connect(function(player, itemId)
  if not validItem(itemId) then return end
  if player.Money.Value >= getPrice(itemId) then
    -- Allow purchase
  end
end)</code></pre></div>

  <div class="example"><strong>Example 11: FilteringEnabled Protection</strong>
<pre><code>-- Client can only request, server validates and updates stats
game.ReplicatedStorage.AddCoins:FireServer(10)</code></pre></div>

  <div class="example"><strong>Example 12: RemoteEvent for GUI Effects</strong>
<pre><code>-- Server fires RemoteEvent, client shows effect
game.ReplicatedStorage.ShowEffect:FireClient(player, "Explosion")</code></pre></div>

  <div class="example"><strong>Example 13: RemoteFunction for Synchronous Response</strong>
<pre><code>local result = game.ReplicatedStorage.Ask:InvokeServer("What time is it?")
print(result)</code></pre></div>

  <div class="example"><strong>Example 14: Store Remotes in ReplicatedStorage</strong>
<pre><code>local event = Instance.new("RemoteEvent")
event.Name = "MyEvent"
event.Parent = game.ReplicatedStorage
local func = Instance.new("RemoteFunction")
func.Name = "MyFunction"
func.Parent = game.ReplicatedStorage</code></pre></div>

  <div class="example"><strong>Example 15: Secure Server Changes Only</strong>
<pre><code>-- Never let the client directly change scores, money, etc.
-- Always use server scripts and validate!</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Create a RemoteEvent for players to request an effect, with the server validating before showing.<br>
    2. Use RemoteFunction for the client to ask the server for its current coin count.<br>
    3. Make sure only the server can change player stats, never the client.<br>
    4. Handle exploitable requests with validation and rejection.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always validate and sanitize data from clients—never trust client input for critical logic!</div>
  <div class="tip">Store RemoteEvents and RemoteFunctions in ReplicatedStorage for access by both client and server.</div>
  <div class="tip">Use FilteringEnabled (always ON) to keep your game safe from exploits.</div>
  <div class="warning">Never let clients change stats directly—only server scripts should!</div>
  <div class="tip">RemoteEvents are for one-way communication (no response), RemoteFunctions for request/response.</div>
</section><section id="guis-ui">
  <h2>GUIs & UI: ScreenGui, Frame, TextLabel, Button, Events, Animation</h2>
  <blockquote>
    GUIs (Graphical User Interfaces) are menus, HUDs, popups, shops, leaderboards, and more. Mastering UI lets you guide, inform, and delight your players with interactive, animated screens!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. ScreenGui</strong><br>
    The root container for all UI elements. Parent to <code>StarterGui</code> so it appears on players’ screens. Holds Frames, TextLabels, Buttons, etc.
  </div>
  <div class="deepdive">
    <strong>2. Frame</strong><br>
    A rectangular container for grouping other UI elements. Style frames for panels, boxes, windows, etc.
  </div>
  <div class="deepdive">
    <strong>3. TextLabel & TextButton</strong><br>
    <code>TextLabel</code> displays text. <code>TextButton</code> displays clickable text and fires events (like <code>MouseButton1Click</code>).
  </div>
  <div class="deepdive">
    <strong>4. Events & User Input</strong><br>
    Connect functions to events—button clicks, mouse overs, text changes, etc. Make interactive menus, shops, inventory, and more.
  </div>
  <div class="deepdive">
    <strong>5. UI Animation & Tweening</strong><br>
    Animate GUIs with <code>TweenService</code>—move, fade, resize, color-change, etc. Use <code>:TweenPosition()</code>, <code>:TweenSize()</code>, and custom tweens for smooth effects.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">GUIs are menus and popups players see and click on.</div>
  <div class="simple">Frames group things together. TextLabels show info. Buttons let players click!</div>
  <div class="simple">Use events to react to clicks, hovers, and input. Animate GUIs for cool effects.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Creating a ScreenGui</strong>
<pre><code>local gui = Instance.new("ScreenGui")
gui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")</code></pre></div>

  <div class="example"><strong>Example 2: Add a Frame</strong>
<pre><code>local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 300, 0, 200)
frame.Position = UDim2.new(0.5, -150, 0.5, -100)
frame.BackgroundColor3 = Color3.fromRGB(30,30,30)
frame.Parent = gui</code></pre></div>

  <div class="example"><strong>Example 3: Add a TextLabel</strong>
<pre><code>local label = Instance.new("TextLabel")
label.Text = "Hello, Player!"
label.Size = UDim2.new(1,0,0.2,0)
label.Position = UDim2.new(0,0,0,0)
label.BackgroundTransparency = 1
label.TextColor3 = Color3.fromRGB(255,255,255)
label.Parent = frame</code></pre></div>

  <div class="example"><strong>Example 4: Add a Button and Connect Event</strong>
<pre><code>local button = Instance.new("TextButton")
button.Text = "Click Me!"
button.Size = UDim2.new(0.5,0,0.3,0)
button.Position = UDim2.new(0.25,0,0.6,0)
button.BackgroundColor3 = Color3.fromRGB(0,170,255)
button.Parent = frame
button.MouseButton1Click:Connect(function()
  print("Button was clicked!")
end)</code></pre></div>

  <div class="example"><strong>Example 5: Hide/Show GUI</strong>
<pre><code>frame.Visible = false
wait(2)
frame.Visible = true</code></pre></div>

  <div class="example"><strong>Example 6: Tween Position Animation</strong>
<pre><code>frame:TweenPosition(UDim2.new(0.5, -150, 0.8, -100), "Out", "Bounce", 1)</code></pre></div>

  <div class="example"><strong>Example 7: TweenService for Smooth Effects</strong>
<pre><code>local TweenService = game:GetService("TweenService")
local tween = TweenService:Create(frame, TweenInfo.new(0.5), {BackgroundColor3 = Color3.new(1,0,0)})
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 8: Animate Button Size</strong>
<pre><code>button:TweenSize(UDim2.new(0.6,0,0.4,0), "Out", "Quad", 0.5)</code></pre></div>

  <div class="example"><strong>Example 9: Change Label Text on Button Click</strong>
<pre><code>button.MouseButton1Click:Connect(function()
  label.Text = "Clicked!"
end)</code></pre></div>

  <div class="example"><strong>Example 10: InputBox for Player Text</strong>
<pre><code>local input = Instance.new("TextBox")
input.PlaceholderText = "Type here..."
input.Size = UDim2.new(0.8,0,0.2,0)
input.Position = UDim2.new(0.1,0,0.8,0)
input.Parent = frame
input.FocusLost:Connect(function(enter)
  if enter then
    print("Player typed:", input.Text)
  end
end)</code></pre></div>

  <div class="example"><strong>Example 11: Animate Transparency</strong>
<pre><code>frame.BackgroundTransparency = 1
local tween = TweenService:Create(frame, TweenInfo.new(1), {BackgroundTransparency = 0})
tween:Play()</code></pre></div>

  <div class="example"><strong>Example 12: Show Popup Message</strong>
<pre><code>label.Text = "You earned a badge!"
frame.Visible = true
wait(2)
frame.Visible = false</code></pre></div>

  <div class="example"><strong>Example 13: Hover Button Effects</strong>
<pre><code>button.MouseEnter:Connect(function()
  button.BackgroundColor3 = Color3.fromRGB(255,255,0)
end)
button.MouseLeave:Connect(function()
  button.BackgroundColor3 = Color3.fromRGB(0,170,255)
end)</code></pre></div>

  <div class="example"><strong>Example 14: Draggable GUI</strong>
<pre><code>frame.Active = true
frame.Draggable = true</code></pre></div>

  <div class="example"><strong>Example 15: Close Button to Destroy GUI</strong>
<pre><code>local close = Instance.new("TextButton")
close.Text = "X"
close.Size = UDim2.new(0,30,0,30)
close.Position = UDim2.new(1,-35,0,5)
close.Parent = frame
close.MouseButton1Click:Connect(function()
  gui:Destroy()
end)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Make a GUI with a button that updates a label when clicked.<br>
    2. Animate a menu frame sliding in and out.<br>
    3. Add a text input and display the player’s entry in a popup.<br>
    4. Make a close button to remove the GUI.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Parent ScreenGui to PlayerGui to show it on the player’s screen.</div>
  <div class="tip">Use TweenService for smooth animations—don’t just jump instantly!</div>
  <div class="tip">Connect events for all interactive elements—clicks, hovers, inputs.</div>
  <div class="warning">Don’t overload the screen with too many GUIs—keep it clean and readable!</div>
  <div class="tip">Organize GUIs in folders and use modules for reusable UI code.</div>
</section><section id="avatar-customization">
  <h2>Avatar Customization & Accessories: BodyParts, Clothing, Accessory, Humanoid Properties</h2>
  <blockquote>
    Avatar customization lets players express themselves with unique looks! Learn to script body parts, clothes, accessories, and humanoid properties for creative, personalized characters.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive">
    <strong>1. BodyParts</strong><br>
    Avatars are composed of BodyParts (Head, Torso, LeftArm, etc.). You can swap, recolor, or resize these to change appearance. R6 (6 parts) and R15 (15 parts) are Roblox’s main avatar rigs.
  </div>
  <div class="deepdive">
    <strong>2. Clothing</strong><br>
    Clothing includes <code>Pants</code> and <code>Shirt</code> objects. Parent these to the character to display custom textures. Use asset IDs for thousands of styles!
  </div>
  <div class="deepdive">
    <strong>3. Accessories</strong><br>
    Accessories are hats, hair, glasses, gear, etc. Add <code>Accessory</code> objects to the character to equip items. Each accessory has an <code>Attachment</code> to position it on the avatar.
  </div>
  <div class="deepdive">
    <strong>4. Humanoid Properties</strong><br>
    Change scale, health, walk speed, jump power, and more via the Humanoid object. Control animation type (R6/R15), display name, health, and core avatar behaviors.
  </div>
  <div class="deepdive">
    <strong>5. Scripting Customization</strong><br>
    Script avatar changes—equip items, swap clothes, change colors, resize parts, update humanoid properties, or create shops for player customization.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Players can wear shirts, pants, hats, and more—change looks anytime!</div>
  <div class="simple">Accessories are items like hats and swords. Humanoid controls movement and health.</div>
  <div class="simple">Script avatar changes for shops, power-ups, and fun!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Change Shirt and Pants</strong>
<pre><code>local shirt = Instance.new("Shirt")
shirt.ShirtTemplate = "rbxassetid://123456789"
shirt.Parent = player.Character
local pants = Instance.new("Pants")
pants.PantsTemplate = "rbxassetid://987654321"
pants.Parent = player.Character</code></pre></div>

  <div class="example"><strong>Example 2: Add Hat Accessory</strong>
<pre><code>local accessory = game.ReplicatedStorage.Hat:Clone()
accessory.Parent = player.Character</code></pre></div>

  <div class="example"><strong>Example 3: Change BodyPart Color</strong>
<pre><code>player.Character.Head.Color = Color3.new(1, 0.8, 0.6)</code></pre></div>

  <div class="example"><strong>Example 4: Resize BodyPart</strong>
<pre><code>player.Character["LeftArm"].Size = Vector3.new(2, 2, 1)</code></pre></div>

  <div class="example"><strong>Example 5: Change Display Name</strong>
<pre><code>player.Character.Humanoid.DisplayName = "Champion"</code></pre></div>

  <div class="example"><strong>Example 6: Adjust WalkSpeed & JumpPower</strong>
<pre><code>local humanoid = player.Character.Humanoid
humanoid.WalkSpeed = 32
humanoid.JumpPower = 100</code></pre></div>

  <div class="example"><strong>Example 7: Equip Multiple Accessories</strong>
<pre><code>for _, item in pairs(shopItems) do
  local accessory = item:Clone()
  accessory.Parent = player.Character
end</code></pre></div>

  <div class="example"><strong>Example 8: Remove Accessory</strong>
<pre><code>for _, acc in pairs(player.Character:GetChildren()) do
  if acc:IsA("Accessory") then
    acc:Destroy()
  end
end</code></pre></div>

  <div class="example"><strong>Example 9: Change Humanoid RigType</strong>
<pre><code>player.Character.Humanoid.RigType = Enum.HumanoidRigType.R15</code></pre></div>

  <div class="example"><strong>Example 10: Create Custom Avatar Shop</strong>
<pre><code>local function buyAccessory(player, accessoryName)
  local accessory = game.ReplicatedStorage.Accessories:FindFirstChild(accessoryName):Clone()
  accessory.Parent = player.Character
end</code></pre></div>

  <div class="example"><strong>Example 11: Change Head Mesh for Custom Shape</strong>
<pre><code>local mesh = Instance.new("SpecialMesh")
mesh.MeshType = Enum.MeshType.Head
mesh.Scale = Vector3.new(2,2,2)
mesh.Parent = player.Character.Head</code></pre></div>

  <div class="example"><strong>Example 12: Script for Random Outfit</strong>
<pre><code>local shirts = {"id1", "id2", "id3"}
local pants = {"id4", "id5", "id6"}
local shirt = Instance.new("Shirt")
shirt.ShirtTemplate = "rbxassetid://" .. shirts[math.random(1,#shirts)]
shirt.Parent = player.Character
local pant = Instance.new("Pants")
pant.PantsTemplate = "rbxassetid://" .. pants[math.random(1,#pants)]
pant.Parent = player.Character</code></pre></div>

  <div class="example"><strong>Example 13: Detect Accessory Equipped</strong>
<pre><code>player.Character.ChildAdded:Connect(function(child)
  if child:IsA("Accessory") then
    print("Equipped:", child.Name)
  end
end)</code></pre></div>

  <div class="example"><strong>Example 14: Script for Avatar Reset</strong>
<pre><code>player:LoadCharacter()</code></pre></div>

  <div class="example"><strong>Example 15: Humanoid Health & Death Effects</strong>
<pre><code>player.Character.Humanoid.Died:Connect(function()
  print(player.Name .. " has died!")
end)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Script a shop to let players buy and equip hats.<br>
    2. Change a player’s shirt and pants with buttons.<br>
    3. Resize body parts for power-ups.<br>
    4. Detect when a player equips a new accessory.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Store accessories and clothes in ReplicatedStorage for easy access!</div>
  <div class="tip">Always check if <code>player.Character</code> exists before changing body parts or accessories.</div>
  <div class="tip">Use Humanoid properties for walk speed, jump power, and display name changes.</div>
  <div class="warning">Don’t equip too many accessories—may cause visual glitches!</div>
  <div class="tip">Script random outfits or shops for fun customization!</div>
</section><section id="game-structure-organization">
  <h2>Game Structure & Organization: Folders, Scripts, Best Practices</h2>
  <blockquote>
    Well-organized games are scalable, maintainable, and easy to debug. Structure your folders, scripts, and assets for clarity and efficiency!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. Folders & Hierarchies</strong><br>
    Use <code>Folder</code> instances to group related parts, scripts, assets, or NPCs. Organize for logic, not just looks!
  </div>
  <div class="deepdive"><strong>2. Script Placement</strong><br>
    Place <code>Script</code> in <code>ServerScriptService</code> for server logic, <code>LocalScript</code> in <code>StarterPlayerScripts</code> or <code>StarterGui</code> for client logic.
  </div>
  <div class="deepdive"><strong>3. Asset Management</strong><br>
    Store models, RemoteEvents, ModuleScripts in <code>ReplicatedStorage</code> for easy access by both server and client.
  </div>
  <div class="deepdive"><strong>4. Naming Conventions</strong><br>
    Use clear, consistent names for parts, folders, scripts, and assets. Prefix or suffix for type (e.g., “EnemyAI”, “CoinSpawner”).
  </div>
  <div class="deepdive"><strong>5. Best Practices</strong><br>
    Avoid clutter, keep hierarchy shallow, use modules/functions for repeated logic, and document with comments.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Folders group stuff so you stay organized. Put scripts where they belong!</div>
  <div class="simple">Give everything clear names—easy to find, easy to fix.</div>
  <div class="simple">Use ReplicatedStorage for shared stuff, ServerScriptService for server code.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Create a Folder</strong>
<pre><code>local folder = Instance.new("Folder")
folder.Name = "Enemies"
folder.Parent = workspace</code></pre></div>
  <div class="example"><strong>Example 2: Organize NPCs</strong>
<pre><code>workspace.Enemies:FindFirstChild("Zombie").Parent = workspace.Enemies</code></pre></div>
  <div class="example"><strong>Example 3: Script Placement</strong>
<pre><code>-- Server scripts go in ServerScriptService
-- LocalScripts go in StarterPlayerScripts or StarterGui</code></pre></div>
  <div class="example"><strong>Example 4: Asset in ReplicatedStorage</strong>
<pre><code>local sword = game.ReplicatedStorage.Sword:Clone()
sword.Parent = workspace</code></pre></div>
  <div class="example"><strong>Example 5: Naming Conventions</strong>
<pre><code>local coinSpawner = Instance.new("Script")
coinSpawner.Name = "CoinSpawner"</code></pre></div>
  <div class="example"><strong>Example 6: Find All Scripts in Folder</strong>
<pre><code>for _, obj in pairs(game.ServerScriptService:GetChildren()) do
  if obj:IsA("Script") then print(obj.Name) end
end</code></pre></div>
  <div class="example"><strong>Example 7: Use ModuleScripts for Reuse</strong>
<pre><code>local Util = require(game.ReplicatedStorage.Util)
Util.doSomething()</code></pre></div>
  <div class="example"><strong>Example 8: Document with Comments</strong>
<pre><code>-- This script spawns coins every 5 seconds</code></pre></div>
  <div class="example"><strong>Example 9: Avoid Deep Nesting</strong>
<pre><code>-- Instead of workspace.Models.Enemies.Zombie, use workspace.Enemies.Zombie</code></pre></div>
  <div class="example"><strong>Example 10: Organize GUIs</strong>
<pre><code>local guiFolder = Instance.new("Folder")
guiFolder.Name = "ShopGUIs"
guiFolder.Parent = game.StarterGui</code></pre></div>
  <div class="example"><strong>Example 11: Centralize RemoteEvents</strong>
<pre><code>local event = Instance.new("RemoteEvent")
event.Name = "ShopBuy"
event.Parent = game.ReplicatedStorage</code></pre></div>
  <div class="example"><strong>Example 12: Find by Name</strong>
<pre><code>local npc = workspace.Enemies:FindFirstChild("Boss")
if npc then print("Found Boss!") end</code></pre></div>
  <div class="example"><strong>Example 13: Remove Unused Assets</strong>
<pre><code>for _, obj in pairs(workspace:GetChildren()) do
  if obj.Name == "OldModel" then obj:Destroy() end
end</code></pre></div>
  <div class="example"><strong>Example 14: Folder for Effects</strong>
<pre><code>local effects = Instance.new("Folder")
effects.Name = "Effects"
effects.Parent = workspace</code></pre></div>
  <div class="example"><strong>Example 15: Folder for Player Data</strong>
<pre><code>local dataFolder = Instance.new("Folder")
dataFolder.Name = player.Name .. "_Data"
dataFolder.Parent = game.ServerStorage</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Organize NPCs, coins, and effects into folders.<br>
    2. Move shared assets to ReplicatedStorage.<br>
    3. Use clear naming for all scripts and models.<br>
    4. Document at least three scripts with comments.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Keep your hierarchy clean—avoid deep nesting!</div>
  <div class="tip">Use folders for grouping, not just visuals.</div>
  <div class="tip">Organize scripts and assets for easy debugging and scaling.</div>
  <div class="warning">Don’t put sensitive data in ReplicatedStorage—use ServerStorage or ServerScriptService!</div>
  <div class="tip">Name everything clearly and consistently.</div>
</section><section id="monetization-marketplace">
  <h2>Monetization & Marketplace: Developer Products, GamePasses, Selling Items</h2>
  <blockquote>
    Monetization lets your game earn revenue through sales—GamePasses, Developer Products, shops, and more. Use secure server logic and provide real value!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. GamePasses</strong><br>
    GamePasses are permanent purchases for special powers, access, or cosmetics. Check ownership with <code>PlayerOwnsAsset</code>.
  </div>
  <div class="deepdive"><strong>2. Developer Products</strong><br>
    Developer Products are one-time purchases (coins, boosts, items). Handle purchases securely with <code>ProcessReceipt</code>.
  </div>
  <div class="deepdive"><strong>3. MarketplaceService</strong><br>
    Use <code>MarketplaceService</code> for all purchases. Connect events for <code>PromptPurchaseFinished</code> and <code>ProcessReceipt</code>.
  </div>
  <div class="deepdive"><strong>4. Secure Transactions</strong><br>
    Validate all purchases server-side. Never trust client for giving items or currency!
  </div>
  <div class="deepdive"><strong>5. Selling Items</strong><br>
    Create in-game shops using GUIs and RemoteEvents. Award items/currency only after confirming purchase.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">GamePasses are powers forever. Developer Products are boosts or coins you buy once.</div>
  <div class="simple">Use MarketplaceService for all purchases. Always check on the server!</div>
  <div class="simple">Only give items after the server confirms the player paid!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Check GamePass Ownership</strong>
<pre><code>local MarketplaceService = game:GetService("MarketplaceService")
local passId = 123456
local hasPass = MarketplaceService:PlayerOwnsAsset(player, passId)
if hasPass then
  print("Player owns the pass!")
end</code></pre></div>
  <div class="example"><strong>Example 2: Prompt GamePass Purchase</strong>
<pre><code>MarketplaceService:PromptGamePassPurchase(player, passId)</code></pre></div>
  <div class="example"><strong>Example 3: Prompt Developer Product Purchase</strong>
<pre><code>MarketplaceService:PromptProductPurchase(player, 987654)</code></pre></div>
  <div class="example"><strong>Example 4: Handle Product Purchase</strong>
<pre><code>MarketplaceService.ProcessReceipt = function(receiptInfo)
  local player = game.Players:GetPlayerByUserId(receiptInfo.PlayerId)
  if receiptInfo.ProductId == 987654 then
    player.leaderstats.Coins.Value = player.leaderstats.Coins.Value + 100
  end
  return Enum.ProductPurchaseDecision.PurchaseGranted
end</code></pre></div>
  <div class="example"><strong>Example 5: Secure Shop Logic</strong>
<pre><code>game.ReplicatedStorage.BuyItem.OnServerEvent:Connect(function(player, itemId)
  if canBuy(player, itemId) then
    giveItem(player, itemId)
  end
end)</code></pre></div>
  <div class="example"><strong>Example 6: GUI Shop Button</strong>
<pre><code>buyButton.MouseButton1Click:Connect(function()
  game.ReplicatedStorage.BuyItem:FireServer(itemId)
end)</code></pre></div>
  <div class="example"><strong>Example 7: Confirm Purchase on Server</strong>
<pre><code>MarketplaceService.PromptPurchaseFinished:Connect(function(player, assetId, isPurchased)
  if isPurchased then
    -- Give reward
  end
end)</code></pre></div>
  <div class="example"><strong>Example 8: Prevent Exploits</strong>
<pre><code>if not validatePurchase(player, itemId) then return end</code></pre></div>
  <div class="example"><strong>Example 9: Leaderboard Award</strong>
<pre><code>player.leaderstats.Coins.Value = player.leaderstats.Coins.Value + 50</code></pre></div>
  <div class="example"><strong>Example 10: Refund Logic</strong>
<pre><code>-- Only refund if server-side logic detects a problem</code></pre></div>
  <div class="example"><strong>Example 11: Shop Item Table</strong>
<pre><code>local shopItems = {["Sword"] = 100, ["Shield"] = 150}</code></pre></div>
  <div class="example"><strong>Example 12: Award Item After Purchase</strong>
<pre><code>if purchaseConfirmed then
  giveItem(player, itemName)
end</code></pre></div>
  <div class="example"><strong>Example 13: Purchase Prompt for GamePass</strong>
<pre><code>MarketplaceService:PromptGamePassPurchase(player, gamePassId)</code></pre></div>
  <div class="example"><strong>Example 14: ProcessReceipt for Multiple Products</strong>
<pre><code>if receiptInfo.ProductId == coinId then
  awardCoins(player, 100)
elseif receiptInfo.ProductId == boostId then
  awardBoost(player)
end</code></pre></div>
  <div class="example"><strong>Example 15: Shop Confirmation GUI</strong>
<pre><code>confirmButton.MouseButton1Click:Connect(function()
  -- Confirm purchase before sending to server
end)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Script a shop that sells two items—one via GamePass, one via Developer Product.<br>
    2. Securely award coins only if ProcessReceipt confirms purchase.<br>
    3. Protect against exploits by validating all purchases on the server!
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Always use server-side checks for purchases!</div>
  <div class="tip">Use MarketplaceService events for all transactions.</div>
  <div class="tip">Award items only after purchase is confirmed server-side.</div>
  <div class="warning">Never let clients award themselves coins or items!</div>
  <div class="tip">Document your shop logic for easy updates.</div>
</section><section id="optimization-performance">
  <h2>Optimization & Performance: Lag Reduction, Efficient Code, Streaming</h2>
  <blockquote>
    Fast, smooth games keep players happy! Optimize scripts, assets, and physics for maximum performance and minimum lag.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. Script Optimization</strong><br>
    Write efficient code—avoid unnecessary loops, debounce events, and use wait() or task.wait() sparingly.
  </div>
  <div class="deepdive"><strong>2. Asset Optimization</strong><br>
    Use low-poly models, compressed textures, and minimal particles. Remove unused assets!
  </div>
  <div class="deepdive"><strong>3. Physics & Collision Groups</strong><br>
    Use collision groups to avoid unnecessary physics checks. Anchor static parts and limit moving objects.
  </div>
  <div class="deepdive"><strong>4. StreamingEnabled</strong><br>
    Enable StreamingEnabled to load parts of the map only as needed. Great for large worlds!
  </div>
  <div class="deepdive"><strong>5. Monitoring Performance</strong><br>
    Use MicroProfiler (Ctrl+F6) and Output window to find bottlenecks and errors.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Make your game run smooth—less lag, faster scripts, small models!</div>
  <div class="simple">Anchor things that don’t move. Use StreamingEnabled for giant maps.</div>
  <div class="simple">Watch for slow code and too many effects—keep it simple!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Debounce Button Click</strong>
<pre><code>local debounce = false
button.MouseButton1Click:Connect(function()
  if debounce then return end
  debounce = true
  -- action
  wait(1)
  debounce = false
end)</code></pre></div>
  <div class="example"><strong>Example 2: Anchor Static Parts</strong>
<pre><code>for _, part in pairs(workspace.Static:GetChildren()) do
  part.Anchored = true
end</code></pre></div>
  <div class="example"><strong>Example 3: Use Collision Groups</strong>
<pre><code>local PhysicsService = game:GetService("PhysicsService")
PhysicsService:CreateCollisionGroup("NPCs")
PhysicsService:SetPartCollisionGroup(npcPart, "NPCs")</code></pre></div>
  <div class="example"><strong>Example 4: StreamingEnabled Setup</strong>
<pre><code>game.Workspace.StreamingEnabled = true</code></pre></div>
  <div class="example"><strong>Example 5: Remove Unused Assets</strong>
<pre><code>for _, obj in pairs(workspace:GetChildren()) do
  if obj.Name == "OldEffect" then obj:Destroy() end
end</code></pre></div>
  <div class="example"><strong>Example 6: Efficient Looping</strong>
<pre><code>for i = 1, #items do
  process(items[i])
end</code></pre></div>
  <div class="example"><strong>Example 7: Limit Particle Rate</strong>
<pre><code>emitter.Rate = 10 -- Lower rate for performance</code></pre></div>
  <div class="example"><strong>Example 8: Use task.wait()</strong>
<pre><code>for i = 1, 10 do
  task.wait(0.5)
end</code></pre></div>
  <div class="example"><strong>Example 9: Monitor Performance</strong>
<pre><code>print("Script start:", os.clock())
-- code
print("Script end:", os.clock())</code></pre></div>
  <div class="example"><strong>Example 10: Profile with MicroProfiler</strong>
<pre><code>-- Press Ctrl+F6 in Studio to open MicroProfiler</code></pre></div>
  <div class="example"><strong>Example 11: Avoid Unnecessary Loops</strong>
<pre><code>if condition then
  -- Only loop if needed
end</code></pre></div>
  <div class="example"><strong>Example 12: Group Effects for Toggle</strong>
<pre><code>for _, effect in pairs(workspace.Effects:GetChildren()) do
  effect.Enabled = false
end</code></pre></div>
  <div class="example"><strong>Example 13: Use LocalScripts for Client Effects</strong>
<pre><code>-- Only show particles/sounds on local client, not server</code></pre></div>
  <div class="example"><strong>Example 14: Remove Debris with Debris Service</strong>
<pre><code>local Debris = game:GetService("Debris")
Debris:AddItem(part, 5)</code></pre></div>
  <div class="example"><strong>Example 15: Check Player Ping</strong>
<pre><code>local ping = player:GetNetworkPing()
print("Player ping:", ping)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Debounce a shop button for lag-free purchases.<br>
    2. Anchor all static scenery parts.<br>
    3. Set up StreamingEnabled for a huge map.<br>
    4. Profile a script to find slow sections.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use StreamingEnabled for big worlds—players only load what they need!</div>
  <div class="tip">Anchor everything that doesn’t move to save CPU.</div>
  <div class="tip">Remove unused models, sounds, and particles.</div>
  <div class="warning">Too many loops, parts, or effects = lag!</div>
  <div class="tip">Profile your game regularly to keep it fast.</div>
</section><section id="security-anti-exploit">
  <h2>Security & Anti-Exploit: Server-side Checks, Exploit Prevention</h2>
  <blockquote>
    Secure games prevent cheating, exploits, and abuse. Learn how to validate client data, protect server logic, and respond to suspicious behavior!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. Server-side Validation</strong><br>
    Always check and sanitize any data sent by clients—never trust client input for critical game logic!
  </div>
  <div class="deepdive"><strong>2. Restrict Sensitive Logic to Server</strong><br>
    Only change leaderstats, currency, items, and progress on the server—not the client!
  </div>
  <div class="deepdive"><strong>3. Anti-Exploit Detection</strong><br>
    Detect suspicious or impossible actions (e.g., move too fast, buy items without payment). Log and respond to exploit attempts.
  </div>
  <div class="deepdive"><strong>4. Rate Limiting & Debouncing</strong><br>
    Use debounces and limits for RemoteEvents/Functions—prevent spam and abuse.
  </div>
  <div class="deepdive"><strong>5. FilteringEnabled & Remotes</strong><br>
    FilteringEnabled (always ON) ensures only the server can change the game state. Use RemoteEvents/Functions for communication.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Never trust the client—check everything on the server!</div>
  <div class="simple">Only the server should change coins, stats, and items.</div>
  <div class="simple">Detect and block cheaters—keep your game safe!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Validate RemoteEvent Data</strong>
<pre><code>game.ReplicatedStorage.AddCoins.OnServerEvent:Connect(function(player, amount)
  if type(amount) ~= "number" or amount < 0 or amount > 100 then return end
  player.leaderstats.Coins.Value = player.leaderstats.Coins.Value + amount
end)</code></pre></div>
  <div class="example"><strong>Example 2: Restrict Leaderstats Changes</strong>
<pre><code>game.ReplicatedStorage.ChangeStats.OnServerEvent:Connect(function(player, stat, value)
  if stat == "Coins" and type(value) == "number" then
    player.leaderstats.Coins.Value = value
  end
end)</code></pre></div>
  <div class="example"><strong>Example 3: Log Exploit Attempts</strong>
<pre><code>if suspicious then
  print("Exploit attempt by:", player.Name)
end</code></pre></div>
  <div class="example"><strong>Example 4: Debounce RemoteEvents</strong>
<pre><code>local debounce = {}
game.ReplicatedStorage.SomeEvent.OnServerEvent:Connect(function(player)
  if debounce[player] then return end
  debounce[player] = true
  -- action
  wait(2)
  debounce[player] = nil
end)</code></pre></div>
  <div class="example"><strong>Example 5: Detect Impossible Movement</strong>
<pre><code>if (player.Character.HumanoidRootPart.Position - lastPosition).magnitude > maxDistance then
  print("Possible teleport exploit!")
end</code></pre></div>
  <div class="example"><strong>Example 6: Kick Cheaters</strong>
<pre><code>if cheatingDetected then
  player:Kick("Exploiting detected!")
end</code></pre></div>
  <div class="example"><strong>Example 7: FilteringEnabled Protection</strong>
<pre><code>-- Only server scripts change stats, client requests via RemoteEvents</code></pre></div>
  <div class="example"><strong>Example 8: Rate Limit Requests</strong>
<pre><code>local lastRequest = {}
game.ReplicatedStorage.Buy.OnServerEvent:Connect(function(player)
  if os.clock() - (lastRequest[player] or 0) < 1 then return end
  lastRequest[player] = os.clock()
  -- process
end)</code></pre></div>
  <div class="example"><strong>Example 9: Secure Purchases</strong>
<pre><code>if not validPurchase(player, itemId) then return end</code></pre></div>
  <div class="example"><strong>Example 10: Log Stats Changes</strong>
<pre><code>print(player.Name .. " changed stats:", stat, value)</code></pre></div>
  <div class="example"><strong>Example 11: Block Multiple Requests</strong>
<pre><code>if requestCount[player] > 10 then
  player:Kick("Too many requests!")
end</code></pre></div>
  <div class="example"><strong>Example 12: Use ServerStorage for Sensitive Data</strong>
<pre><code>local secret = Instance.new("Folder")
secret.Parent = game.ServerStorage</code></pre></div>
  <div class="example"><strong>Example 13: Block Exploit GUI</strong>
<pre><code>if player.PlayerGui:FindFirstChild("ExploitGUI") then
  player:Kick("Unauthorized GUI detected!")
end</code></pre></div>
  <div class="example"><strong>Example 14: Secure RemoteFunction</strong>
<pre><code>game.ReplicatedStorage.GetData.OnServerInvoke = function(player, request)
  if type(request) ~= "string" then return end
  -- return safe data
end</code></pre></div>
  <div class="example"><strong>Example 15: Monitor Suspicious Behavior</strong>
<pre><code>game.Players.PlayerAdded:Connect(function(player)
  player.Chatted:Connect(function(msg)
    if isSuspicious(msg) then
      print("Suspicious chat:", msg)
    end
  end)
end)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Validate all RemoteEvent data for coins, items, and stats.<br>
    2. Block and log impossible movement and rapid requests.<br>
    3. Kick players who repeatedly try to exploit.<br>
    4. Store sensitive data server-side only!
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Validate everything sent from the client!</div>
  <div class="tip">Only the server should change leaderstats and items.</div>
  <div class="tip">Log and respond to suspicious actions—don’t ignore possible exploits!</div>
  <div class="warning">Never let clients change coins or items directly!</div>
  <div class="tip">Use ServerStorage for secrets, never ReplicatedStorage!</div>
</section><section id="testing-debugging-error-handling">
  <h2>Testing, Debugging, Error Handling: Output, Breakpoints, try/catch</h2>
  <blockquote>
    Test and debug scripts to find bugs fast! Use Output, breakpoints, and error handling for reliable games.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. Output Window</strong><br>
    Use <code>print()</code>, <code>warn()</code>, and <code>error()</code> to log info and find bugs. The Output window shows all messages.
  </div>
  <div class="deepdive"><strong>2. Breakpoints & Step Debugging</strong><br>
    In Studio, click gutter to set breakpoints. Step through code to watch variable changes.
  </div>
  <div class="deepdive"><strong>3. Error Handling</strong><br>
    Use <code>pcall()</code> for protected calls, catch and handle errors gracefully.
  </div>
  <div class="deepdive"><strong>4. try/catch Patterns</strong><br>
    Lua uses <code>pcall()</code>, not try/catch. Use <code>pcall</code> to run code safely.
  </div>
  <div class="deepdive"><strong>5. Automated Testing</strong><br>
    Write test scripts to check functions and features before publishing.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Use print() and Output to find bugs. Set breakpoints to pause code.</div>
  <div class="simple">Use pcall() to catch errors—never crash!</div>
  <div class="simple">Test your game before publishing—always!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Print to Output</strong>
<pre><code>print("Hello, world!")</code></pre></div>
  <div class="example"><strong>Example 2: Warning Message</strong>
<pre><code>warn("This could be a problem!")</code></pre></div>
  <div class="example"><strong>Example 3: Error Message</strong>
<pre><code>error("Something went wrong!")</code></pre></div>
  <div class="example"><strong>Example 4: pcall Error Handling</strong>
<pre><code>local success, result = pcall(function()
  return dangerousFunction()
end)
if not success then
  print("Error:", result)
end</code></pre></div>
  <div class="example"><strong>Example 5: Set Breakpoint (Studio)</strong>
<pre><code>-- Click gutter to set breakpoint, then run and step through code</code></pre></div>
  <div class="example"><strong>Example 6: Debugging Variable</strong>
<pre><code>print("Coins before:", player.leaderstats.Coins.Value)</code></pre></div>
  <div class="example"><strong>Example 7: Step Debugging</strong>
<pre><code>-- Use Step Over/Into in Studio to watch code</code></pre></div>
  <div class="example"><strong>Example 8: Automated Test Script</strong>
<pre><code>local function testAdd(a, b)
  return a + b
end
assert(testAdd(2,3) == 5, "Test failed!")</code></pre></div>
  <div class="example"><strong>Example 9: Catch RemoteEvent Errors</strong>
<pre><code>game.ReplicatedStorage.MyEvent.OnServerEvent:Connect(function(player, data)
  local ok, err = pcall(function()
    process(data)
  end)
  if not ok then print("Error:", err) end
end)</code></pre></div>
  <div class="example"><strong>Example 10: Test Leaderboard Update</strong>
<pre><code>assert(player.leaderstats.Coins.Value == expectedCoins, "Leaderboard error!")</code></pre></div>
  <div class="example"><strong>Example 11: Debugging GUI</strong>
<pre><code>print("Button Visible:", button.Visible)</code></pre></div>
  <div class="example"><strong>Example 12: Error Handling in Module</strong>
<pre><code>local success, err = pcall(Module.doSomething)
if not success then warn(err) end</code></pre></div>
  <div class="example"><strong>Example 13: Output for DataStore Errors</strong>
<pre><code>local ok, result = pcall(function()
  return DataStore:GetAsync(key)
end)
if not ok then
  warn("DataStore error:", result)
end</code></pre></div>
  <div class="example"><strong>Example 14: Assert for Testing</strong>
<pre><code>assert(type(value) == "number", "Not a number!")</code></pre></div>
  <div class="example"><strong>Example 15: Test Script for Shop Purchase</strong>
<pre><code>assert(shop:Buy("Sword") == true, "Shop purchase failed!")</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Print variable values before and after actions.<br>
    2. Use pcall() to protect RemoteEvent processing.<br>
    3. Write simple test scripts for key functions.<br>
    4. Set breakpoints and step through a script in Studio.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use print(), warn(), error() to debug and log info.</div>
  <div class="tip">Always protect dangerous code with pcall().</div>
  <div class="tip">Test before publishing—bugs are easier to fix early!</div>
  <div class="warning">Don’t ignore Output warnings and errors—they show what’s wrong!</div>
  <div class="tip">Write automated test scripts for complex functions.</div>
</section><section id="community-social-features">
  <h2>Community & Social Features: Chat, Teams, Friends, Groups</h2>
  <blockquote>
    Community features connect players—chat, teams, friends, and groups make games more social, collaborative, and fun!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. Chat System</strong><br>
    Roblox has a built-in chat, customizable with scripts and modules. Filter messages, create custom channels, and link chat to game events.
  </div>
  <div class="deepdive"><strong>2. Teams</strong><br>
    Use <code>Teams</code> service to split players into groups for games, competitions, or roles. Assign colors, names, and properties.
  </div>
  <div class="deepdive"><strong>3. Friends</strong><br>
    Players can friend each other. Use <code>Player:IsFriendsWith(userId)</code> to enable friend-only features or rewards.
  </div>
  <div class="deepdive"><strong>4. Groups</strong><br>
    Groups allow shared identity, ranks, and perks. Use <code>Player:IsInGroup(groupId)</code> to check membership and grant bonuses.
  </div>
  <div class="deepdive"><strong>5. Social Events & Features</strong><br>
    Script chat events, team changes, social leaderboards, and group rewards for engagement.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Chat lets players talk. Teams group players for games. Friends and groups unlock special features!</div>
  <div class="simple">Check if players are friends or in the same group for rewards.</div>
  <div class="simple">Use events to make chat and teams interactive and fun!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Listen for Chat Messages</strong>
<pre><code>game.Players.PlayerAdded:Connect(function(player)
  player.Chatted:Connect(function(msg)
    print(player.Name .. " said: " .. msg)
  end)
end)</code></pre></div>
  <div class="example"><strong>Example 2: Create a Team</strong>
<pre><code>local Teams = game:GetService("Teams")
local redTeam = Instance.new("Team")
redTeam.Name = "Red"
redTeam.TeamColor = BrickColor.new("Bright red")
redTeam.Parent = Teams</code></pre></div>
  <div class="example"><strong>Example 3: Assign Player to Team</strong>
<pre><code>player.Team = game.Teams.Red</code></pre></div>
  <div class="example"><strong>Example 4: Check if Players are Friends</strong>
<pre><code>if player1:IsFriendsWith(player2.UserId) then
  print("They are friends!")
end</code></pre></div>
  <div class="example"><strong>Example 5: Check Group Membership</strong>
<pre><code>if player:IsInGroup(1234567) then
  print("Player is in the group!")
end</code></pre></div>
  <div class="example"><strong>Example 6: Give Reward to Friends</strong>
<pre><code>if player:IsFriendsWith(other.UserId) then
  player.leaderstats.Coins.Value = player.leaderstats.Coins.Value + 50
end</code></pre></div>
  <div class="example"><strong>Example 7: Team Color Chat Filter</strong>
<pre><code>player.Chatted:Connect(function(msg)
  if player.Team then
    print(player.Team.Name .. " says: " .. msg)
  end
end)</code></pre></div>
  <div class="example"><strong>Example 8: Group Perks</strong>
<pre><code>if player:IsInGroup(groupId) then
  player.Humanoid.WalkSpeed = 32
end</code></pre></div>
  <div class="example"><strong>Example 9: Leaderboard for Teams</strong>
<pre><code>for _, team in pairs(game.Teams:GetChildren()) do
  print(team.Name, team:GetPlayers())
end</code></pre></div>
  <div class="example"><strong>Example 10: Custom Chat Command</strong>
<pre><code>player.Chatted:Connect(function(msg)
  if msg == "/dance" then
    -- trigger dance animation
  end
end)</code></pre></div>
  <div class="example"><strong>Example 11: Team Change GUI</strong>
<pre><code>changeButton.MouseButton1Click:Connect(function()
  player.Team = game.Teams.Blue
end)</code></pre></div>
  <div class="example"><strong>Example 12: Friend-Only Area</strong>
<pre><code>if player:IsFriendsWith(ownerId) then
  -- allow entry
end</code></pre></div>
  <div class="example"><strong>Example 13: Group Rank Check</strong>
<pre><code>if player:GetRankInGroup(groupId) >= 100 then
  -- special admin powers
end</code></pre></div>
  <div class="example"><strong>Example 14: Team Leaderboard</strong>
<pre><code>local scores = {}
for _, player in pairs(game.Players:GetPlayers()) do
  if player.Team then
    scores[player.Team.Name] = (scores[player.Team.Name] or 0) + player.leaderstats.Score.Value
  end
end
print(scores)</code></pre></div>
  <div class="example"><strong>Example 15: Social Event Trigger</strong>
<pre><code>game.Players.PlayerAdded:Connect(function(player)
  if player:IsInGroup(groupId) then
    game.ReplicatedStorage.GroupEvent:FireClient(player, "Welcome group member!")
  end
end)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Create two teams and assign players.<br>
    2. Give bonus coins if players are friends.<br>
    3. Unlock a power if player is in a specific group.<br>
    4. Listen for chat commands to trigger events.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use Teams for grouping players by color, role, or competition.</div>
  <div class="tip">Check <code>IsFriendsWith</code> and <code>IsInGroup</code> for social features and rewards.</div>
  <div class="tip">Script chat events for custom commands and moderation.</div>
  <div class="warning">Don’t reveal sensitive info in chat—always filter and moderate!</div>
  <div class="tip">Use events for interactive social gameplay.</div>
</section><section id="advanced-scripting-patterns">
  <h2>Advanced Scripting Patterns: Coroutines, Promises, Advanced OOP</h2>
  <blockquote>
    Advanced patterns make code powerful, flexible, and scalable. Use coroutines for multitasking, promises for async flow, and OOP for reusable objects!
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. Coroutines</strong><br>
    Coroutines let scripts run multiple tasks in parallel. Use <code>coroutine.create</code>, <code>coroutine.resume</code>, <code>coroutine.yield</code> for custom async logic.
  </div>
  <div class="deepdive"><strong>2. Promises</strong><br>
    Promises (with community modules like evaera/promise) model async operations—chain <code>:andThen()</code>, <code>:catch()</code> for clean error handling and sequencing.
  </div>
  <div class="deepdive"><strong>3. Advanced OOP</strong><br>
    Use metatables for inheritance, encapsulation, and polymorphism. Build reusable classes and objects.
  </div>
  <div class="deepdive"><strong>4. Async/Await Patterns</strong><br>
    Simulate async/await with Promises or coroutines for readable async code.
  </div>
  <div class="deepdive"><strong>5. Custom Scripting Frameworks</strong><br>
    Use frameworks like Knit, ProfileService, Rodux for scalable architecture and advanced patterns.
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Coroutines let your scripts do many things at once.</div>
  <div class="simple">Promises help with waiting for things and handling errors.</div>
  <div class="simple">Advanced OOP lets you build custom objects with smart features.</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Basic Coroutine</strong>
<pre><code>local co = coroutine.create(function()
  for i = 1, 5 do
    print("Coroutine step", i)
    coroutine.yield()
  end
end)
coroutine.resume(co)</code></pre></div>
  <div class="example"><strong>Example 2: Coroutine for Parallel Tasks</strong>
<pre><code>function runAsync()
  coroutine.wrap(function()
    wait(1)
    print("Async done!")
  end)()
end
runAsync()</code></pre></div>
  <div class="example"><strong>Example 3: Promise Example (evaera/promise)</strong>
<pre><code>local Promise = require(path.to.promise)
Promise.new(function(resolve, reject)
  wait(1)
  resolve("Done!")
end):andThen(function(result)
  print(result)
end):catch(function(err)
  warn(err)
end)</code></pre></div>
  <div class="example"><strong>Example 4: OOP Class with Metatable</strong>
<pre><code>local Class = {}
Class.__index = Class
function Class.new()
  local self = setmetatable({}, Class)
  self.value = 0
  return self
end
function Class:increment()
  self.value = self.value + 1
end
return Class</code></pre></div>
  <div class="example"><strong>Example 5: Inheritance with Metatables</strong>
<pre><code>local Animal = {}
function Animal:speak() print("Animal sound!") end
local Dog = setmetatable({}, {__index = Animal})
function Dog:speak() print("Woof!") end
Dog:speak()</code></pre></div>
  <div class="example"><strong>Example 6: Promise for Async Operation</strong>
<pre><code>Promise.new(function(resolve, reject)
  wait(2)
  resolve("Loaded!")
end):andThen(print)</code></pre></div>
  <div class="example"><strong>Example 7: Coroutine for NPC Patrol</strong>
<pre><code>local function patrol(npc)
  while true do
    -- move npc
    wait(2)
  end
end
coroutine.wrap(patrol)(npc)</code></pre></div>
  <div class="example"><strong>Example 8: Promises for DataStore</strong>
<pre><code>Promise.new(function(resolve, reject)
  local ok, data = pcall(function() return DataStore:GetAsync(key) end)
  if ok then resolve(data) else reject("Failed!") end
end):andThen(print):catch(warn)</code></pre></div>
  <div class="example"><strong>Example 9: OOP Object Usage</strong>
<pre><code>local PlayerClass = require(path.to.PlayerClass)
local player = PlayerClass.new("Ray")
player:increment()</code></pre></div>
  <div class="example"><strong>Example 10: Async/Await Simulation</strong>
<pre><code>local Promise = require(path.to.promise)
local function asyncTask()
  return Promise.new(function(resolve)
    wait(1)
    resolve("Finished!")
  end)
end
asyncTask():andThen(print)</code></pre></div>
  <div class="example"><strong>Example 11: Custom Framework (Knit)</strong>
<pre><code>local Knit = require(game:GetService("ReplicatedStorage").Knit)
Knit.Start():andThen(function()
  print("Knit started!")
end)</code></pre></div>
  <div class="example"><strong>Example 12: Parallel Coroutines</strong>
<pre><code>for i = 1, 5 do
  coroutine.wrap(function()
    wait(i)
    print("Coroutine", i, "done!")
  end)()
end</code></pre></div>
  <div class="example"><strong>Example 13: Promise Chain</strong>
<pre><code>Promise.new(function(resolve)
  resolve(1)
end):andThen(function(val)
  return val + 1
end):andThen(print)</code></pre></div>
  <div class="example"><strong>Example 14: OOP Encapsulation</strong>
<pre><code>function Class:getValue()
  return self.value
end</code></pre></div>
  <div class="example"><strong>Example 15: Promises with Error Handling</strong>
<pre><code>Promise.new(function(_, reject)
  reject("Error!")
end):catch(warn)</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Create an OOP class for an enemy.<br>
    2. Use a coroutine for a repeating patrol.<br>
    3. Use a Promise to wait for data and handle errors.<br>
    4. Chain two Promises for sequential tasks.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Use coroutines for multitasking (not too many at once!)</div>
  <div class="tip">Promises simplify complex async logic—great for DataStores or web requests.</div>
  <div class="tip">Use OOP for reusable code—classes, inheritance, and encapsulation.</div>
  <div class="warning">Don’t spawn thousands of coroutines—can lag or break your game!</div>
  <div class="tip">Frameworks help organize large games—learn and use them for big projects.</div>
</section><section id="publishing-updating">
  <h2>Publishing & Updating: Versioning, Updates, Rollback</h2>
  <blockquote>
    Publishing puts your game live! Learn best practices for updates, version control, and rollback for reliable player experiences.
  </blockquote>

  <h3>Detailed Explanations</h3>
  <div class="deepdive"><strong>1. Publishing the Game</strong><br>
    Use <code>File &gt; Publish to Roblox</code> to update your live game. Saves all changes to the cloud.
  </div>
  <div class="deepdive"><strong>2. Version History</strong><br>
    Roblox automatically tracks versions. Use <code>View &gt; Version History</code> to see previous saves.
  </div>
  <div class="deepdive"><strong>3. Rollback</strong><br>
    Restore old versions if an update causes issues. Use Version History to rollback instantly.
  </div>
  <div class="deepdive"><strong>4. Safe Updating</strong><br>
    Test updates in a private place or with test users before publishing to all players.
  </div>
  <div class="deepdive"><strong>5. Change Logs & Communication</strong><br>
    Write change logs to inform players of updates. Communicate downtime, new features, and bug fixes!
  </div>

  <h4>Simplified Explanations</h4>
  <div class="simple">Publish your game to share with everyone. Roblox keeps old versions for you.</div>
  <div class="simple">Rollback if things go wrong. Always test updates before going live.</div>
  <div class="simple">Tell players what changed—keep them informed!</div>

  <h3>15+ Script Examples</h3>
  <div class="example"><strong>Example 1: Publish Game</strong>
<pre><code>-- File > Publish to Roblox</code></pre></div>
  <div class="example"><strong>Example 2: View Version History</strong>
<pre><code>-- View > Version History in Studio</code></pre></div>
  <div class="example"><strong>Example 3: Rollback Game Version</strong>
<pre><code>-- Restore previous version from Version History</code></pre></div>
  <div class="example"><strong>Example 4: Test in Private Place</strong>
<pre><code>-- Use File > Save to Roblox As and test privately</code></pre></div>
  <div class="example"><strong>Example 5: Change Log Example</strong>
<pre><code>local changelog = [[
- Added new sword
- Fixed shop bug
- Improved performance
]]</code></pre></div>
  <div class="example"><strong>Example 6: Notify Players of Update</strong>
<pre><code>game.ReplicatedStorage.UpdateEvent:FireAllClients("New update: See changelog!")</code></pre></div>
  <div class="example"><strong>Example 7: Automated Update Message</strong>
<pre><code>game.Players.PlayerAdded:Connect(function(player)
  player:WaitForChild("PlayerGui")
  local msg = Instance.new("Message")
  msg.Text = "Welcome! Latest update: new sword added."
  msg.Parent = player.PlayerGui
end)</code></pre></div>
  <div class="example"><strong>Example 8: Test Update with Friends</strong>
<pre><code>-- Invite friends to private test place before public update</code></pre></div>
  <div class="example"><strong>Example 9: Document Update Plan</strong>
<pre><code>local updatePlan = [[
1. Add new item
2. Fix bug
3. Test changes
4. Publish live
]]</code></pre></div>
  <div class="example"><strong>Example 10: Communicate Downtime</strong>
<pre><code>game.ReplicatedStorage.UpdateEvent:FireAllClients("Server restarting for update!")</code></pre></div>
  <div class="example"><strong>Example 11: Save Backup Before Update</strong>
<pre><code>-- File > Save to File before publishing update</code></pre></div>
  <div class="example"><strong>Example 12: Restore Backup if Needed</strong>
<pre><code>-- File > Open File to restore backup</code></pre></div>
  <div class="example"><strong>Example 13: Announce Rollback</strong>
<pre><code>game.ReplicatedStorage.UpdateEvent:FireAllClients("Rollback: previous version restored!")</code></pre></div>
  <div class="example"><strong>Example 14: Track Update Version</strong>
<pre><code>local currentVersion = "v1.2.3"</code></pre></div>
  <div class="example"><strong>Example 15: Show Changelog in GUI</strong>
<pre><code>local gui = Instance.new("ScreenGui")
local label = Instance.new("TextLabel")
label.Text = changelog
label.Parent = gui
gui.Parent = player.PlayerGui</code></pre></div>

  <div class="challenge">
    <strong>Practice Challenge:</strong><br>
    1. Publish a test update in a private place.<br>
    2. Use Version History to rollback after a bug.<br>
    3. Notify all players of the latest update and changelog.<br>
    4. Create an update plan and follow it for your next release.
  </div>

  <h3>Tips and Common Mistakes</h3>
  <div class="tip">Test updates privately before going live!</div>
  <div class="tip">Use Version History for backups and rollbacks.</div>
  <div class="tip">Always communicate changes and downtime to players.</div>
  <div class="warning">Never publish major changes without testing!</div>
  <div class="tip">Keep a changelog for transparency and feedback.</div>
</section>
