

(getgenv()).Config = {

 ["FastAttack"] = true,

 ["ClickAttack"] = true

} 

coroutine.wrap(function()

local StopCamera = require(game.ReplicatedStorage.Util.CameraShaker)StopCamera:Stop()

    for v,v in pairs(getreg()) do

        if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework then

             for v,v in pairs(debug.getupvalues(v)) do

                if typeof(v) == "table" then

                    spawn(function()

                        game:GetService("RunService").RenderStepped:Connect(function()

                            if getgenv().Config['FastAttack'] then

                                 pcall(function()

                                     v.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)

                                     v.activeController.attacking = false

                                     v.activeController.increment = 2

                                     v.activeController.blocking = false   

                                     v.activeController.hitboxMagnitude = 500

                               v.activeController.humanoid.AutoRotate = true

                                 v.activeController.focusStart = 0.2

                                 v.activeController.currentAttackTrack = 0.2

                                     sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRaxNerous", math.huge)

                                 end)

                             end

                         end)

                    end)

                end

            end

        end

    end

end)();

spawn(function()

    game:GetService("RunService").RenderStepped:Connect(function()

        if getgenv().Config['ClickAttack'] then

             pcall(function()

                game:GetService'VirtualUser':CaptureController()

       game:GetService'VirtualUser':Button1Down(Vector2.new(0,1,0,1))

            end)

        end

    end)

end)

local Flux = loadstring(game:HttpGet"https://raw.githubusercontent.com/dawid-scripts/UI-Libs/main/fluxlib.txt")()

local win = Flux:Window("RIPPR HUB", "Baseplate", Color3.fromRGB(1,0,0), Enum.KeyCode.LeftControl)

local tab = win:Tab("Tab 1", "rbxassetid://13423880248")

tab:Toggle("AUTOFARM", "NuwScr", function(t)

print(t)

end)
