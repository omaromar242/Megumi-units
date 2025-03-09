 -- Initial spawn of the first tower
local args = {
    [1] = "fa609078-baec-4a98-b15d-e7dba01d8e57",
    [2] = CFrame.new(33.8105392, 8.50992775, -151.300278, -0.0192896146, -0, -0.999813974, -0, 1.00000012, -0, 0.999813974, 0, -0.0192896146) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
}
game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(args))

-- Check every 5 seconds if any part of the EndScreen is visible, and teleport if visible
while true do
    wait(5)
    local player = game:GetService("Players").LocalPlayer
    local endScreen = player.PlayerGui.GameGui:FindFirstChild("EndScreen")
    if endScreen and endScreen.Visible then
        game:GetService("TeleportService"):Teleport(17720162456, player)
        break
    end
end

-- Function to check Money and spawn other towers
local function checkMoneyAndSpawnTowers()
    local player = game:GetService("Players").LocalPlayer
    local leaderstats = player:WaitForChild("leaderstats")
    local money = leaderstats:WaitForChild("Money")

    -- Wait until Money reaches 400
    while money.Value < 400 do
        wait(1)
    end

    -- Once Money reaches 400, spawn the additional towers
    local spawnArgs1 = {
        [1] = "9f7ab22e-1667-4f45-a806-18afdde643df",
        [2] = CFrame.new(5.72673798, 8.51061249, -137.76712, -1, 0, 0, 0, 1, 0, 0, 0, -1) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }
    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(spawnArgs1))

    local spawnArgs2 = {
        [1] = "9f7ab22e-1667-4f45-a806-18afdde643df",
        [2] = CFrame.new(6.21704865, 8.51061249, -132.107239, -1, 0, 0, 0, 1, 0, 0, 0, -1) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }
    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(spawnArgs2))

    local spawnArgs3 = {
        [1] = "9f7ab22e-1667-4f45-a806-18afdde643df",
        [2] = CFrame.new(5.87857819, 8.51061249, -126.92337, -1, 0, 0, 0, 1, 0, 0, 0, -1) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }
    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(spawnArgs3))

    local spawnArgs4 = {
        [1] = "9f7ab22e-1667-4f45-a806-18afdde643df",
        [2] = CFrame.new(5.90122986, 8.51061249, -123.231895, -1, 0, 0, 0, 1, 0, 0, 0, -1) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }
    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(spawnArgs4))

    -- Wait until Money reaches 1400
    while money.Value < 1400 do
        wait(1)
    end

    -- Once Money reaches 1400, spawn the final tower
    local spawnArgs5 = {
        [1] = "304c85da-e481-4573-ba5b-96b9fef23cc3",
        [2] = CFrame.new(48.2543221, 8.55292702, -144.030334, 0.684781134, 0, -0.728748798, -0, 1, -0, 0.728748858, 0, 0.684781075) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }
    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(spawnArgs5))

    -- Wait until Money reaches 800 and then upgrade towers 4 times
    while money.Value < 800 do
        wait(1)
    end

    -- Run the upgrade tower function 4 times
    for i = 1, 4 do
        local upgradeArgs = {
            [1] = workspace.Towers.SorcererAgent
        }
        game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs))
    end

    -- Wait until Money reaches 2500 and then upgrade towers 4 times for SorcererAgent2
    while money.Value < 2500 do
        wait(1)
    end

    -- Run the upgrade tower function 4 times for SorcererAgent2
    for i = 1, 4 do
        local upgradeArgs2 = {
            [1] = workspace.Towers.SorcererAgent2
        }
        game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs2))
    end

    -- Wait until Money reaches 1100 and then spawn the next tower
    while money.Value < 1100 do
        wait(1)
    end

    -- Once Money reaches 1100, spawn the specified tower
    local spawnArgs6 = {
        [1] = "7723dcba-7ffe-4a32-a8a5-9e3d1ef331de",
        [2] = CFrame.new(40.0208664, 8.50992775, -152.431061, -1, 0, 0, 0, 1, 0, 0, 0, -1) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }
    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(spawnArgs6))

    -- Wait until Money reaches 3200 and then upgrade towers 4 times for SorcererAgent3
    while money.Value < 3200 do
        wait(1)
    end

    -- Run the upgrade tower function 4 times for SorcererAgent3
    for i = 1, 4 do
        local upgradeArgs3 = {
            [1] = workspace.Towers.SorcererAgent3
        }
        game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs3))
    end

    -- Wait until Money reaches 6000 and then upgrade the SoulCurseAwk tower
    while money.Value < 6000 do
        wait(1)
    end

    -- Upgrade the SoulCurseAwk tower
    local upgradeArgs4 = {
        [1] = workspace.Towers.SoulCurseAwk
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs4))

    -- Wait until Money reaches 8200 and then upgrade the KingOfCurses tower
    while money.Value < 8200 do
        wait(1)
    end

    -- Upgrade the KingOfCurses tower
    local upgradeArgs5 = {
        [1] = workspace.Towers.KingOfCurses
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs5))

    -- Wait until Money reaches 16000 and then upgrade towers 4 times for SorcererAgent4
    while money.Value < 16000 do
        wait(1)
    end

    -- Run the upgrade tower function 4 times for SorcererAgent4
    for i = 1, 4 do
        local upgradeArgs6 = {
            [1] = workspace.Towers.SorcererAgent4
        }
        game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs6))
    end

    -- Wait until Money reaches 15600 and then upgrade KingOfCurses2
    while money.Value < 15600 do
        wait(1)
    end

    -- Upgrade KingOfCurses2
    local upgradeArgs7 = {
        [1] = workspace.Towers.KingOfCurses2
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs7))

    -- Wait until Money reaches 28700 and then upgrade KingOfCurses3
    while money.Value < 28700 do
        wait(1)
    end

    -- Upgrade KingOfCurses3
    local upgradeArgs8 = {
        [1] = workspace.Towers.KingOfCurses3
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs8))

    -- Wait until Money reaches 13200 and then upgrade SoulCurseAwk2
    while money.Value < 13200 do
        wait(1)
    end

    -- Upgrade SoulCurseAwk2
    local upgradeArgs9 = {
        [1] = workspace.Towers.SoulCurseAwk2
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs9))

    -- Wait until Money reaches 42200 and then upgrade KingOfCurses4
    while money.Value < 42200 do
        wait(1)
    end

    -- Upgrade KingOfCurses4
    local upgradeArgs10 = {
        [1] = workspace.Towers.KingOfCurses4
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs10))

    -- Wait until Money reaches 22600 and then upgrade SoulCurseAwk3
    while money.Value < 22600 do
        wait(1)
    end

    -- Upgrade SoulCurseAwk3
    local upgradeArgs11 = {
        [1] = workspace.Towers.SoulCurseAwk3
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs11))

    -- Wait until Money reaches 42100 and then upgrade SoulCurseAwk4
    while money.Value < 42100 do
        wait(1)
    end

    -- Upgrade SoulCurseAwk4
    local upgradeArgs12 = {
        [1] = workspace.Towers.SoulCurseAwk4
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs12))

    -- Wait until Money reaches 79000 and then upgrade SoulCurseAwk5
    while money.Value < 79000 do
        wait(1)
    end

    -- Upgrade SoulCurseAwk5
    local upgradeArgs13 = {
        [1] = workspace.Towers.SoulCurseAwk5
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs13))
end

-- Start the function
checkMoneyAndSpawnTowers()
