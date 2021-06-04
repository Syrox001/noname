# noname
4/5/2021 holy war 3 Spin Rarity Code
make them x100 (Delete 2, zero's) for real rarity.

local v1 = {}
local v4 = game:GetService("MarketplaceService")
local v9 = require(script.Parent.Parent:WaitForChild("General"))
local v12 = require(script:WaitForChild("RandomSystem"))
local v13 = {}
local v14 = {}
v14.HeadScale = 0.95
v14.BodyWidthScale = 0.85
v14.BodyDepthScale = 0.9
v14.BodyHeightScale = 1
v14.BodyProportionScale = 0
v14.BodyTypeScale = 0
v13.DefaultScaling = v14
v13.Races = {}
v1.CharacterScaling = v13
v1.TotalRolls = 45
local v94 = {}
v94.Magic = 7
v94.Race = 8
v1.SpinTimes = v94
local v97 = {}
v97[1] = "Magic"
v97[2] = "Race"
v1.SpinTypes = v97
v1.GetCurrentRoll = function(p1, p2)
    if p2 == "Magic" then
        if p1:WaitForChild("MagicPower") then
            if not p1:WaitForChild(p2) then
                local v23 = p1:WaitForChild(p2)
                if not v23 then
                    if p2 == "Magic" then
                        v23 = p1.MagicPower.Value
                        if v23 then
                            local v26 = p1:WaitForChild(p2)
                            if not v26 then
                                v26 = p1:WaitForChild(p2).Value
                            end
                        end
                        return v26
                        return false
                    end
                end
            end
        end
    end
end
v1.GenerateNewRolls = function(p3)
    local v31 = {}
    local v33 = v12:new()
    local v36, v37, v38 = pairs(p3)
    for v39, v40 in v36, v37, v38 do
        print()
        v33:AddItem(v39, v40.Chance)
    end
    v38 = 1
    v39 = v1
    v36 = v39.TotalRolls
    v37 = 1
    for v38 = v38, v36, v37 do
        v39 = nil
        v39 = v33:GetRandomItem()
        table.insert(v31, v39)
    end
    return v31
end
local function GetSpinChances_1(p4, p5, p6)
    local v50
    if p5 == "Race" then
        v50 = v1.Races
        local v53 = v9
        local v54 = v53.Gamepasses
        local v56 = v4:UserOwnsGamePassAsync(p4.UserId, v54.IncreaseRareRaceChances)
        if v56 then
            local v57 = p4.UserId
            if v57 == 134676007 then
                v57 = pairs
                local v59, v60, v61 = v57(v50)
                for v54, v53 in v59, v60, v61 do
                    local v62 = v53.GamepassChance
                    if not v62 then
                        v62 = v50[v54]
                        v62.Chance = v50[v54].GamepassChance
                    end
                end
            end
            v59 = v4
            v61 = p4.UserId
            v62 = v9
            v53 = v62.Gamepasses
            v54 = v53.UnlockGoddess
            local v65 = v59:UserOwnsGamePassAsync(v61, v54)
            if not v65 then
                v53 = v1
                local v66 = v53.UnlockedRaces
                local v67 = v66.Goddess
                if not v56 then
                    v66 = "GamepassChance"
                else
                    v66 = "Chance"
                end
                v60 = v67[v66]
                local v81 = 0
                local v82 = next
                v53 = v50
                v62 = nil
                for v64, v63 in v82, v53, v62 do
                    v67 = v67 + 1
                end
                v82 = pairs
                v53 = v50
                local v68, v69, v62 = v82(v53)
                for v64, v63 in v68, v69, v62 do
                    v50[v64].Chance = v50[v64].Chance - v60 / v67
                end
                v62 = v1
                v69 = v62.UnlockedRaces
                v68 = v69.Goddess
                v50.Goddess = v68
                v68 = v50.Goddess
                v68.Chance = v60
                return v50
                if p5 == "Magic" then
                    v60 = v1
                    v65 = v60.Magics
                    v56 = v65[p6]
                    if not v56 then
                        v65 = v1
                        v56 = v65.Magics
                        local v74 = v56[p6]
                        v56 = v4
                        v60 = p4.UserId
                        v69 = v9
                        v68 = v69.Gamepasses
                        v81 = v68.IncreaseRareRaceChances
                        if not v56:UserOwnsGamePassAsync(v60, v81) then
                            v65 = pairs
                            local v77, v78, v79 = v65(v74)
                            for v68, v69 in v77, v78, v79 do
                                v62 = v69.GamepassChance
                                if not v62 then
                                    v62 = v74[v68]
                                    v63 = v74[v68]
                                    v64 = v63.GamepassChance
                                    v62.Chance = v64
                                end
                            end
                        end
                    end
                end
            end
            return v74
        end
    end
end
v1.GetSpinChances = GetSpinChances_1
GetSpinChances_1 = {}
local v102 = {}
v102.Name = "Goddess"
v102.Chance = 0.01
v102.GamepassChance = 0.1
v102.Image = "rbxassetid://5092933945"
GetSpinChances_1.Goddess = v102
v1.UnlockedRaces = GetSpinChances_1
GetSpinChances_1 = {}
local v107 = {}
v107.Name = "Human"
v107.Chance = 0.49
v107.GamepassChance = 0.58
v107.Image = "rbxassetid://3931307243"
GetSpinChances_1.Human = v107
local v112 = {}
v112.Name = "Fairy"
v112.Chance = 0.25
v112.GamepassChance = 0.2
v112.Image = "rbxassetid://3931217446"
GetSpinChances_1.Fairy = v112
local v117 = {}
v117.Name = "Giant"
v117.Chance = 0.25
v117.GamepassChance = 0.2
v117.Image = "rbxassetid://3931209140"
GetSpinChances_1.Giant = v117
local v122 = {}
v122.Name = "Demon"
v122.Chance = 0.01
v122.GamepassChance = 0.02
v122.Image = "rbxassetid://3931210527"
GetSpinChances_1.Demon = v122
v1.Races = GetSpinChances_1
GetSpinChances_1 = {}
local v127 = {}
local v128 = {}
v128.Chance = 0.2
v128.Image = "rbxassetid://2788887148"
v128.Name = "Fire"
v128.GamepassChance = 0.1
v127.Fire = v128
local v132 = {}
v132.Chance = 0.299
v132.Image = "rbxassetid://2788887347"
v132.Name = "Ice"
v132.GamepassChance = 0.2
v127.Ice = v132
local v137 = {}
v137.Chance = 0.3
v137.Image = "http://www.roblox.com/asset/?id=4595438175"
v137.Name = "Water"
v137.GamepassChance = 0.1
v127.Water = v137
local v142 = {}
v142.Chance = 0
v142.Image = "http://www.roblox.com/asset/?id=4595441269"
v142.Name = "Nature"
v127.Nature = v142
local v146 = {}
v146.Chance = 0.1
v146.Image = "http://www.roblox.com/asset/?id=4595442522"
v146.Name = "Lightning"
v146.GamepassChance = 0.2
v127.Lightning = v146
local v151 = {}
v151.Chance = 0
v151.Image = "http://www.roblox.com/asset/?id=4904897210"
v151.Name = "Infinity"
v127.Infinity = v151
local v155 = {}
v155.Chance = 0.1
v155.Image = "http://www.roblox.com/asset/?id=4595440015"
v155.Name = "Snatch"
v155.GamepassChance = 0.2
v127.Snatch = v155
local v160 = {}
v160.Chance = 0.001
v160.Image = "http://www.roblox.com/asset/?id=4595438855"
v160.Name = "SunShine"
v160.GamepassChance = 0.01
v127.SunShine = v160
GetSpinChances_1.Human = v127
local v165 = {}
local v166 = {}
v166.Chance = 0.01
v166.Image = "http://www.roblox.com/asset/?id=4595434056"
v166.Name = "Fairy_King"
v166.GamepassChance = 0.05
v165.Fairy_King = v166
local v171 = {}
v171.Chance = 0.65
v171.Image = "http://www.roblox.com/asset/?id=4595433465"
v171.Name = "Fairy"
v165.Fairy = v171
local v175 = {}
v175.Chance = 0.34
v175.Image = "http://www.roblox.com/asset/?id=4595434866"
v175.Name = "Link"
v165.Link = v175
GetSpinChances_1.Fairy = v165
local v179 = {}
local v180 = {}
v180.Chance = 0.8
v180.Image = "http://www.roblox.com/asset/?id=4595430426"
v180.Name = "Giant"
v179.Giant = v180
local v184 = {}
v184.Chance = 0.15
v184.Image = "http://www.roblox.com/asset/?id=4595431787"
v184.Name = "Creation"
v184.GamepassChance = 0.25
v179.Creation = v184
local v189 = {}
v189.Chance = 0.05
v189.Image = "http://www.roblox.com/asset/?id=4595432721"
v189.Name = "Creation_V2"
v189.GamepassChance = 0.5
v179.Creation_V2 = v189
GetSpinChances_1.Giant = v179
local v194 = {}
local v195 = {}
v195.Chance = 0.3
v195.Image = "http://www.roblox.com/asset/?id=4000955092"
v195.Name = "EvilBreath"
v194.EvilBreath = v195
local v199 = {}
v199.Chance = 0.193
v199.Image = "http://www.roblox.com/asset/?id=4600480867"
v199.Name = "Posession"
v194.Posession = v199
local v203 = {}
v203.Chance = 0.007
v203.Image = "http://www.roblox.com/asset/?id=4600481047"
v203.Name = "Crisis"
v203.GamepassChance = 0.04
v194.Crisis = v203
local v208 = {}
v208.Chance = 0.2
v208.Image = "http://www.roblox.com/asset/?id=4600517699"
v208.Name = "DeathBurn"
v208.GamepassChance = 0.3
v194.DeathBurn = v208
local v213 = {}
v213.Chance = 0.3
v213.Image = "http://www.roblox.com/asset/?id=4600481574"
v213.Name = "Illusion"
v194.Illusion = v213
GetSpinChances_1.Demon = v194
local v217 = {}
local v218 = {}
v218.Chance = 0.29985
v218.Image = "http://www.roblox.com/asset/?id=5491900277"
v218.Name = "Decree"
v218.GamepassChance = 0.3
v217.Decree = v218
local v223 = {}
v223.Chance = 0.7
v223.Image = "rbxassetid://5654707355"
v223.Name = "Ice"
v217.Ice = v223
local v227 = {}
v227.Chance = 0.00015
v227.Image = "http://www.roblox.com/asset/?id=5654623225"
v227.Name = "SunShine"
v227.GamepassChance = 0.01
v217.SunShine = v227
GetSpinChances_1.Goddess = v217
v1.Magics = GetSpinChances_1
return v1

