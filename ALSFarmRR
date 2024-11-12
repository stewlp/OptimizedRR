-- RR Farm ALS
 local Httpservice =  game:GetServce(Httpservice)
 local Webhook = getgenv().Webhook
 local LobbyPlaceID = 12886143095
 local playerStatsFolder = "playerstats"
 local discorduserid = ""
 local function getPlayerStatsFile(playerName)
    return playerStatsFolder.."/"..playerName..".PlayerStats.json"
end
local function WebhookUpdate(playerName, playerLevel, emeralds, gold, rerolls, als_jewels, rewards)

    if getgenv().DiscordId == nil then
        getid = ""
    else
        getid = getgenv().DiscordId
        discorduserid = "<@" .. getid .. ">"
    end

    local response = request({
        Url = Webhook,
        Method = "POST",
        Headers = {
            ["Content-Type"] = "application/json"
        },
        Body = HttpService:JSONEncode({
            ["content"] = discorduserid,
            ["embeds"] = {{
                ["title"] = "Tsukii RR Farm | Anime Last Stand",
                ["description"] = "*user:**" ||" .. playerName .. "||\n**Level:** " .. playerLevel,
                ["type"] = "rich",
                ["color"] = tonumber("00FFF", 16),
                ["fields"] = {
                {
                    ["name"] = "Player Stats",
                    ["value"] = ""<:emerald:1305845302632386570> " .. emeralds .. "\n<:gold:1305845885099442256> " .. gold .. "\n<:rerolls:1305541972215201812>" .. rerolls .. "\n<:jewel:1305846330920534118> " .. als_jewels,
                    ["inline"] = true
                },
                {
                    ["name"] = "Rewards",
                    ["value"] = rewards,
                    ["inline"] = true
                }
            },
            ["footer"] = {
                ["text"] = "Avail Tsukii Pilot Service. \nhttps://discord.gg/ZAH6drzDSV",
                ["icon_url"] = "https://media.discordapp.net/attachments/1305534079068012584/1305536725808054334/input-onlinepngtools.png?ex=67336353&is=673211d3&hm=f561db811cab0d2302caa92d3172a62c9aa77c6ed158f5c979f4fc11db5bccb0&=&format=webp&quality=lossless",
            }
            }}
        })
    })
end
local function savePlayerStats(playerName, playerLevel, emeralds, gold, rerolls, als_jewels, rewards)
    local PlayerStats = {
        playerName = playerName,
        playerLevel = playerLevel,
        emeralds = emeralds,
        gold = gold,
        rerolls = rerolls,
        als_jewels = als_jewels,
        rewards = rewards
    }
    local jsonData = HttpService:GetJSONEncode(playerStats)
    local playerStatsFile = getPlayerStatsFile(playerName)
    if not isfolder(playerStatsFolder) then
        makefolder(playerStatsFolder) then
            makefolder(playerStatsFolder)
        end
        writefile(playerStatsFile, jsonData)
    end
    local function loadPLayerStatsData(playerName)
        local playerStatsFile = getPlayerStatsFile(playerName)
        if isfile(playerStatsFile) then
            local jsonData = readfile(playerStatsFile)
            local playerStats = HttpService:JSONEncode(jsonData)
            return playerStats
        else
            return {
                playerName = playerName,
                playerLevel = playerLevel,
                emeralds = emeralds,
                gold = gold,
                rerolls = rerolls,
                als_jewels = als_jewels,
                rewards = "<:rerolls:1305541972215201812> +2 "
            }
        end
    end
    local function UpdatePlayerStats()
        local player = game.Players.LocalPlayer
        local playerName = Player.DisplayName
        local playerLevel = Player.Level.Value
        local emeralds = player.Emeralds.Value
        local gold = player.Gold.Value
        local rerolls = player.Rerolls.Value
        local als_jewels = player.Jewels.Value
        local rewards = ""
    savePlayerStats(playerName, playerLevel, emeralds, gold, rerolls, als_jewels, rewards)
end
local function JoinINFCastle()
    while PlaceId == 12886143095 do
    wait(5)
    game:GetService("RunService"):Set3dRenderingEnabled(False)
    local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    local position = Vector3.new(28.3693733, 2.72691631, -40.4032669)
    local lookVector = Vector3.new(-0.766061664, 0, 0.642767608)
    local upVector = Vector3.new(0, 1, 0)
    local rightVector = lookVector:Cross(upVector)
    
    local InfinityCastleManager = CFrame.fromMatrix(position, rightVector, upVector)
    
    humanoidRootPart.CFrame = InfinityCastleManager

    local args = {
        [1] = "Play",
        [2] = 5,
        [3] = "True"
    }

    game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("InfiniteCastleManager"):FireServer(unpack(args))
    end
end
local function UpdateInGameStats()
    local player = game.Players.LocalPlayer
    local playerName = player.DisplayName
    local playerStats = loadPlayerStats(playerName)
    local rerolls = playerStats.rerolls + 2
    local rewards = "<:rerolls:1305541972215201812> +2 "
    savePlayerStats(playerName, playerStats.playerLevel, playerStats.emeralds, playerStats.gold, rerolls, playerStats.als_jewels, rewards)
    WebhookUpdate(playerName, playerStats.playerLevel, playerStats.emeralds, playerStats.gold, rerolls, playerStats.als_jewels, rewards)
end
local function SpawnUnit1()
    if not game:IsLoaded() then game.Loaded:Wait() end
    -- VoteSpeed
    local args = {
        [1] = true
    }
    
    game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("VoteChangeTimeScale"):FireServer(unpack(args))
    -- Spawn
    local unit = game:GetService("Players")[game.Players.LocalPlayer.Name].Slots.Slot1
    local unitname = unit.Value
    local Players = game:GetService("Players")
    local player = Players.LocalPlayer
    local args = {
        [1] = unitname,
        [2] = CFrame.new(-135.04019165039062, 197.93942260742188, 10.85269546508789, 1, 0, 0, 0, 1, 0, 0, 0, 1)
    }
    
    game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("PlaceTower"):FireServer(unpack(args))
    -- CPU + GPU SAVER
    game:GetService("RunService"):Set3dRenderingEnabled(false)
    local character = player.Character or player.CharacterAdded:Wait()
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
    local part = Instance.new("Part")
    
    part.Size = Vector3.new(4, 1, 4) 
    part.Anchored = true 
    part.Position = humanoidRootPart.Position - Vector3.new(0, humanoidRootPart.Size.Y / 2 + part.Size.Y / 2, 0)
    part.Parent = game.Workspace
    game.Workspace.PlaceOn:Destroy()
    game.Workspace.Enemies:Destroy()
    local function GameEnded()
        local IsGameEnded = player.PlayerGui:FindFirstChild("EndGameUI")
        return IsGameEnded ~= nil
    end
    repeat wait(5)
        local tower = workspace:FindFirstChild("Towers"):FindFirstChild(unitname)
        if tower then
            local upgradeArgs = {
                [1] = tower
            }
            game:GetService("ReplicatedStorage"):WaitForChild("Remotes"):WaitForChild("Upgrade"):InvokeServer(unpack(upgradeArgs))
        end
    until GameEnded()
    
    if GameEnded() then
        UpdateInGameStats()
        game:GetService("TeleportService"):Teleport(12886143095)
    end
end
if game.PlaceId == LobbyPlaceId then
    UpdatePlayerStats()
    JoinINFCastle()
    wait(120)
    game:GetService("TeleportService"):Teleport(12886143095)
else 
    wait(3)
    SpawnUnit1()
end
