local Players=game:GetService("Players")
local TweenService=game:GetService("TweenService")
local UserInputService=game:GetService("UserInputService")
local RunService=game:GetService("RunService")
local LocalPlayer=Players.LocalPlayer
local pg=LocalPlayer.PlayerGui
if pg:FindFirstChild("EH")then pg.EH:Destroy()end
local sg=Instance.new("ScreenGui",pg)
sg.Name="EH" sg.ResetOnSpawn=false sg.DisplayOrder=999
local R=Color3.fromRGB(220,38,38) local R2=Color3.fromRGB(255,100,100) local BG=Color3.fromRGB(8,4,4) local PN=Color3.fromRGB(20,8,8) local TX=Color3.fromRGB(240,220,220) local MT=Color3.fromRGB(120,60,60) local GR=Color3.fromRGB(34,197,94) local YL=Color3.fromRGB(245,158,11) local BD=Color3.fromRGB(80,20,20)
local function ntf(msg,col)col=col or GR
local o=sg:FindFirstChild("NT")if o then o:Destroy()end
local f=Instance.new("Frame",sg)f.Name="NT"f.Size=UDim2.new(0,255,0,42)f.Position=UDim2.new(1,10,0,10)f.BackgroundColor3=PN f.BorderSizePixel=0 f.ZIndex=99
Instance.new("UICorner",f).CornerRadius=UDim.new(0,8)
local s=Instance.new("UIStroke",f)s.Color=col s.Thickness=1.5
local l=Instance.new("TextLabel",f)l.Size=UDim2.new(1,-10,1,0)l.Position=UDim2.new(0,10,0,0)l.BackgroundTransparency=1 l.Text=msg l.TextColor3=TX l.Font=Enum.Font.GothamBold l.TextSize=11 l.TextXAlignment=Enum.TextXAlignment.Left l.TextWrapped=true l.ZIndex=100
TweenService:Create(f,TweenInfo.new(0.3,Enum.EasingStyle.Back),{Position=UDim2.new(1,-268,0,10)}):Play()
task.delay(3,function()if f and f.Parent then f:Destroy()end end)end
-- JANELA
local win=Instance.new("Frame",sg)win.Size=UDim2.new(0,340,0,500)win.Position=UDim2.new(0.5,-170,0.5,-250)win.BackgroundColor3=BG win.BorderSizePixel=0
Instance.new("UICorner",win).CornerRadius=UDim.new(0,14)
local ws=Instance.new("UIStroke",win)ws.Color=R ws.Thickness=1.5
-- BANNER/LOGO
local banner=Instance.new("Frame",win)banner.Size=UDim2.new(1,0,0,70)banner.BackgroundColor3=Color3.fromRGB(15,3,3)banner.BorderSizePixel=0
Instance.new("UICorner",banner).CornerRadius=UDim.new(0,12)
local grad=Instance.new("UIGradient",banner)grad.Color=ColorSequence.new({ColorSequenceKeypoint.new(0,Color3.fromRGB(80,0,0)),ColorSequenceKeypoint.new(0.5,Color3.fromRGB(180,20,20)),ColorSequenceKeypoint.new(1,Color3.fromRGB(80,0,0))})grad.Rotation=90
local logoT=Instance.new("TextLabel",banner)logoT.Size=UDim2.new(1,0,0,38)logoT.Position=UDim2.new(0,0,0,6)logoT.BackgroundTransparency=1 logoT.Text="😈 EZKID HUB"logoT.Font=Enum.Font.GothamBlack logoT.TextSize=22 logoT.TextColor3=Color3.new(1,1,1) logoT.TextXAlignment=Enum.TextXAlignment.Center
local s2=Instance.new("UIStroke",logoT)s2.Color=Color3.fromRGB(255,60,60)s2.Thickness=1.5
local subT=Instance.new("TextLabel",banner)subT.Size=UDim2.new(1,0,0,18)subT.Position=UDim2.new(0,0,0,44)subT.BackgroundTransparency=1 subT.Text="TEAM EZKID JOIN TODAY 🔴"subT.Font=Enum.Font.GothamBold subT.TextSize=10 subT.TextColor3=R2 subT.TextXAlignment=Enum.TextXAlignment.Center
-- BOTÕES DO TOPO
local cb=Instance.new("TextButton",banner)cb.Size=UDim2.new(0,24,0,16)cb.Position=UDim2.new(1,-28,0,6)cb.BackgroundColor3=Color3.fromRGB(180,20,20)cb.Text="✕"cb.TextColor3=Color3.new(1,1,1)cb.Font=Enum.Font.GothamBold cb.TextSize=10 cb.BorderSizePixel=0
Instance.new("UICorner",cb).CornerRadius=UDim.new(0,4)
cb.MouseButton1Click:Connect(function()sg:Destroy()end)
local mb=Instance.new("TextButton",banner)mb.Size=UDim2.new(0,24,0,16)mb.Position=UDim2.new(1,-56,0,6)mb.BackgroundColor3=Color3.fromRGB(120,80,0)mb.Text="–"mb.TextColor3=Color3.new(1,1,1)mb.Font=Enum.Font.GothamBold mb.TextSize=14 mb.BorderSizePixel=0
Instance.new("UICorner",mb).CornerRadius=UDim.new(0,4)
local mn=false mb.MouseButton1Click:Connect(function()mn=not mn;win.Size=mn and UDim2.new(0,340,0,70)or UDim2.new(0,340,0,500)end)
-- DRAG
local dr,ds,sp=false,nil,nil
banner.InputBegan:Connect(function(i)if i.UserInputType==Enum.UserInputType.Touch or i.UserInputType==Enum.UserInputType.MouseButton1 then dr=true ds=i.Position sp=win.Position end end)
UserInputService.InputChanged:Connect(function(i)if dr and(i.UserInputType==Enum.UserInputType.Touch or i.UserInputType==Enum.UserInputType.MouseMovement)then local d=i.Position-ds;win.Position=UDim2.new(sp.X.Scale,sp.X.Offset+d.X,sp.Y.Scale,sp.Y.Offset+d.Y)end end)
UserInputService.InputEnded:Connect(function(i)if i.UserInputType==Enum.UserInputType.Touch or i.UserInputType==Enum.UserInputType.MouseButton1 then dr=false end end)
-- TABBAR
local tabBar=Instance.new("Frame",win)tabBar.Size=UDim2.new(1,0,0,30)tabBar.Position=UDim2.new(0,0,0,71)tabBar.BackgroundColor3=PN tabBar.BorderSizePixel=0
Instance.new("UIListLayout",tabBar).FillDirection=Enum.FillDirection.Horizontal
local ct=Instance.new("Frame",win)ct.Size=UDim2.new(1,0,1,-101)ct.Position=UDim2.new(0,0,0,101)ct.BackgroundTransparency=1 ct.BorderSizePixel=0
local tabs={} local function sw(id)for k,t in pairs(tabs)do t.p.Visible=(k==id)t.b.TextColor3=k==id and R2 or MT t.b.BackgroundTransparency=k==id and 0.6 or 1 end end
local tnames={"🏃Mov","⚔️Cmb","🔧Util","💻Exec"}
for i,name in ipairs(tnames)do
local b=Instance.new("TextButton",tabBar)b.Size=UDim2.new(0.25,0,1,0)b.BackgroundColor3=R b.BackgroundTransparency=1 b.Text=name b.TextColor3=MT b.Font=Enum.Font.GothamBold b.TextSize=10 b.BorderSizePixel=0 b.LayoutOrder=i
local p=Instance.new("Frame",ct)p.Size=UDim2.new(1,0,1,0)p.BackgroundTransparency=1 p.BorderSizePixel=0 p.Visible=false
tabs[i]={b=b,p=p}local idx=i b.MouseButton1Click:Connect(function()sw(idx)end)end
-- FUNÇÃO BTN
local function mkBtn(par,n,fn,i)
local r=Instance.new("Frame",par)r.Size=UDim2.new(1,-8,0,44)r.BackgroundColor3=PN r.BackgroundTransparency=0.2 r.BorderSizePixel=0 r.LayoutOrder=i
Instance.new("UICorner",r).CornerRadius=UDim.new(0,8)
local st=Instance.new("UIStroke",r)st.Color=BD st.Thickness=1
local t=Instance.new("TextLabel",r)t.Size=UDim2.new(1,-90,1,0)t.Position=UDim2.new(0,10,0,0)t.BackgroundTransparency=1 t.Text=n t.TextColor3=TX t.Font=Enum.Font.GothamBold t.TextSize=12 t.TextXAlignment=Enum.TextXAlignment.Left
local b=Instance.new("TextButton",r)b.Size=UDim2.new(0,70,0,28)b.Position=UDim2.new(1,-76,0.5,-14)b.BackgroundColor3=R b.BackgroundTransparency=0.5 b.Text="▶ EXEC"b.TextColor3=Color3.new(1,1,1)b.Font=Enum.Font.GothamBold b.TextSize=10 b.BorderSizePixel=0
Instance.new("UICorner",b).CornerRadius=UDim.new(0,6)
Instance.new("UIStroke",b).Color=R
b.MouseButton1Click:Connect(function()b.Text="⏳";task.spawn(function()local ok,e=pcall(fn);if ok then b.Text="✅"else ntf("❌ "..tostring(e):sub(1,35),R)b.Text="❌"end;task.delay(2,function()if b and b.Parent then b.Text="▶ EXEC"end end)end)end)end
local function mkSF(p)local sf=Instance.new("ScrollingFrame",p)sf.Size=UDim2.new(1,-4,1,-4)sf.Position=UDim2.new(0,2,0,2)sf.BackgroundTransparency=1 sf.BorderSizePixel=0 sf.ScrollBarThickness=3 sf.ScrollBarImageColor3=R sf.CanvasSize=UDim2.new(0,0,0,0)
local ll=Instance.new("UIListLayout",sf)ll.Padding=UDim.new(0,5)ll.SortOrder=Enum.SortOrder.LayoutOrder ll.HorizontalAlignment=Enum.HorizontalAlignment.Center
ll:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()sf.CanvasSize=UDim2.new(0,0,0,ll.AbsoluteContentSize.Y+10)end)return sf end
-- ABA 1: MOVIMENTO
local s1=mkSF(tabs[1].p)
mkBtn(s1,"💨 Speed x60",function()local c=LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait();c:WaitForChild("Humanoid").WalkSpeed=60;ntf("💨 Speed 60!",GR)end,1)
mkBtn(s1,"⚡ Speed x100",function()local c=LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait();c:WaitForChild("Humanoid").WalkSpeed=100;ntf("⚡ Speed 100!",GR)end,2)
mkBtn(s1,"🦘 Jump x80",function()local c=LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait();c:WaitForChild("Humanoid").JumpPower=80;ntf("🦘 Jump 80!",GR)end,3)
mkBtn(s1,"♾️ Infinite Jump",function()UserInputService.JumpRequest:Connect(function()local c=LocalPlayer.Character;if c then local h=c:FindFirstChildOfClass("Humanoid");if h then h:ChangeState(Enum.HumanoidStateType.Jumping)end end end);ntf("♾️ Inf Jump!",GR)end,4)
mkBtn(s1,"🦅 Fly",function()local c=LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait();local hrp=c:WaitForChild("HumanoidRootPart");c:WaitForChild("Humanoid").PlatformStand=true;local bv=Instance.new("BodyVelocity",hrp);bv.MaxForce=Vector3.new(1e5,1e5,1e5);bv.Velocity=Vector3.zero;local bg=Instance.new("BodyGyro",hrp);bg.MaxTorque=Vector3.new(1e5,1e5,1e5);bg.D=400;RunService.RenderStepped:Connect(function()local cam=workspace.CurrentCamera;local d=Vector3.zero;if UserInputService:IsKeyDown(Enum.KeyCode.W)then d=d+cam.CFrame.LookVector end;if UserInputService:IsKeyDown(Enum.KeyCode.S)then d=d-cam.CFrame.LookVector end;if UserInputService:IsKeyDown(Enum.KeyCode.A)then d=d-cam.CFrame.RightVector end;if UserInputService:IsKeyDown(Enum.KeyCode.D)then d=d+cam.CFrame.RightVector end;if UserInputService:IsKeyDown(Enum.KeyCode.Space)then d=d+Vector3.new(0,1,0)end;bv.Velocity=d*55;bg.CFrame=cam.CFrame end);ntf("🦅 Fly!",GR)end,5)
mkBtn(s1,"👻 Noclip",function()RunService.Stepped:Connect(function()local c=LocalPlayer.Character;if c then for _,v in ipairs(c:GetDescendants())do if v:IsA("BasePart")then v.CanCollide=false end end end end);ntf("👻 Noclip!",GR)end,6)
-- ABA 2: COMBATE
local s2b=mkSF(tabs[2].p)
mkBtn(s2b,"🛡️ God Mode",function()local h=LocalPlayer.Character:WaitForChild("Humanoid");h.MaxHealth=math.huge;h.Health=math.huge;RunService.Heartbeat:Connect(function()if h and h.Parent and h.Health<h.MaxHealth then h.Health=math.huge end end);ntf("🛡️ God Mode!",GR)end,1)
mkBtn(s2b,"💀 Kill Aura",function()local me=LocalPlayer;RunService.Heartbeat:Connect(function()local c=me.Character;if not c then return end;local hrp=c:FindFirstChild("HumanoidRootPart");if not hrp then return end;for _,pl in ipairs(Players:GetPlayers())do if pl~=me and pl.Character then local h=pl.Character:FindFirstChildOfClass("Humanoid");local h2=pl.Character:FindFirstChild("HumanoidRootPart");if h and h2 and h.Health>0 and(hrp.Position-h2.Position).Magnitude<15 then h.Health=0 end end end end);ntf("💀 Kill Aura!",GR)end,2)
mkBtn(s2b,"👁️ ESP Players",function()for _,pl in ipairs(Players:GetPlayers())do if pl~=LocalPlayer and pl.Character then local h=Instance.new("Highlight",pl.Character);h.FillColor=R;h.OutlineColor=Color3.new(1,1,1);h.FillTransparency=0.4 end end;ntf("👁️ ESP!",GR)end,3)
mkBtn(s2b,"💣 Kill All",function()local me=LocalPlayer;for _,pl in ipairs(Players:GetPlayers())do if pl~=me and pl.Character then local h=pl.Character:FindFirstChildOfClass("Humanoid");if h then h.Health=0 end end end;ntf("💣 Kill All!",GR)end,4)
-- ABA 3: UTILIDADES
local s3=mkSF(tabs[3].p)
mkBtn(s3,"⏰ Anti AFK",function()LocalPlayer.Idled:Connect(function()local v=game:GetService("VirtualUser");v:Button2Down(Vector2.zero,workspace.CurrentCamera.CFrame);task.wait(0.5);v:Button2Up(Vector2.zero,workspace.CurrentCamera.CFrame)end);ntf("⏰ Anti AFK!",GR)end,1)
mkBtn(s3,"📡 TP to Player",function()local c=LocalPlayer.Character;if not c then error("Sem char")end;local hrp=c:FindFirstChild("HumanoidRootPart");for _,pl in ipairs(Players:GetPlayers())do if pl~=LocalPlayer and pl.Character then local h2=pl.Character:FindFirstChild("HumanoidRootPart");if h2 and hrp then hrp.CFrame=h2.CFrame+Vector3.new(3,0,0);ntf("📡 TP!",GR)return end end end;error("Nenhum player")end,2)
mkBtn(s3,"🌾 Auto Farm",function()local me=LocalPlayer;task.spawn(function()while true do local c=me.Character;if c then local hrp=c:FindFirstChild("HumanoidRootPart");if hrp then for _,v in ipairs(workspace:GetDescendants())do if v:IsA("BasePart")then local n=v.Name:lower();if n:find("coin")or n:find("gem")or n:find("drop")or n:find("fruit")or n:find("item")then hrp.CFrame=CFrame.new(v.Position+Vector3.new(0,3,0));task.wait(0.05)end end end end end;task.wait(0.1)end end);ntf("🌾 Farm ON!",GR)end,3)
mkBtn(s3,"🌅 Skybox Ezkid",function()local sky=Instance.new("Sky",game:GetService("Lighting"));sky.SkyboxBk="rbxassetid://6444884337";sky.SkyboxDn="rbxassetid://6444884337";sky.SkyboxFt="rbxassetid://6444884337";sky.SkyboxLf="rbxassetid://6444884337";sky.SkyboxRt="rbxassetid://6444884337";sky.SkyboxUp="rbxassetid://6444884337";ntf("🌅 Skybox aplicada!",GR)end,4)
mkBtn(s3,"🔄 Rejoin",function()game:GetService("TeleportService"):Teleport(game.PlaceId,LocalPlayer)end,5)
-- ABA 4: EXEC + IA
local ep=tabs[4].p
local ebg=Instance.new("Frame",ep)ebg.Size=UDim2.new(1,-16,0,105)ebg.Position=UDim2.new(0,8,0,4)ebg.BackgroundColor3=Color3.fromRGB(6,2,2)ebg.BorderSizePixel=0
Instance.new("UICorner",ebg).CornerRadius=UDim.new(0,8)Instance.new("UIStroke",ebg).Color=BD
local ecb=Instance.new("TextBox",ebg)ecb.Size=UDim2.new(1,-12,1,-12)ecb.Position=UDim2.new(0,6,0,6)ecb.BackgroundTransparency=1 ecb.Text=""ecb.PlaceholderText="-- Cole ou escreva seu script aqui..."ecb.PlaceholderColor3=MT ecb.TextColor3=R2 ecb.Font=Enum.Font.Code ecb.TextSize=11 ecb.TextXAlignment=Enum.TextXAlignment.Left ecb.TextYAlignment=Enum.TextYAlignment.Top ecb.MultiLine=true ecb.ClearTextOnFocus=false
local exB=Instance.new("TextButton",ep)exB.Size=UDim2.new(1,-16,0,30)exB.Position=UDim2.new(0,8,0,113)exB.BackgroundColor3=R exB.BackgroundTransparency=0.4 exB.Text="▶ EXECUTAR"exB.TextColor3=Color3.new(1,1,1)exB.Font=Enum.Font.GothamBlack exB.TextSize=13 exB.BorderSizePixel=0
Instance.new("UICorner",exB).CornerRadius=UDim.new(0,8)Instance.new("UIStroke",exB).Color=R
local clB=Instance.new("TextButton",ep)clB.Size=UDim2.new(0.47,-4,0,24)clB.Position=UDim2.new(0,8,0,148)clB.BackgroundColor3=BD clB.BackgroundTransparency=0.4 clB.Text="✕ Limpar"clB.TextColor3=TX clB.Font=Enum.Font.GothamBold clB.TextSize=11 clB.BorderSizePixel=0
Instance.new("UICorner",clB).CornerRadius=UDim.new(0,6)
local sep=Instance.new("Frame",ep)sep.Size=UDim2.new(1,-16,0,1)sep.Position=UDim2.new(0,8,0,178)sep.BackgroundColor3=BD sep.BorderSizePixel=0
Instance.new("TextLabel",ep,{Size=UDim2.new(1,-16,0,16),Position=UDim2.new(0,8,0,184),BackgroundTransparency=1,Text="🤖 IA - Descreva o script:",TextColor3=MT,Font=Enum.Font.GothamBold,TextSize=10,TextXAlignment=Enum.TextXAlignment.Left})
local ibg=Instance.new("Frame",ep)ibg.Size=UDim2.new(1,-16,0,36)ibg.Position=UDim2.new(0,8,0,202)ibg.BackgroundColor3=Color3.fromRGB(6,2,2)ibg.BorderSizePixel=0
Instance.new("UICorner",ibg).CornerRadius=UDim.new(0,7)Instance.new("UIStroke",ibg).Color=BD
local iBox=Instance.new("TextBox",ibg)iBox.Size=UDim2.new(1,-12,1,-8)iBox.Position=UDim2.new(0,6,0,4)iBox.BackgroundTransparency=1 iBox.Text=""iBox.PlaceholderText="speed 200, fly, god, esp, kill aura, farm..."iBox.PlaceholderColor3=MT iBox.TextColor3=TX iBox.Font=Enum.Font.Gotham iBox.TextSize=11 iBox.MultiLine=false iBox.ClearTextOnFocus=false
local gBtn=Instance.new("TextButton",ep)gBtn.Size=UDim2.new(1,-16,0,28)gBtn.Position=UDim2.new(0,8,0,242)gBtn.BackgroundColor3=R gBtn.BackgroundTransparency=0.4 gBtn.Text="🤖 GERAR"gBtn.TextColor3=Color3.new(1,1,1)gBtn.Font=Enum.Font.GothamBlack gBtn.TextSize=12 gBtn.BorderSizePixel=0
Instance.new("UICorner",gBtn).CornerRadius=UDim.new(0,7)Instance.new("UIStroke",gBtn).Color=R
local rbg=Instance.new("Frame",ep)rbg.Size=UDim2.new(1,-16,0,88)rbg.Position=UDim2.new(0,8,0,274)rbg.BackgroundColor3=Color3.fromRGB(6,2,2)rbg.BorderSizePixel=0
Instance.new("UICorner",rbg).CornerRadius=UDim.new(0,8)Instance.new("UIStroke",rbg).Color=BD
local rBox=Instance.new("TextBox",rbg)rBox.Size=UDim2.new(1,-12,1,-12)rBox.Position=UDim2.new(0,6,0,6)rBox.BackgroundTransparency=1 rBox.Text="-- Script gerado aqui"rBox.TextColor3=R2 rBox.Font=Enum.Font.Code rBox.TextSize=10 rBox.TextXAlignment=Enum.TextXAlignment.Left rBox.TextYAlignment=Enum.TextYAlignment.Top rBox.MultiLine=true rBox.ClearTextOnFocus=false
local eIA=Instance.new("TextButton",ep)eIA.Size=UDim2.new(0.48,-4,0,24)eIA.Position=UDim2.new(0,8,0,366)eIA.BackgroundColor3=GR eIA.BackgroundTransparency=0.5 eIA.Text="▶ Exec"eIA.TextColor3=Color3.new(1,1,1)eIA.Font=Enum.Font.GothamBold eIA.TextSize=11 eIA.BorderSizePixel=0
Instance.new("UICorner",eIA).CornerRadius=UDim.new(0,6)
local cIA=Instance.new("TextButton",ep)cIA.Size=UDim2.new(0.48,-4,0,24)cIA.Position=UDim2.new(0.52,0,0,366)cIA.BackgroundColor3=BD cIA.BackgroundTransparency=0.4 cIA.Text="⎘ Copiar"cIA.TextColor3=TX cIA.Font=Enum.Font.GothamBold cIA.TextSize=11 cIA.BorderSizePixel=0
Instance.new("UICorner",cIA).CornerRadius=UDim.new(0,6)
exB.MouseButton1Click:Connect(function()local code=ecb.Text;if code==""then ntf("⚠️ Escreva algo!",YL)return end;exB.Text="⏳";task.spawn(function()local ok,err=pcall(function()local fn,e=loadstring(code);if fn then fn()else error(e)end end);if ok then ntf("✅ Executado!",GR)else ntf("❌ "..tostring(err):sub(1,40),R)end;exB.Text="▶ EXECUTAR"end)end)
clB.MouseButton1Click:Connect(function()ecb.Text=""end)
local function gl(pr)local t=pr:lower();local v=t:match("%d+")or"100"
local scripts={speed='local c=game.Players.LocalPlayer.Character or game.Players.LocalPlayer.CharacterAdded:Wait()\nc:WaitForChild("Humanoid").WalkSpeed=V',jump='local c=game.Players.LocalPlayer.Character or game.Players.LocalPlayer.CharacterAdded:Wait()\nc:WaitForChild("Humanoid").JumpPower=V',fly='local lp=game.Players.LocalPlayer;local c=lp.Character or lp.CharacterAdded:Wait();local hrp=c:WaitForChild("HumanoidRootPart");c:WaitForChild("Humanoid").PlatformStand=true;local bv=Instance.new("BodyVelocity",hrp);bv.MaxForce=Vector3.new(1e5,1e5,1e5);bv.Velocity=Vector3.zero;local bg=Instance.new("BodyGyro",hrp);bg.MaxTorque=Vector3.new(1e5,1e5,1e5);bg.D=400;game:GetService("RunService").RenderStepped:Connect(function();local u=game:GetService("UserInputService");local cam=workspace.CurrentCamera;local d=Vector3.zero;if u:IsKeyDown(Enum.KeyCode.W)then d=d+cam.CFrame.LookVector end;if u:IsKeyDown(Enum.KeyCode.S)then d=d-cam.CFrame.LookVector end;if u:IsKeyDown(Enum.KeyCode.A)then d=d-cam.CFrame.RightVector end;if u:IsKeyDown(Enum.KeyCode.D)then d=d+cam.CFrame.RightVector end;if u:IsKeyDown(Enum.KeyCode.Space)then d=d+Vector3.new(0,1,0)end;bv.Velocity=d*55;bg.CFrame=cam.CFrame;end)',god='local h=game.Players.LocalPlayer.Character:WaitForChild("Humanoid");h.MaxHealth=math.huge;h.Health=math.huge;game:GetService("RunService").Heartbeat:Connect(function()if h.Health<h.MaxHealth then h.Health=math.huge end end)',noclip='game:GetService("RunService").Stepped:Connect(function();local c=game.Players.LocalPlayer.Character;if c then for _,v2 in ipairs(c:GetDescendants())do if v2:IsA("BasePart")then v2.CanCollide=false end end end;end)',esp='for _,pl in ipairs(game.Players:GetPlayers())do if pl~=game.Players.LocalPlayer and pl.Character then local h=Instance.new("Highlight",pl.Character);h.FillColor=Color3.fromRGB(220,38,38);h.OutlineColor=Color3.new(1,1,1);h.FillTransparency=0.4 end end',kill='local me=game.Players.LocalPlayer;game:GetService("RunService").Heartbeat:Connect(function();local c=me.Character;if not c then return end;local hrp=c:FindFirstChild("HumanoidRootPart");if not hrp then return end;for _,pl in ipairs(game.Players:GetPlayers())do if pl~=me and pl.Character then local h=pl.Character:FindFirstChildOfClass("Humanoid");local h2=pl.Character:FindFirstChild("HumanoidRootPart");if h and h2 and(hrp.Position-h2.Position).Magnitude<15 then h.Health=0 end end end;end)',farm='local me=game.Players.LocalPlayer;task.spawn(function()while true do local c=me.Character;if c then local hrp=c:FindFirstChild("HumanoidRootPart");if hrp then for _,obj in ipairs(workspace:GetDescendants())do if obj:IsA("BasePart")then local n=obj.Name:lower();if n:find("coin")or n:find("gem")or n:find("drop")or n:find("fruit")or n:find("item")then hrp.CFrame=CFrame.new(obj.Position+Vector3.new(0,3,0));task.wait(0.05)end end end end end;task.wait(0.1)end end)',afk='game.Players.LocalPlayer.Idled:Connect(function()local v=game:GetService("VirtualUser");v:Button2Down(Vector2.zero,workspace.CurrentCamera.CFrame);task.wait(0.3);v:Button2Up(Vector2.zero,workspace.CurrentCamera.CFrame)end)'}
for k,sc in pairs(scripts)do if t:find(k)then return sc:gsub("V",v)end end
return'-- Comando: "'..pr:sub(1,25)..'"\n-- Tente: speed,
