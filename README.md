local Rayfield = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Rayfield/main/source'))()

local MainWindow = Rayfield:CreateWindow({
    Name = "Main",
    LoadingTitle = "Loading...",
    LoadingSubtitle = "by Falxe",
    ConfigurationSaving = {
        Enabled = true,
        FolderName = nil,
        FileName = "McDonalds Hub"
    },
    Discord = {
        Enabled = false,
        Invite = "noinvitelink",
        RememberJoins = true
    },
    KeySystem = true,
    KeySettings = {
        Title = "McDonalds Hub",
        Subtitle = "Key System",
        Note = "Key: McDonalds",
        FileName = "SiriusKey",
        SaveKey = true,
        GrabKeyFromSite = false,
        Key = "McDonalds"
    }
})

local MainTab = MainWindow:CreateTab("Main", 4483362458)

-- Adicionando a seção ESP
local ESPTab = MainWindow:CreateTab("ESP", 4483362459)

local ToggleInfiniteJump = MainTab:CreateToggle({
    Name = "Infinite Jump",
    CurrentValue = false,
    Flag = "Toggle1",
    Callback = function(InfiniteJumpEnabled)
        game:GetService("UserInputService").JumpRequest:Connect(function()
            if InfiniteJumpEnabled then
                game.Players.LocalPlayer.Character:FindFirstChildOfClass('Humanoid'):ChangeState("Jumping")
            end
        end)
    end,
})

local ButtonAutoParry = MainTab:CreateButton({
    Name = "Auto Parry",
    Callback = function()
        loadstring(game:HttpGet("https://raw.githubusercontent.com/Hosvile/Refinement/main/MC%3ABlade%20Ball%20Parry%20V4.0.0", true))()
    end,
})

local SpamParryActive = false

local ToggleSpamParry = MainTab:CreateToggle({
    Name = "Spam Parry",
    CurrentValue = false,
    Flag = "Toggle2",
    Callback = function(SpamParryEnabled)
        SpamParryActive = SpamParryEnabled
        while SpamParryActive do
            wait(0.00000001)
            local A_1 = 0.5
            local A_2 = CFrame.new(-362.910553, 162.087189, -108.92099, -0.307151765, 0.553279102, -0.774299741, 1.25479271e-08, 0.813630223, 0.581382751, 0.951660633, 0.178572729, -0.249907941)
            local A_3 = {
                ["3960686678"] = Vector3.new(1135.95263671875, 77.38058471679688, 143.90975952148438),
                ["5035366793"] = Vector3.new(354.0633850097656, 96.46871948242188, 152.36886596679688),
                ["5106936036"] = Vector3.new(541.0000610351562, 220.25466918945312, 75.87210083007812),
                ["4964704812"] = Vector3.new(956.8787841796875, 72.02096557617188, 150.72613525390625),
                ["2736297194"] = Vector3.new(1334.7119140625, 268.01336669921875, 64.19168090820312),
                ["4910866376"] = Vector3.new(581.0640258789062, 79.1673583984375, 164.9876251220703),
                ["2622402466"] = Vector3.new(445.94512939453125, 237.86489868164062, 71.14041137695312),
                ["4223346508"] = Vector3.new(637.4026489257812, 69.26394653320312, 179.8350067138672),
                ["2891761433"] = Vector3.new(947.3765869140625, 70.34628295898438, 153.00196838378906),
                ["3373954888"] = Vector3.new(1006.4465942382812, 79.81172180175781, 141.0169677734375),
                ["619750991"] = Vector3.new(1013.7300415039062, 83.64263153076172, 136.68939208984375),
                ["3110077224"] = Vector3.new(1063.3101806640625, 92.79286193847656, 127.34844970703125),
                ["1216040303"] = Vector3.new(1061.13720703125, 82.53833770751953, 137.90789794921875)
            }
            local A_4 = {
                [1] = 814,
                [2] = 273
            }
            local Event = game:GetService("ReplicatedStorage").Remotes.ParryAttempt
            Event:FireServer(A_1, A_2, A_3, A_4)
        end
    end,
})
