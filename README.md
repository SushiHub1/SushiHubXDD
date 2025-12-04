local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

local Window = Rayfield:CreateWindow({
   Name = "⚒️Sushi Hub⚒️",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "⚒️Sushi Hub⚒️",
   LoadingSubtitle = "by 19.blxd",
   ShowText = "⚒️Sushi Hub⚒️", -- for mobile users to unhide rayfield, change if you'd like
   Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   ToggleUIKeybind = "K", -- The keybind to toggle the UI visibility (string like "K" or Enum.KeyCode)

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "⚒️Sushi Hub⚒️"
   },

   Discord = {
      Enabled = true, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "https://discord.gg/hu43feSh2G", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "⚒️Sushi Hub⚒️ Key",
      Subtitle = "Link In discord",
      Note = "https://discord.gg/hu43feSh2G", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = false, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = true, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"https://pastebin.com/raw/FJWVwR6B"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})

local MainTab = Window:CreateTab("🏡Home", nil) -- Title, Image
local MainSection = MainTab:CreateSection("Main")

Rayfield:Notify({
   Title = "Du Hast das script erfolgreich ausgeführt!",
   Content = "Viel Spaß damit",
   Duration = 5,
   Image = nil,
})

local Button = MainTab:CreateButton({
   Name = "Noclip",
   Callback = function()
   loadstring(game:HttpGet("https://pastebin.com/raw/2JZWpiKn", true))()
   end,
})

local Slider = MainTab:CreateSlider({
   Name = "WalkSpeed",
   Range = {0, 1000},
   Increment = 1,
   Suffix = "Speed",
   CurrentValue = 16,
   Flag = "Slider1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
           game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = (Value)
   end,
})
local Input = MainTab:CreateInput({
   Name = "JumpPower",
   CurrentValue = "",
   PlaceholderText = "1-10000r",
   RemoveTextAfterFocusLost = true,
   Flag = "Input1",
   Callback = function(Text)
           game.Players.LocalPlayer.Character.Humanoid.JumpPower =(Text)
   end,
})

local Button = MainTab:CreateButton({
   Name = "Fly",
   Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Hotdog120823/FlyGuiV5/refs/heads/main/FlyGui"))()
   end,
})
