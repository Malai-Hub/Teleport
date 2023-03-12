local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Teleport Troll (Cr. Malai Hub)", "DarkTheme")
local Tab = Window:NewTab("Players")
local Section = Tab:NewSection("Teleport")
Plr = {}
for i,v in pairs(game:GetService("Players"):GetChildren()) do
    table.insert(Plr,v.Name) 
end
Section:NewDropdown("Select Player", "",Plr, function(t)
    PlayerTP = t
end)

Section:NewToggle("Teleport", "", function(t)
	_G.TelePort = t
end)



spawn(function()
  while wait() do
    if _G.TelePort then
      game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[PlayerTP].Character.HumanoidRootPart.CFrame
    end
  end
end)
