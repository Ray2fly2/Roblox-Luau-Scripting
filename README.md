<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  VARIABLES
</h2>
<pre>
-- This is a VARIABLE
local Variable = "Hello!" -- Stores strings (text), numbers, booleans, tables, etc.
-- You can name variables almost anything except Lua keywords (like 'if', 'end')

print(Variable) -- prints "Hello!"

print("test") -- prints "test"
warn("test") -- prints warning "test" in yellow

-- Numbers
local Number = 5
print(Number + 3) -- 8
print(Number - 2) -- 3
print(Number * 4) -- 20
print(Number / 2) -- 2.5

-- Strings
local Name = "Ray"
print("Hello, "..Name) -- concatenates and prints "Hello, Ray"

-- Booleans
local isTrue = true
print(isTrue) -- prints true
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  IF STATEMENTS
</h2>
<pre>
local age = 16

if age >= 18 then
    print("You are an adult")
else
    print("You are a minor")
end
-- Checks if age is 18 or older and prints accordingly
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  FUNCTIONS
</h2>
<pre>
function Greet()
    print("Hi there!")
end

Greet() -- Calls the function, prints "Hi there!"

-- Functions with parameters
function SayHi(name)
    print("Hi, "..name)
end

SayHi("Ray") -- prints "Hi, Ray"
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  LOOPS
</h2>
<pre>
-- For loop (runs 5 times)
for i = 1,5 do
    print(i) -- prints 1 2 3 4 5
end

-- While loop
local count = 1
while count <= 3 do
    print("Counting "..count)
    count = count + 1
end
-- Prints Counting 1, Counting 2, Counting 3

-- Repeat until loop
local num = 1
repeat
    print("Number is "..num)
    num = num + 1
until num > 3
-- Prints Number is 1, 2, 3
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  TABLES
</h2>
<pre>
local Fruits = {"Apple","Banana","Orange"} -- List of fruits
print(Fruits[1]) -- prints "Apple" (Lua tables start at 1)

-- Tables as dictionaries
local player = {Name="Ray", Age=16}
print(player.Name) -- prints "Ray"
print(player["Age"]) -- prints 16
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  EVENTS (ROBLOX SPECIFIC)
</h2>
<pre>
local part = workspace.Part

part.Touched:Connect(function(hit)
    print(hit.Name.." touched the part")
end)
-- When something touches 'part', prints what touched it
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  FINDFIRSTCHILD
</h2>
<pre>
local character = hit.Parent -- The object that touched something
local humanoid = character:FindFirstChild("Humanoid") -- Checks if it has a Humanoid

if humanoid then -- If yes, it's a player or NPC
    print("It's a player or NPC")
end
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  REMOTEEVENTS (CLIENT ⇄ SERVER COMMUNICATION)
</h2>
<pre>
-- SERVER SCRIPT
local event = game.ReplicatedStorage.MyEvent

event.OnServerEvent:Connect(function(player, msg)
    print(player.Name.." says "..msg)
end)

-- LOCAL SCRIPT
local event = game.ReplicatedStorage.MyEvent

event:FireServer("Hello Server") -- Sends message to server
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  REMOTEFUNCTIONS (REQUEST & RESPONSE)
</h2>
<pre>
-- SERVER SCRIPT
local func = game.ReplicatedStorage.MyFunction

func.OnServerInvoke = function(player, msg)
    print(player.Name.." asked: "..msg)
    return "Hello from server"
end

-- LOCAL SCRIPT
local func = game.ReplicatedStorage.MyFunction

local reply = func:InvokeServer("Hello Server")
print(reply) -- prints "Hello from server"
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  PCALL (SAFE CODE EXECUTION)
</h2>
<pre>
local success, result = pcall(function()
    return "safe code"
end)

if success then
    print(result) -- prints "safe code"
else
    warn("Error happened")
end
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  INSTANCE.NEW (CREATE OBJECTS)
</h2>
<pre>
local part = Instance.new("Part") -- creates a new part
part.Parent = workspace -- puts it in the world
part.Position = Vector3.new(0,10,0) -- sets position
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  VALUE OBJECTS (STORE VALUES IN GAME)
</h2>
<pre>
local coins = Instance.new("IntValue")
coins.Name = "Coins"
coins.Value = 30
coins.Parent = game.Players.Player1
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  TWEENSERVICE (SMOOTH ANIMATIONS)
</h2>
<pre>
local TweenService = game:GetService("TweenService")
local info = TweenInfo.new(2) -- duration: 2 seconds
local goal = {Transparency = 1} -- target properties

