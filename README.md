local function checkMoneyAndSpawnTowers()
    local money = game:GetService("Players").LocalPlayer.leaderstats.Money

    -- Wait until Money reaches 400 and then spawn the first tower
    while money.Value < 400 do
        wait(1)
    end

    local args1 = {
        [1] = "fa609078-baec-4a98-b15d-e7dba01d8e57",
        [2] = CFrame.new(33.8105392, 8.50992775, -151.300278, -0.0192896146, -0, -0.999813974, -0, 1.00000012, -0, 0.999813974, 0, -0.0192896146) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }

    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(args1))

    -- Check every 5 seconds if the EndScreen ImageLabel is visible, and teleport if visible
    while true do
        wait(5)
        local endScreen = game:GetService("Players").LocalPlayer.PlayerGui.GameGui.EndScreen
        if endScreen and endScreen.ImageLabel.Visible then
            game:GetService("TeleportService"):Teleport(17720162456, game:GetService("Players").LocalPlayer)
            break
        end
    end

    -- Wait until Money reaches 800 and then spawn the next towers
    while money.Value < 800 do
        wait(1)
    end

    local args2 = {
        [1] = "9f7ab22e-1667-4f45-a806-18afdde643df",
        [2] = CFrame.new(5.72673798, 8.51061249, -137.76712, -1, 0, 0, 0, 1, 0, 0, 0, -1) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }

    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(args2))

    -- Continue the remaining script without changes

    while money.Value < 1200 do
        wait(1)
    end

    local args3 = {
        [1] = "9f7ab22e-1667-4f45-a806-18afdde643df",
        [2] = CFrame.new(6.21704865, 8.51061249, -132.107239, -1, 0, 0, 0, 1, 0, 0, 0, -1) * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
    }

    game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(args3))

    -- Continue with the rest of your script
    -- (Rest of the code unchanged)

    -- Wait until Money reaches 28700 and then upgrade KingOfCurses3
    while money.Value < 28700 do
        wait(1)
    end

    local upgradeArgs8 = {
        [1] = workspace.Towers.KingOfCurses3
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs8))

    -- Wait until Money reaches 13200 and then upgrade SoulCurseAwk2
    while money.Value < 13200 do
        wait(1)
    end

    local upgradeArgs9 = {
        [1] = workspace.Towers.SoulCurseAwk2
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs9))

    -- Wait until Money reaches 42200 and then upgrade KingOfCurses4
    while money.Value < 42200 do
        wait(1)
    end

    local upgradeArgs10 = {
        [1] = workspace.Towers.KingOfCurses4
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs10))

    -- Wait until Money reaches 22600 and then upgrade SoulCurseAwk3
    while money.Value < 22600 do
        wait(1)
    end

    local upgradeArgs11 = {
        [1] = workspace.Towers.SoulCurseAwk3
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs11))

    -- Wait until Money reaches 42100 and then upgrade SoulCurseAwk4
    while money.Value < 42100 do
        wait(1)
    end

    local upgradeArgs12 = {
        [1] = workspace.Towers.SoulCurseAwk4
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs12))

    -- Wait until Money reaches 79000 and then upgrade SoulCurseAwk5
    while money.Value < 79000 do
        wait(1)
    end

    local upgradeArgs13 = {
        [1] = workspace.Towers.SoulCurseAwk5
    }
    game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs13))
end

-- Start the function
checkMoneyAndSpawnTowers()
