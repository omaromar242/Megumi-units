-- Services
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Players = game:GetService("Players")

-- Player and Money reference
local player = Players.LocalPlayer
local moneyStat = player:WaitForChild("leaderstats"):WaitForChild("Money")

-- Reference to the Equipped IntValues
local equipped1 = player:WaitForChild("Equipped1")
local equipped2 = player:WaitForChild("Equipped2")
local equipped3 = player:WaitForChild("Equipped3")

-- New IDs for the equipped values
local newEquipped1ID = "new_id_for_equipped1"
local newEquipped2ID = "new_id_for_equipped2"
local newEquipped3ID = "new_id_for_equipped3"

-- Helper function to wait for or check a specific Money value
local function waitForMoney(value)
    if moneyStat.Value >= value then
        return -- Exit if Money is already enough
    end
    while moneyStat.Value < value do
        task.wait(0.1)
    end
end

-- Function to update the Equipped values with the new IDs
local function updateEquipped()
    -- Set the new ID values to the Equipped IntValues
    equipped1.Value = newEquipped1ID
    equipped2.Value = newEquipped2ID
    equipped3.Value = newEquipped3ID
end

-- Step 1: Spawn the first tower
local args1 = {
    [1] = "ca30e0fc-4701-433a-aa5f-83102bd91103",
    [2] = CFrame.new(-48.4406929, 7.80889416, -57.8131981, 0.91123724, -0, -0.411881834, 0, 1, -0, 0.411881834, 0, 0.91123724)
        * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
}
ReplicatedStorage.Functions.SpawnNewTower:InvokeServer(unpack(args1))

-- Step 2: Wait until Money is 900 and upgrade the first tower
waitForMoney(900)
local upgradeArgs1 = {
    [1] = workspace.Towers.BowSorcererAwk
}
ReplicatedStorage.Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs1))

-- Step 3: Wait until Money is 650 and spawn the second tower
waitForMoney(650)
local args3 = {
    [1] = "ca30e0fc-4701-433a-aa5f-83102bd91103",
    [2] = CFrame.new(-39.3042946, 7.80889416, -87.9372711, 0.827569544, 0, 0.56136322, 0, 1, 0, -0.56136322, 0, 0.827569544)
        * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
}
ReplicatedStorage.Functions.SpawnNewTower:InvokeServer(unpack(args3))

-- Step 4: Wait until Money is 900 and upgrade the second tower
waitForMoney(900)
local upgradeArgs2 = {
    [1] = workspace.Towers.BowSorcererAwk
}
ReplicatedStorage.Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs2))

-- Step 5: Wait until Money is 2400 and sell the upgraded tower
waitForMoney(2400)
local args5 = {
    [1] = workspace.Towers.BowSorcererAwk2
}
ReplicatedStorage.Functions.SellTower:InvokeServer(unpack(args5))

-- Step 6: Upgrade the tower after selling
local upgradeArgs3 = {
    [1] = workspace.Towers.BowSorcererAwk2
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs3))

-- Step 7: Wait until Money is 400 and spawn a new tower
waitForMoney(400)
local args7 = {
    [1] = "b3244fb2-605a-4a6d-84da-4b32a9a5eafd",
    [2] = CFrame.new(-32.2276421, 7.797894, -83.8576355, -1, 0, 0, 0, 1, 0, 0, 0, -1)
        * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
}
ReplicatedStorage.Functions.SpawnNewTower:InvokeServer(unpack(args7))

-- Step 8: Wait until Money is 7000 and upgrade the BowSorcererAwk3 tower
waitForMoney(7000)
local upgradeArgs4 = {
    [1] = workspace.Towers.BowSorcererAwk3
}
ReplicatedStorage.Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs4))

-- Step 9: Wait until Money is 1200, then wait an extra 3 seconds before upgrading BroomSorcerer
waitForMoney(1200)
task.wait(3) -- Added 3-second delay here
local args = {
    [1] = workspace.Towers.BroomSorcerer
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(args))

-- Step 10: Wait until Money is 800 and spawn a new tower
waitForMoney(800)
local args10 = {
    [1] = "5d160787-8ef8-41eb-bc70-7c2e5e071984",
    [2] = CFrame.new(-37.6261559, 7.80889416, -82.6685562, -1, 0, 0, 0, 1, 0, 0, 0, -1)
        * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
}
ReplicatedStorage.Functions.SpawnNewTower:InvokeServer(unpack(args10))

-- Step 11: After Step 10 - Additional actions

-- Wait until Money reaches 650
waitForMoney(650)

-- Step 12: Spawn a new tower
local args12 = {
    [1] = "ca30e0fc-4701-433a-aa5f-83102bd91103",
    [2] = CFrame.new(-43.0112267, 7.80889416, -88.2887268, -1, 0, 0, 0, 1, 0, 0, 0, -1)
        * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
}
game:GetService("ReplicatedStorage").Functions.SpawnNewTower:InvokeServer(unpack(args12))

-- Wait until Money reaches 900 and upgrade the BowSorcererAwk tower
waitForMoney(900)
local upgradeArgs6 = {
    [1] = workspace.Towers.BowSorcererAwk
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs6))

-- Wait until Money reaches 2400 and upgrade the BowSorcererAwk2 tower
waitForMoney(2400)
local upgradeArgs7 = {
    [1] = workspace.Towers.BowSorcererAwk2
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs7))

-- Wait until Money reaches 7000 and upgrade the BowSorcererAwk3 tower
waitForMoney(7000)
local upgradeArgs8 = {
    [1] = workspace.Towers.BowSorcererAwk3
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs8))

-- Step 13: Wait until Money reaches 29000 and upgrade the BowSorcererAwk4 tower
waitForMoney(29000)
local upgradeArgs9 = {
    [1] = workspace.Towers.BowSorcererAwk4
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs9))

-- Step 14: Wait until Money reaches 3600 and upgrade the GuitarSorcerer tower
waitForMoney(3600)
local upgradeArgs10 = {
    [1] = workspace.Towers.GuitarSorcerer
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs10))

-- Step 15: Wait until Money reaches 4000, then wait 5 seconds before upgrading the BroomSorcerer2 tower
waitForMoney(4000)
task.wait(30) -- Added 5-second delay here
local upgradeArgs11 = {
    [1] = workspace.Towers.BroomSorcerer2
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs11))

-- Step 16: Wait until Money reaches 29000 and upgrade the BowSorcererAwk4 tower
waitForMoney(29000)
local upgradeArgs12 = {
    [1] = workspace.Towers.BowSorcererAwk4
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs12))

-- Step 17: Wait until Money reaches 12000, then wait 5 seconds before upgrading the GuitarSorcerer2 tower
waitForMoney(12000)
task.wait(20) -- Added 5-second delay here
local upgradeArgs13 = {
    [1] = workspace.Towers.GuitarSorcerer2
}
game:GetService("ReplicatedStorage").Functions.UpgradeTower:InvokeServer(unpack(upgradeArgs13))

-- Step 18: Wait until Money is 650 and spawn a new tower
waitForMoney(650)
local args13 = {
    [1] = "ca30e0fc-4701-433a-aa5f-83102bd91103",
    [2] = CFrame.new(-41.9435692, 7.80889416, -91.8173599, -1, 0, 0, 0, 1, 0, 0, 0, -1)
        * CFrame.Angles(-3.1415927410125732, -8.742277657347586e-08, -3.1415927410125732)
}
ReplicatedStorage.Functions.SpawnNewTower:InvokeServer(unpack(args13))
