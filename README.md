<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Roblox Luau Scripting Encyclopedia</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: #121212;
    color: #eee;
    margin: 0;
    display: flex;
    height: 100vh;
  }
  #sidebar {
    width: 280px;
    background: #1e1e1e;
    overflow-y: auto;
    padding: 20px;
    box-sizing: border-box;
    border-right: 2px solid #333;
  }
  #sidebar h2 {
    margin-top: 0;
    font-size: 1.2rem;
    text-transform: uppercase;
    color: #4caf50;
  }
  #sidebar button {
    width: 100%;
    margin: 6px 0;
    background: #333;
    border: none;
    padding: 10px 15px;
    color: #eee;
    font-weight: bold;
    cursor: pointer;
    border-radius: 5px;
    text-align: left;
    text-transform: uppercase;
    transition: background 0.3s ease;
  }
  #sidebar button:hover, #sidebar button.active {
    background: #4caf50;
    color: #121212;
  }
  #content {
    flex: 1;
    padding: 30px 40px;
    overflow-y: auto;
    background: #181818;
  }
  h1, h2, h3 {
    text-transform: uppercase;
    color: #4caf50;
    margin-top: 1.6rem;
    margin-bottom: 0.8rem;
  }
  pre {
    background: #222;
    border-radius: 8px;
    padding: 20px;
    overflow-x: auto;
    font-size: 0.9rem;
    line-height: 1.5;
    color: #cfd8dc;
  }
  p {
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: 1.3rem;
  }
  code {
    background: #333;
    padding: 2px 5px;
    border-radius: 3px;
    font-family: Consolas, monospace;
  }
</style>
</head>
<body>
  <nav id="sidebar">
    <h2>Roblox Luau Topics</h2>
    <button onclick="showTopic('variables')">Variables</button>
    <button onclick="showTopic('printing')">Printing & Operators</button>
    <button onclick="showTopic('ifstatements')">If Statements</button>
    <button onclick="showTopic('loops')">Loops</button>
    <button onclick="showTopic('functions')">Functions</button>
    <button onclick="showTopic('tables')">Tables</button>
    <button onclick="showTopic('events')">Events (Roblox)</button>
    <button onclick="showTopic('remotes')">RemoteEvents & RemoteFunctions</button>
    <button onclick="showTopic('modules')">ModuleScripts & OOP</button>
    <button onclick="showTopic('tweenservice')">TweenService & Animations</button>
    <button onclick="showTopic('contextaction')">ContextActionService</button>
    <button onclick="showTopic('pathfinding')">PathfindingService</button>
    <button onclick="showTopic('marketplace')">MarketplaceService</button>
    <button onclick="showTopic('userdata')">User Data & DataStores</button>
  </nav>

  <main id="content">
    <h1>Roblox Luau Scripting Encyclopedia</h1>
    <p>Select a topic from the sidebar to get started.</p>
  </main>

