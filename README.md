local CoreGui = game:GetService("StarterGui")
local Players = game:GetService("Players")

getgenv().HitboxSize = 15
getgenv().HitboxTransparency = 0

getgenv().HitboxStatus = false
getgenv().TeamCheck = false
getgenv().FriendCheck = false

getgenv().Walkspeed = 16
getgenv().Jumppower = 50

--// UI

local Rayfield = loadstring(game:HttpGet('https://[Log in to view URL]'))()

local Window = Rayfield:CreateWindow({
   Name = "Muscle legends Script V2",
   LoadingTitle = "Beamed ",
   LoadingSubtitle = "by ben1x1x1x1x",
   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "ben1x1x1x1x hub v2.lua"
   },
   Discord = {
      Enabled = false,
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },
   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided",
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local MainTab = Window:CreateTab("Combat", nil) -- Title, Image
local MainSection = MainTab:CreateSection("Main")

local Slider = MainTab:CreateSlider({
   Name = "Kill aura Range",
   Range = {0, 500},
   Increment = 1,
   Suffix = "Kill aura",
   CurrentValue = 15,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
    getgenv().HitboxSize = value
end)
