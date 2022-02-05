function checklevel()
    LV = game:GetService("Players").LocalPlayer.PlayerStats.Level.Value
    if LV == 1 or LV <= 50000 then
        MON = "Pirates [Lv:15]"
        QUESTNAME = "Pirates"
    end
  end
          
spawn(function()
    while true do wait()
        checklevel()
        if not game:GetService("Players").LocalPlayer.PlayerGui.QuestGui.Enabled then
            game:GetService("ReplicatedStorage").FuncQuest:InvokeServer(QUESTNAME)
        end
        for i,v in pairs(game:GetService("Workspace").Lives:GetChildren()) do
            if v.Name == MON and v.Torso.Transparency == 0 then
               game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
                game:GetService'VirtualUser':CaptureController()
                game:GetService'VirtualUser':ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
             end
  end
     end
end)