local tween = TweenService:Create(part, info, goal)
tween:Play() -- smoothly fades the part out
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  CONTEXTACTIONSERVICE (CUSTOM CONTROLS)
</h2>
<pre>
local CAS = game:GetService("ContextActionService")

local function onAction(actionName, inputState, inputObj)
    if inputState == Enum.UserInputState.Begin then
        print("Button pressed")
    end
end

CAS:BindAction("JumpButton", onAction, true, Enum.KeyCode.Space)
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  PATHFINDINGSERVICE (NPC AI MOVEMENT)
</h2>
<pre>
local PathfindingService = game:GetService("PathfindingService")
local path = PathfindingService:CreatePath()
path:ComputeAsync(npc.Position, target.Position)
path:MoveTo(npc)
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  MARKETPLACESERVICE (DEV PRODUCTS & GAME PASSES)
</h2>
<pre>
local MarketplaceService = game:GetService("MarketplaceService")
MarketplaceService:PromptProductPurchase(player, productId) -- prompts player to buy developer product
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  MODULESCRIPTS (REUSABLE CODE)
</h2>
<pre>
-- Module script (in ReplicatedStorage)
local module = {}

function module.SayHi()
    print("Hi from module!")
end

return module

-- Using the module
local myModule = require(game.ReplicatedStorage.MyModule)
myModule.SayHi()
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  OOP (OBJECT ORIENTED PROGRAMMING)
</h2>
<pre>
local Dog = {}
Dog.__index = Dog

function Dog.new(name)
    local self = setmetatable({}, Dog)
    self.Name = name
    return self
end

function Dog:Bark()
    print(self.Name.." barks!")
end

local myDog = Dog.new("Rex")
myDog:Bark()
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  HUMANOID STATES (DETECT CHANGES)
</h2>
<pre>
local humanoid = workspace.Player.Character:WaitForChild("Humanoid")
humanoid.StateChanged:Connect(function(old,new)
    print("Changed from "..old.Name.." to "..new.Name)
end)
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  COLLECTIONSERVICE (TAGGING OBJECTS)
</h2>
<pre>
local CollectionService = game:GetService("CollectionService")
local taggedParts = CollectionService:GetTagged("BouncePad")
for _, part in pairs(taggedParts) do
    print(part.Name.." is a bounce pad")
end

CollectionService:AddTag(workspace.Part, "BouncePad") -- adds a tag
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  COLLISION GROUPS
</h2>
<pre>
local PhysicsService = game:GetService("PhysicsService")
PhysicsService:CreateCollisionGroup("Ghosts")
PhysicsService:SetPartCollisionGroup(workspace.Part, "Ghosts")
PhysicsService:CollisionGroupSetCollidable("Ghosts", "Default", false)
-- This makes "Ghosts" not collide with default objects
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  ATTRIBUTES (CUSTOM PROPERTIES)
</h2>
<pre>
local part = workspace.Part
part:SetAttribute("Health", 100) -- set custom attribute
print(part:GetAttribute("Health")) -- get it

part.AttributeChanged:Connect(function(attr)
    print(attr.." changed to "..part:GetAttribute(attr))
end)
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  MATH LIBRARY
</h2>
<pre>
print(math.random(1,10)) -- random number 1-10
print(math.floor(5.8)) -- 5
print(math.ceil(5.2)) -- 6
print(math.abs(-7)) -- 7
print(math.sqrt(16)) -- 4
print(math.pi) -- 3.1415...
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  DEBUG LIBRARY
</h2>
<pre>
local function myFunction()
    print(debug.traceback("Here is the traceback"))
end
myFunction()
</pre>

<h2 style="text-transform: uppercase; border-bottom: 2px solid #444; padding-bottom: 6px; margin-top: 30px;">
  ENUMS
</h2>
<pre>
local part = workspace.Part
part.Material = Enum.Material.Neon
print(Enum.Material.Neon.Name) -- prints Neon
</pre>
