--for mobs location : 'game.Workspace' ,if the mobs inside folder/Model just do 'game.Workspace["filesname/Modelsname"]' find their name and location with DarkDex/DexExplorer

--for mobs name : at line 34 'if v:IsA("Model") and v.Name == "enemynames" then' ,mobs name must same with on DarkDex/DexExplorer
--if you want farm all mobs,just remove 'if v:IsA("Model") and v.Name == "enemynames" then' and 'end' under 'until v.Humanoid.Health <= 0 or getgenv().autofarm == false'
--and they must at same folders

--for distance/position and angles : CFrame.new(left/right,over/under,behind/front)
--if you want make the position to under,make (0,-5,0)
--if you want make the position to over,make (0,5,0)
--if you want make the position to behind,remove * CFrame.Angles(math.rad(-90),0,0)
















getgenv().autofarm = true --true to make it on,false to make it stop

coroutine.wrap(function()
    while wait() do
        if getgenv().autofarm == true then
            pcall(function()
                for i,v in pairs(game.Workspace:GetChildren()) do --enemy location
                    if v:IsA("Model") and v.Name == "enemynames" then --remove this if you want farm all mobs 
                        if v.Humanoid.Health > 0 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
                            repeat
                                wait()
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0,5,0) * CFrame.Angles(math.rad(-90),0,0) --distance and angles
                            until v.Humanoid.Health <= 0 or getgenv().autofarm == false
                        end
                    end
                end
            end)
        end
    end
end)()

--no clip on when you start to farm,you can remove it if you dont want use noclip
game:GetService("RunService").RenderStepped:Connect(function() 
    if autofarm == true then
        game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
    end
end)
