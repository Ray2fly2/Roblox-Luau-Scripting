<!-- The full HTML file will be too large for a single chat response, but here's a deeply expanded section for "Variables & Data Types" as a template. You can request the next section, and I'll keep building out each topic in the same exhaustive style. -->

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
</section>