<script>
const topics = {
  variables: `
<h2>VARIABLES</h2>
<p>Variables are like labeled boxes where you can store different types of data: numbers, text, true/false values, tables (arrays/dictionaries), and more. In Luau, variables are created using the <code>local</code> keyword to limit their scope to where they’re defined.</p>

<p>Variables allow you to save data for later use in your scripts. You can change the contents of variables, use them in calculations, or print them out for debugging.</p>

<p>Example:</p>

<pre><code>-- Create a variable storing a number
local playerScore = 0

-- Create a variable storing text
local playerName = "Ray"

-- Update the score
playerScore = playerScore + 10

-- Print the player's name and score
print("Player: " .. playerName .. " Score: " .. playerScore)
</code></pre>

<p>In this example, <code>playerScore</code> starts at zero and then increases by 10. We then print a message showing the player's name and score by combining strings with the <code>..</code> operator.</p>

<p>Variables are fundamental for keeping track of game data like health, coins, player names, and much more.</p>
`,

  printing: `
<h2>PRINTING & OPERATORS</h2>
<p>Printing is how you output messages to Roblox Studio’s output window, which helps debug your scripts. You use <code>print()</code> to show simple messages, and <code>warn()</code> to output warnings in yellow.</p>

<p>Operators let you do math and combine values. Common operators include:</p>
<ul>
  <li><code>+</code> Addition</li>
  <li><code>-</code> Subtraction</li>
  <li><code>*</code> Multiplication</li>
  <li><code>/</code> Division</li>
  <li><code>^</code> Power (exponent)</li>
  <li><code>%</code> Modulus (remainder)</li>
  <li><code>..</code> String concatenation</li>
</ul>

<p>Example script:</p>

<pre><code>local a = 7
local b = 3

print("Add: " .. (a + b))       -- prints 10
print("Subtract: " .. (a - b))  -- prints 4
print("Multiply: " .. (a * b))  -- prints 21
print("Divide: " .. (a / b))    -- prints 2.3333...
print("Power: " .. (a ^ b))     -- prints 343 (7^3)
print("Remainder: " .. (a % b)) -- prints 1 (7 mod 3)

print("Hello " .. "World")      -- prints Hello World

warn("This is a warning!")      -- prints warning message in yellow
</code></pre>

<p>Use printing to check values during development and operators to perform math or combine strings.</p>
`,

  ifstatements: `
<h2>IF STATEMENTS</h2>
<p>If statements let your code make decisions based on conditions. They check whether something is true or false and run code accordingly.</p>

<p>Example:</p>

<pre><code>local health = 75

if health > 50 then
    print("You are healthy!")
elseif health > 20 then
    print("You are injured!")
else
    print("You are critically low on health!")
end
</code></pre>

<p>This checks the player’s health and prints a different message depending on how much health remains.</p>

<p>You can combine conditions using <code>and</code>, <code>or</code>, and negate them with <code>not</code> for complex logic.</p>

<p>Example with combined conditions:</p>

<pre><code>local isAdmin = true
local isOnline = false

if isAdmin and isOnline then
    print("Welcome, admin!")
elseif isAdmin and not isOnline then
    print("Admin is offline")
else
    print("You are a guest")
end
</code></pre>
`,

  loops: `
<h2>LOOPS</h2>
<p>Loops let you run a block of code multiple times, which is great for repeating actions like updating game states or checking conditions repeatedly.</p>

<p>There are three common loops in Luau:</p>
<ul>
  <li><strong>For loops:</strong> Repeat a fixed number of times.</li>
  <li><strong>While loops:</strong> Repeat while a condition is true.</li>
  <li><strong>Repeat until loops:</strong> Repeat until a condition becomes true.</li>
</ul>

<p>Examples:</p>

<pre><code>-- For loop that counts from 1 to 5
for i = 1, 5 do
    print("Count: " .. i)
end

-- While loop that runs while count is less than 3
local count = 0
while count < 3 do
    print("While loop count: " .. count)
    count = count + 1
end

-- Repeat until loop that runs until count is 3 or more
local count2 = 0
repeat
    print("Repeat until count: " .. count2)
    count2 = count2 + 1
until count2 >= 3
</code></pre>

<p>Loops are essential for repetitive game logic like spawning enemies, updating scores, or creating timers.</p>
`,

  functions: `
<h2>FUNCTIONS</h2>
<p>Functions are reusable blocks of code that can be called multiple times. They help organize your code into smaller pieces and allow you to pass in values (parameters) and get back results.</p>

<p>Example of a simple function without parameters:</p>

<pre><code>function greet()
    print("Hello, player!")
end

greet() -- Calls the function and prints the message
</code></pre>

<p>Example of a function with parameters:</p>

<pre><code>function greetPlayer(name)
    print("Hello, " .. name .. "!")
end

greetPlayer("Ray") -- Prints Hello, Ray!
</code></pre>

<p>Functions can return values:</p>

<pre><code>function add(a, b)
    return a + b
end

local result = add(5, 3)
print("Sum: " .. result) -- prints Sum: 8
</code></pre>

<p>Functions help keep your code clean, reusable, and easier to manage, especially in big projects.</p>
`,

  tables: `
<h2>TABLES</h2>
<p>Tables are one of the most powerful data structures in Luau. They work like arrays or dictionaries and can hold many values, including other tables.</p>

<p>Example of an array-style table:</p>

<pre><code>local fruits = {"Apple", "Banana", "Orange"}

print(fruits[1]) -- prints Apple (Lua tables are 1-indexed)
print(fruits[2]) -- prints Banana
</code></pre>

<p>Example of a dictionary-style table with key-value pairs:</p>

<pre><code>local player = {
    Name = "Ray",
    Score = 120,
    IsAdmin = true
}

print(player.Name) -- prints Ray
print(player["Score"]) -- prints 120
</code></pre>

<p>Tables can store anything, and you can loop through them with <code>pairs()</code> or <code>ipairs()</code>.</p>

<p>Example looping through a table:</p>

<pre><code>for index, fruit in ipairs(fruits) do
    print(index, fruit)
end
</code></pre>

<p>Tables are used everywhere in Roblox scripting to store collections of data like inventories, player stats, or game settings.</p>
`,

  events: `
<h2>EVENTS (ROBLOX SPECIFIC)</h2>
<p>Events allow your scripts to respond to things happening in the game, such as players touching parts, joining, leaving, or other custom triggers.</p>

<p>Example of the <code>Touched</code> event on a part:</p>

<pre><code>local part = workspace.Part

part.Touched:Connect(function(hit)
    print(hit.Name .. " touched the part!")
end)
</code></pre>

<p>This script prints the name of any object that touches the part. Useful for creating traps, pickups, or interactive objects.</p>

<p>Other common events include <code>PlayerAdded</code> (when a player joins), <code>Changed</code> (when a property changes), and many more.</p>

<p>You can connect functions to these events to run your code automatically when something happens.</p>
`,

  remotes: `
<h2>REMOTE EVENTS & REMOTE FUNCTIONS</h2>
<p>RemoteEvents and RemoteFunctions let the client (player's device) and the server communicate safely. This is crucial because some code must run on the server (for security), and some code runs on the client (for UI and controls).</p>

<p><strong>RemoteEvent:</strong> Used to send messages from client to server or vice versa.</p>

<pre><code>-- Server Script:
local event = game.ReplicatedStorage.MyEvent

event.OnServerEvent:Connect(function(player, message)
    print(player.Name .. " says: " .. message)
end)

-- LocalScript (Client):
local event = game.ReplicatedStorage.MyEvent
event:FireServer("Hello Server!")
</code></pre>

<p><strong>RemoteFunction:</strong> Used when the client needs to ask the server for information and wait for a reply.</p>

<pre><code>-- Server Script:
local func = game.ReplicatedStorage.MyFunction

func.OnServerInvoke = function(player, query)
    if query == "GetCoins" then
        return 100 -- example coin count
    else
        return "Unknown query"
    end
end

-- LocalScript (Client):
local func = game.ReplicatedStorage.MyFunction
local coins = func:InvokeServer("GetCoins")
print("You have " .. coins .. " coins.")
</code></pre>

<p>Using remotes properly helps secure your game and lets you sync data between server and client.</p>
`,

  modules: `
<h2>MODULESCRIPTS & OBJECT-ORIENTED PROGRAMMING (OOP)</h2>
<p>ModuleScripts let you write reusable code that can be used in many places without rewriting. They are perfect for organizing big projects by separating functionality into different modules.</p>

<p>Example of a simple ModuleScript named <code>MathModule</code>:</p>

<pre><code>-- MathModule
local MathModule = {}

function MathModule.Add(a, b)
    return a + b
end

function MathModule.Multiply(a, b)
    return a * b
end

return MathModule
</code></pre>

<p>You can use it in other scripts like this:</p>

<pre><code>local Math = require(game.ReplicatedStorage.MathModule)

print(Math.Add(5, 7))      -- prints 12
print(Math.Multiply(3, 4)) -- prints 12
</code></pre>

<p>OOP is a style of programming where you create 'classes' and 'objects' to represent real-world entities or game systems. Roblox Luau supports this using metatables.</p>

<p>Example of a basic class-like structure:</p>

<pre><code>local Dog = {}
Dog.__index = Dog

function Dog.new(name)
    local self = setmetatable({}, Dog)
    self.Name = name
    return self
end

function Dog:Bark()
    print(self.Name .. " says: Woof!")
end

local myDog = Dog.new("Rex")
myDog:Bark() -- prints "Rex says: Woof!"
</code></pre>

<p>Using ModuleScripts and OOP keeps your code clean, reusable, and easier to manage.</p>
`,

  tweenservice: `
<h2>TWEENSERVICE & ANIMATIONS</h2>
<p>TweenService is used to create smooth, animated transitions for parts, UI elements, and properties. Instead of instantly changing a property, tweening animates the change over time.</p>

<p>Example: smoothly fading out a part's transparency over 2 seconds.</p>

<pre><code>local TweenService = game:GetService("TweenService")
local part = workspace.Part

local tweenInfo = TweenInfo.new(
    2, -- Duration (seconds)
    Enum.EasingStyle.Quad,
    Enum.EasingDirection.Out
)

local goal = {}
goal.Transparency = 1 -- fade out

local tween = TweenService:Create(part, tweenInfo, goal)
tween:Play()
</code></pre>

<p>Tweens can be used for many cool effects like UI fades, moving platforms, scaling objects, and more.</p>

<p>You can customize tween duration, easing styles (how the animation accelerates or decelerates), and repeat counts.</p>
`,

  contextaction: `
<h2>CONTEXTACTIONSERVICE</h2>
<p>ContextActionService lets you bind functions to player inputs like keyboard, mouse, or gamepad buttons. This is great for custom controls, shortcuts, or game mechanics.</p>

<p>Example: bind the space bar to print a jump message.</p>

<pre><code>local CAS = game:GetService("ContextActionService")

local function onJumpAction(actionName, inputState, inputObject)
    if inputState == Enum.UserInputState.Begin then
        print("Jump button pressed!")
    end
end

CAS:BindAction("JumpAction", onJumpAction, false, Enum.KeyCode.Space)
</code></pre>

<p>This script prints "Jump button pressed!" when the spacebar is pressed.</p>

<p>You can bind multiple keys or buttons, disable bindings temporarily, and manage complex input schemes using ContextActionService.</p>
`,

  pathfinding: `
<h2>PATHFINDINGSERVICE</h2>
<p>PathfindingService helps NPCs move around obstacles by calculating a path between two points.</p>

<p>Example of making an NPC move to a target using pathfinding:</p>

<pre><code>local PathfindingService = game:GetService("PathfindingService")
local npc = workspace.NPC
local target = workspace.Target.Position

local path = PathfindingService:CreatePath()
path:ComputeAsync(npc.Position, target)

if path.Status == Enum.PathStatus.Success then
    local waypoints = path:GetWaypoints()
    for _, waypoint in ipairs(waypoints) do
        npc.Humanoid:MoveTo(waypoint.Position)
        npc.Humanoid.MoveToFinished:Wait()
    end
else
    print("No path found!")
end
</code></pre>

<p>This script calculates a path for the NPC and moves it step by step along the waypoints.</p>

<p>Pathfinding is essential for creating smart NPCs that navigate the world naturally.</p>
`,

  marketplace: `
<h2>MARKETPLACESERVICE</h2>
<p>MarketplaceService lets you integrate developer products, game passes, and other Roblox purchases into your game.</p>

<p>Example: prompting a player to buy a developer product (like coins or special items):</p>

<pre><code>local MarketplaceService = game:GetService("MarketplaceService")
local productId = 12345678 -- replace with your product ID

game.Players.PlayerAdded:Connect(function(player)
    MarketplaceService:PromptProductPurchase(player, productId)
end)
</code></pre>

<p>This shows the purchase dialog to players when they join.</p>

<p>You can handle purchase processing and rewards by listening to purchase events.</p>
`,

  userdata: `
<h2>USER DATA & DATASTORES</h2>
<p>Saving player data (like coins, stats, inventory) is crucial for long-term games. Roblox provides DataStores to save persistent data on Roblox’s servers.</p>

<p>Example: simple DataStore to save and load a player's coin count.</p>

<pre><code>local DataStoreService = game:GetService("DataStoreService")
local coinsStore = DataStoreService:GetDataStore("PlayerCoins")

game.Players.PlayerAdded:Connect(function(player)
    local userId = player.UserId

    -- Load coins safely
    local success, coins = pcall(function()
        return coinsStore:GetAsync(userId)
    end)

    if success and coins then
        player:SetAttribute("Coins", coins)
        print("Loaded coins for " .. player.Name .. ": " .. coins)
    else
        player:SetAttribute("Coins", 0)
    end
end)

game.Players.PlayerRemoving:Connect(function(player)
    local userId = player.UserId
    local coins = player:GetAttribute("Coins")

    -- Save coins safely
    pcall(function()
        coinsStore:SetAsync(userId, coins)
    end)
end)
</code></pre>

<p>This script loads coins when players join and saves them when they leave, handling errors with <code>pcall</code>.</p>

<p>Data persistence is complex and requires care to avoid data loss or corruption.</p>
`
};

function showTopic(topic) {
  const content = topics[topic];
  if (!content) {
    document.getElementById('content').innerHTML = '<p>Topic not found.</p>';
    return;
  }
  document.getElementById('content').innerHTML = content;

  // Update active button
  const buttons = document.querySelectorAll('#sidebar button');
  buttons.forEach(btn => btn.classList.remove('active'));
  const activeBtn = Array.from(buttons).find(b => b.textContent.toLowerCase().replace(/ /g, '') === topic);
  if (activeBtn) activeBtn.classList.add('active');
}

// Initialize to variables on page load
showTopic('variables');
</script>
</body>
</html>
