#[
CRESCENT ROSE

High Caliber Sniper-Scythe

REQUIRES:
HoloModelAny
PropCore
SetVelocity
Particle
TF2 (Sniper knife)
CS:S (Sounds)
A crowbar and a crossbow

rwby.wikia.com/wiki/Crescent_Rose

Written by suck my PEEP :D


@name Crescent Rose
@persist [Base Pivot Trailer PlayerTarget]:entity 
@persist [Hold M1 M2 Anim SMAnim T Cd] 
@persist [Light Dark Red Black]:vector
runOnTick(1)

if(T<10000)
{
    T+=100 #If some holograms fail to spawn, lower this number
}
if(first())
{
    PlayerTarget = owner()
    
    entity():setAlpha(0)
    Red = vec(120,0,0)
    Dark = vec(40,40,40)
    Black = vec(1,1,1)
    Light = vec(150,150,150)
    Pivot = holoCreate(-1) holoAlpha(-1,0)
    
    #Centre
    Base = holoCreate(0,entity():toWorld(vec(0,0,0)),vec(2,0.2,0.3),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(0,Pivot)
    
    #Trim underneath
    holoCreate(1,entity():toWorld(vec(-6,0,-1.5)),vec(1,0.25,0.15),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(1,Base)
    holoCreate(2,entity():toWorld(vec(-12,0,0)),vec(0.37,0.25,0.15),entity():toWorld(ang(70,0,0)),Dark,"cube") holoParent(2,Base)
    holoCreate(3,entity():toWorld(vec(-22,0,0)),vec(1.6,0.25,0.1),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(3,Base)
    holoCreate(4,entity():toWorld(vec(-31,0,0)),vec(0.3,0.25,0.05),entity():toWorld(ang(70,0,0)),Dark,"cube") holoParent(4,Base)
    
    #Centre 2
    holoCreate(5,entity():toWorld(vec(-22,0,0)),vec(1.6,0.15,0.25),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(5,Base)
    
    #Tail
    holoCreate(6,entity():toWorld(vec(15,0,-0.8)),vec(0.14,0.14,0.5),entity():toWorld(ang(90,0,0)),Dark,"cylinder") holoParent(6,Base) 
    holoCreate(7,entity():toWorld(vec(24,0,-0.8)),vec(0.1,0.1,1.8),entity():toWorld(ang(90,0,0)),Dark,"cylinder") holoParent(7,Base)
    holoCreate(8,entity():toWorld(vec(35,0,-0.8)),vec(0.25,0.1,0.2),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(8,Base)
    holoCreate(9,entity():toWorld(vec(37.7,0,-0.8)),vec(0.2,0.05,0.2),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(9,Base)   
    
    #Taper 
    holoCreate(10,entity():toWorld(vec(41.3,0,-0.8)),vec(0.2,0.05,0.4),entity():toWorld(ang(90,0,0)),Dark,"pyramid") holoParent(10,Base)
    holoCreate(11,entity():toWorld(vec(38.5,0,-0.8)),vec(0.4,0.06,0.02),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(11,Base)
    
    #Scope
    holoCreate(12,entity():toWorld(vec(6,0,2)),vec(0.2,0.06,0.2),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(12,Base)
    holoCreate(13,entity():toWorld(vec(6,0,3.5)),vec(0.1,0.1,0.3),entity():toWorld(ang(90,0,0)),Red,"cylinder") holoParent(13,Base)
    holoCreate(14,entity():toWorld(vec(7.5,0,3.5)),vec(0.11,0.11,0.04),entity():toWorld(ang(90,0,0)),Dark,"cylinder") holoParent(14,Base) 
    holoCreate(15,entity():toWorld(vec(4.5,0,3.5)),vec(0.11,0.11,0.04),entity():toWorld(ang(90,0,0)),Dark,"cylinder") holoParent(15,Base)        

    #Barrel
    holoCreate(16,entity():toWorld(vec(-40,0,0)),vec(1.8,0.1,0.18),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(16,Base)
    holoCreate(17,entity():toWorld(vec(-50,0,0)),vec(0.38,0.2,0.4),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(17,16)
    
    #Magazine
    holoCreate(18,entity():toWorld(vec(-2,0,-4)),vec(0.7,0.12,0.4),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(18,Base)
    holoCreate(19,entity():toWorld(vec(-2,0,-6.4)),vec(0.4,0.12,0.695),entity():toWorld(ang(90,0,0)),Red,"prism") holoParent(19,Base)
    
    #Bridge
    holoCreate(20,entity():toWorld(vec(-47,0,-1)),vec(0.25,0.25,0.65),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(20,16)
    holoCreate(21,entity():toWorld(vec(-47,0,2)),vec(0.1,0.1,0.1),entity():toWorld(ang(0,0,0)),vec(255,255,255),"cube") holoParent(21,16) holoAlpha(21,0)#Hinge 
    holoCreate(22,entity():toWorld(vec(-47,-1.6,7)),vec(0.2,0.08,0.8),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(22,21)
    holoCreate(220,entity():toWorld(vec(-47,1.6,7)),vec(0.2,0.08,0.8),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(220,21)
    
    holoCreate(23,entity():toWorld(vec(-49.5,1.6,7)),vec(0.07,0.6,0.25),entity():toWorld(ang(0,-90,90)),Dark,"prism") holoParent(23,22)
    holoCreate(24,entity():toWorld(vec(-44.3,-1.6,7)),vec(0.07,0.6,0.25),entity():toWorld(ang(0,90,90)),Dark,"prism") holoParent(24,22)
    holoCreate(231,entity():toWorld(vec(-49.5,-1.6,7)),vec(0.07,0.6,0.25),entity():toWorld(ang(0,-90,90)),Dark,"prism") holoParent(231,22)  #THIS SHIT IS BAD DO NOT DO IT
    holoCreate(241,entity():toWorld(vec(-44.3,1.6,7)),vec(0.07,0.6,0.25),entity():toWorld(ang(0,90,90)),Dark,"prism") holoParent(241,22)
}
elseif(!holoEntity(25) && holoCanCreate() & T>1000)
{
    #Top
    holoCreate(25,entity():toWorld(vec(-46,0,12)),vec(0.1,0.1,0.1),entity():toWorld(ang(0,0,0)),vec(255,255,255),"cube") holoParent(25,22) holoAlpha(25,0)#Hinge
    holoCreate(26,entity():toWorld(vec(-46,1.9,12)),vec(0.15,0.15,0.15),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(26,25)
    holoCreate(260,entity():toWorld(vec(-46,-1.9,12)),vec(0.15,0.15,0.15),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(260,25)

    holoCreate(27,entity():toWorld(vec(-47.5,-1.9,13.6)),vec(0.7,0.09,0.3),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(27,25)
    holoCreate(28,entity():toWorld(vec(-51.7,-1.9,13.60)),vec(0.2,0.09,0.3),entity():toWorld(ang(0,0,0)),Red,"prism") holoParent(28,25)
    holoCreate(29,entity():toWorld(vec(-43.24,-1.9,13.60)),vec(0.2,0.09,0.3),entity():toWorld(ang(0,0,0)),Red,"prism") holoParent(29,25)
}
elseif(!holoEntity(30) && holoCanCreate()  & T>1500)
{
    holoCreate(30,entity():toWorld(vec(-47.5,1.9,13.6)),vec(0.7,0.09,0.3),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(30,25)
    holoCreate(31,entity():toWorld(vec(-51.7,1.9,13.60)),vec(0.2,0.09,0.3),entity():toWorld(ang(0,0,0)),Red,"prism") holoParent(31,25)
    holoCreate(32,entity():toWorld(vec(-43.24,1.9,13.60)),vec(0.2,0.09,0.3),entity():toWorld(ang(0,0,0)),Red,"prism") holoParent(32,25)
    
    #Top Blade
    holoCreate(33,entity():toWorld(vec(-46,0,12)),vec(0.1,0.1,0.1),entity():toWorld(ang(0,0,0)),vec(255,255,255),"cube") holoParent(33,22) holoAlpha(33,0)#Hinge
    
    holoCreate(34,entity():toWorld(vec(-62,1.8,13)),vec(0.6,0.6,1.1),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(34,33)
    holoModel(34,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(34,"models/debug/debugwhite")
    holoClipEnabled(34,1)
    holoClip(34,vec(17,0,0),vec(1,0,0),0)
    
    holoCreate(35,entity():toWorld(vec(-59.7,1.8,12.9)),vec(0.55,0.5,1),entity():toWorld(ang(0,0,0)),Light,"cube") holoParent(35,33)
    holoModel(35,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(35,"models/debug/debugwhite")
    holoClipEnabled(35,1)
    holoClip(35,vec(17,0,0),vec(1,0,0),0)
    
    holoCreate(36,entity():toWorld(vec(-62,-1.8,13)),vec(0.6,0.6,1.1),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(36,33)
    holoModel(36,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(36,"models/debug/debugwhite")
    holoClipEnabled(36,1)
    holoClip(36,vec(17,0,0),vec(1,0,0),0)
    
    holoCreate(37,entity():toWorld(vec(-59.7,-1.8,12.9)),vec(0.55,0.5,1),entity():toWorld(ang(0,0,0)),Light,"cube") holoParent(37,33)
    holoModel(37,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(37,"models/debug/debugwhite")
    holoClipEnabled(37,1)
    holoClip(37,vec(17,0,0),vec(1,0,0),0)
    
    #Arm
    holoCreate(38,entity():toWorld(vec(-47,0,-4)),vec(0.1,0.1,0.1),entity():toWorld(ang(0,0,0)),vec(255,255,255),"cube") holoParent(38,16) holoAlpha(38,0) #hinge
    holoCreate(39,entity():toWorld(vec(-47,0,-4)),vec(0.3,0.3,0.5),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(39,38)
    
    }
elseif(!holoEntity(40) && holoCanCreate()  & T>2000)
{
    holoCreate(40,entity():toWorld(vec(-47.5,2.3,-13)),vec(0.45,0.1,1.5),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(40,38)
    holoCreate(41,entity():toWorld(vec(-46.5,2.3,-4)),vec(0.4,0.1,0.5),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(41,38)
    holoCreate(42,entity():toWorld(vec(-48.9,2.3,-2.49)),vec(0.22,0.1,0.25),entity():toWorld(ang(0,0,0)),Red,"prism") holoParent(42,38)
    holoCreate(43,entity():toWorld(vec(-48.9,2.3,-24.4)),vec(0.22,0.1,0.4),entity():toWorld(ang(180,0,0)),Red,"prism") holoParent(43,38)
    holoCreate(44,entity():toWorld(vec(-47.15,2.3,-24.4)),vec(0.3,0.1,0.4),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(44,38)
    holoCreate(45,entity():toWorld(vec(-45,2.3,-23)),vec(0.3,0.1,0.4),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(45,38)
    holoCreate(46,entity():toWorld(vec(-47.5,2.43,-10)),vec(0.08,0.1,0.8),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(46,38)
    holoCreate(47,entity():toWorld(vec(-48.89,2.43,-14.95)),vec(0.3,0.1,0.08),entity():toWorld(ang(-20,0,0)),Dark,"cube") holoParent(47,38)
    
    holoCreate(48,entity():toWorld(vec(-47.5,-2.3,-13)),vec(0.45,0.1,1.5),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(48,38)
    holoCreate(49,entity():toWorld(vec(-46.5,-2.3,-4)),vec(0.4,0.1,0.5),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(49,38)
    }
elseif(!holoEntity(50) && holoCanCreate()  & T>3000)
{
    holoCreate(50,entity():toWorld(vec(-48.9,-2.3,-2.49)),vec(0.22,0.1,0.25),entity():toWorld(ang(0,0,0)),Red,"prism") holoParent(50,38)
    holoCreate(51,entity():toWorld(vec(-48.9,-2.3,-24.4)),vec(0.22,0.1,0.4),entity():toWorld(ang(180,0,0)),Red,"prism") holoParent(51,38)
    holoCreate(52,entity():toWorld(vec(-47.15,-2.3,-24.4)),vec(0.3,0.1,0.4),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(52,38)
    holoCreate(53,entity():toWorld(vec(-45,-2.3,-23)),vec(0.3,0.1,0.4),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(53,38)
    holoCreate(54,entity():toWorld(vec(-47.5,-2.43,-10)),vec(0.08,0.1,0.8),entity():toWorld(ang(0,0,0)),Dark,"cube") holoParent(54,38)
    holoCreate(55,entity():toWorld(vec(-48.89,-2.43,-14.95)),vec(0.3,0.1,0.08),entity():toWorld(ang(-20,0,0)),Dark,"cube") holoParent(55,38)
    
    #Outer edge
    holoCreate(56,Base:toWorld(vec(-56,0,12)),vec(0.8,3,1.4),entity():toWorld(ang(106,180,0)),Dark,"cube") holoParent(56,38)
    holoModel(56,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(36,"models/debug/debugwhite")
    holoClipEnabled(56,1)
    holoClip(56,vec(17,0,0),vec(1,0,1),0)
    holoCreate(57,entity():toWorld(vec(-47,0,-25)),vec(0.1,0.1,0.1)) holoParent(57,38) holoAlpha(57,0)

    #Arms pt2
    holoCreate(58,entity():toWorld(vec(-51,1.5,-16.85)),vec(0.8,1.8,1),entity():toWorld(ang(115,180,0)),Red,"cube") holoParent(58,57)
    holoModel(58,"models/weapons/c_models/c_machete/c_machete.mdl") holoMaterial(58,"models/debug/debugwhite")
    holoClipEnabled(58,1)
    holoClip(58,vec(10,0,0),vec(1,0,0),0)
    holoCreate(59,entity():toWorld(vec(-51,-1.5,-16.85)),vec(0.8,1.8,1),entity():toWorld(ang(115,180,0)),Red,"cube") holoParent(59,57)
    holoModel(59,"models/weapons/c_models/c_machete/c_machete.mdl") holoMaterial(59,"models/debug/debugwhite")
    holoClipEnabled(59,1)
    holoClip(59,vec(10,0,0),vec(1,0,0),0)   
    }
elseif(!holoEntity(60) && holoCanCreate()  & T>4000)
{
    holoCreate(60,entity():toWorld(vec(-44,0,-40)),vec(0.1,0.1,0.1)) holoParent(60,57) holoAlpha(60,0) # hinge
    holoCreate(61,entity():toWorld(vec(-42.5,0,-41.5)),vec(0.55,0.55,0.6),entity():toWorld(ang(0,0,90)),Light,"hq_torus") holoParent(61,60)
    holoCreate(62,entity():toWorld(vec(-42.5,0,-41.5)),vec(0.5,0.5,0.1),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(62,60)
    holoCreate(63,entity():toWorld(vec(-50,0,-12)),vec(0.8,1,1.7),entity():toWorld(ang(106,180,0)),Dark,"cube") holoParent(63,60)
    holoModel(63,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(63,"models/debug/debugwhite")
    holoClipEnabled(63,1)
    holoClip(63,vec(31,0,0),vec(1,0,0.3),0)
    holoCreate(64,entity():toWorld(vec(-48,0,-12)),vec(0.8,0.8,1.65),entity():toWorld(ang(104,180,0)),Light,"cube") holoParent(64,60)
    holoModel(64,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(64,"models/debug/debugwhite")
    holoClipEnabled(64,1)
    holoClip(64,vec(31,0,0),vec(1,0,0.3),0)
    
    #Inner blades
    holoCreate(65,entity():toWorld(vec(-50,2,60)),vec(1.5,0.3,3.9),entity():toWorld(ang(100,180,0)),Light,"cube") holoParent(65,38)
    holoModel(65,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(65,"models/debug/debugwhite")
    holoClipEnabled(65,1,1)
    holoClipEnabled(65,2,1)
    holoClip(65,1,vec(70,0,0),vec(1,0,0.3),0)
    holoClip(65,2,vec(89,0,0),vec(-1,0,0),0)
    holoCreate(66,entity():toWorld(vec(-45,2,48)),vec(1.2,0.2,3.6),entity():toWorld(ang(90,0,0)),Light,"cube") holoParent(66,38)
    holoModel(66,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(66,"models/debug/debugwhite")
    holoClipEnabled(66,1,1)
    holoClipEnabled(66,2,1)
    holoClip(66,1,vec(70,0,0),vec(1,0,0.3),0)
    holoClip(66,2,vec(89,0,0),vec(-1,0,0),0)
    holoCreate(67,entity():toWorld(vec(-50,-2,60)),vec(1.5,0.3,3.9),entity():toWorld(ang(100,180,0)),Light,"cube") holoParent(67,38)
    holoModel(67,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(67,"models/debug/debugwhite")
    holoClipEnabled(67,1,1)
    holoClipEnabled(67,2,1)
    holoClip(67,1,vec(70,0,0),vec(1,0,0.3),0)
    holoClip(67,2,vec(89,0,0),vec(-1,0,0),0)
    holoCreate(68,entity():toWorld(vec(-45,-2,48)),vec(1.2,0.2,3.6),entity():toWorld(ang(90,0,0)),Light,"cube") holoParent(68,38)
    holoModel(68,"models/weapons/c_models/c_croc_knife/c_croc_knife.mdl") holoMaterial(68,"models/debug/debugwhite")
    holoClipEnabled(68,1,1)
    holoClipEnabled(68,2,1)
    holoClip(68,1,vec(70,0,0),vec(1,0,0.3),0)
    holoClip(68,2,vec(89,0,0),vec(-1,0,0),0)
    holoCreate(69,entity():toWorld(vec(-37,0,0)),0*vec(0.2,1,0.2),entity():toWorld(ang(0,0,0)),vec(255,255,255),"cube") holoParent(69,16) #hinge
        }
elseif(!holoEntity(70) && holoCanCreate()  & T>5000)
{
    holoCreate(70,entity():toWorld(vec(-42,1.5,-4)),vec(0.5,0.05,1.3),entity():toWorld(ang(50,0,0)),Red,"cube") holoParent(70,69)
    holoCreate(71,entity():toWorld(vec(-42,-1.5,-4)),vec(0.5,0.05,1.3),entity():toWorld(ang(50,0,0)),Red,"cube") holoParent(71,69)
    holoCreate(72,Base:toWorld(vec(12.9,0,1)),0.15*vec(1,1,1),Base:toWorld(ang(0,0,90)),Dark,"hqtorus") holoParent(72,Base)
    holoCreate(73,Base:toWorld(vec(-7,0,0)),vec(1,0.2,0.3),entity():toWorld(ang(0,0,0)),Red,"cube") holoParent(73,Base)
    holoCreate(74,Base:toWorld(vec(-9,5,0.9)),vec(0.15,0.15,0.7),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(74,Base)
    
    holoParent(-1,entity())
    #Hold = 2   #Uncomment this to pickup as soon as E2 is spawned    
}
elseif(!holoEntity(101) && !first() && holoCanCreate()  & T>6000)
{Trailer = holoCreate(101,Base:toWorld(vec(-33,0,0))) holoAlpha(101,0) holoParent(101,Base)
    #Extra bits
    
    holoCreate(75,entity():toWorld(vec(-42.3,2.3,-23)),vec(0.62,0.1,0.5),entity():toWorld(ang(90,0,0)),Red,"prism") holoParent(75,38) 
    holoClipEnabled(75,1) holoClip(75,vec(0,0,-0.9),vec(0,0,-1),0)
    
    holoCreate(76,entity():toWorld(vec(-42.3,-2.3,-23)),vec(0.62,0.1,0.5),entity():toWorld(ang(90,0,0)),Red,"prism") holoParent(76,38) 
    holoClipEnabled(76,1) holoClip(76,vec(0,0,-0.9),vec(0,0,-1),0)
    
    holoCreate(77,entity():toWorld(vec(-46,2.35,-23)),vec(0.08,0.08,0.1),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(77,38)
    holoCreate(78,entity():toWorld(vec(-44.5,2.35,-21.8)),vec(0.08,0.08,0.1),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(78,38)
    holoCreate(79,entity():toWorld(vec(-44.5,2.35,-24.2)),vec(0.08,0.08,0.1),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(79,38)
    
    holoCreate(80,entity():toWorld(vec(-46,-2.35,-23)),vec(0.08,0.08,0.1),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(80,38)
    holoCreate(81,entity():toWorld(vec(-44.5,-2.35,-21.8)),vec(0.08,0.08,0.1),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(81,38)
    holoCreate(82,entity():toWorld(vec(-44.5,-2.35,-24.2)),vec(0.08,0.08,0.1),entity():toWorld(ang(0,0,90)),Dark,"cylinder") holoParent(82,38)
    T=0
    
    Hold = 2
    }
else
{
#These weapons can be changed if you have a more suitable SWEP to use, such as blank sweps
if(PlayerTarget:weapon():type() == "weapon_crowbar")
{Hold = 1 PlayerTarget:weapon():setAlpha(0)}
elseif(PlayerTarget:weapon():type() == "weapon_crossbow")
{Hold = 2 PlayerTarget:weapon():setAlpha(0)}
 else
{Hold = 0 PlayerTarget:weapon():setAlpha(255)}

#BLADE mode
if($Hold){
    if(Hold==1)
    {   soundPitch(1,70)
        Base:soundPlay(1,0,"weapons/ump45/ump45_boltslap.wav")
        holoPos(-1,PlayerTarget:attachmentPos("anim_attachment_RH"))
        holoAng(-1,PlayerTarget:attachmentAng("anim_attachment_RH"))
        holoParentAttachment(-1,PlayerTarget,"anim_attachment_RH")
        holoAng(0,Pivot:toWorld(ang(90,180,0)))
        holoPos(0,Pivot:toWorld(vec(0,0,20)))
        #Don't do this at home kids, this is inefficient and bad
        holoAlpha(65,255) holoAlpha(66,255) holoAlpha(67,255) holoAlpha(68,255)
        holoAlpha(56,255) holoAlpha(23,255) holoAlpha(34,255) holoAlpha(35,255) holoAlpha(36,255) holoAlpha(37,255) holoAlpha(12,255) holoAlpha(13,255)
        holoAlpha(14,255) holoAlpha(15,255) holoAlpha(6,255) holoAlpha(7,255) holoAlpha(10,255) holoAlpha(11,255) holoAlpha(74,255) holoAlpha(231,255)
        
        holoScale(3,vec(1.6,0.3,0.1)) holoScale(4,vec(0.3,0.3,0.05)) holoScale(0,vec(2,0.2,0.3))    
        holoPos(72,Base:toWorld(vec(12.9,0,1)))
        
        holoAlpha(8,255)
        holoPos(8,Base:toWorld(vec(35,0,-0.8)))
        holoScale(8,vec(0.25,0.1,0.2))
        
        holoAlpha(9,255)
        holoPos(9,Base:toWorld(vec(37.7,0,-0.8)))
        holoAng(9,Base:toWorld(ang(0,0,0)))
        holoScale(9,vec(0.2,0.05,0.2))    
        
        Anim = 0
    }
    #GUN mode
    elseif(Hold==2)
    {
        soundPitch(1,70)
        Base:soundPlay(1,0,"weapons/ump45/ump45_clipin.wav")
        holoPos(-1,PlayerTarget:attachmentPos("anim_attachment_RH"))
        holoAng(-1,PlayerTarget:attachmentAng("anim_attachment_RH"))
        holoParentAttachment(-1,PlayerTarget,"anim_attachment_RH")
        holoAng(0,Pivot:toWorld(ang(0,180,0)))
        holoPos(0,Pivot:toWorld(vec(13,-0.8,4)))
        
        holoAlpha(65,0) holoAlpha(66,0) holoAlpha(67,0) holoAlpha(68,0)
        holoAlpha(56,0) holoAlpha(23,0) holoAlpha(231,0) holoAlpha(74,255)
        holoAlpha(34,0) holoAlpha(35,0) holoAlpha(36,0) holoAlpha(37,0)
        holoAlpha(12,255) holoAlpha(13,255) holoAlpha(14,255) holoAlpha(15,255)
        holoAlpha(6,255) holoAlpha(7,0) holoAlpha(10,0) holoAlpha(11,0)
        holoScale(3,vec(1.6,0.15,0.4)) holoScale(4,vec(0,0,0))
        holoScale(0,vec(2,0.2,0.3))
        holoPos(72,Base:toWorld(vec(12.9,0,1)))
        
        #Barrel
        holoAlpha(8,255)
        holoPos(8,Base:toWorld(vec(18.5,0,-2.8)))
        holoScale(8,vec(0.15,0.2,0.5))
    
        holoAlpha(9,255)
        holoPos(9,Base:toWorld(vec(12,0,-4)))
        holoAng(9,Base:toWorld(ang(-30,0,0)))
        holoScale(9,vec(0.1,0.1,0.5))  
        
        Anim = 100
    }
    
    #CARRY mode
    elseif(!Hold)
    {
        soundPitch(1,70)
        Base:soundPlay(1,0,"weapons/ump45/ump45_clipout.wav")
        
        holoPos(-1,PlayerTarget:attachmentPos("chest"))
        holoAng(-1,PlayerTarget:attachmentAng("chest"))
        holoParentAttachment(-1,PlayerTarget,"chest")
        holoAng(0,Pivot:toWorld(ang(20,-90,0)))
        holoPos(0,Pivot:toWorld(vec(-10,-15,-7)))
        #Oh my god seriously find a better way than manually holo-alpha-ing each part
        holoAlpha(65,0) holoAlpha(66,0) holoAlpha(67,0) holoAlpha(68,0) holoAlpha(56,0)
        holoAlpha(23,0) holoAlpha(231,0) holoAlpha(74,0) holoAlpha(34,0) holoAlpha(35,0)
        holoAlpha(36,0) holoAlpha(37,0) holoAlpha(12,0) holoAlpha(13,0) holoAlpha(14,0)
        holoAlpha(15,0) holoAlpha(6,0) holoAlpha(7,0) holoAlpha(10,0) holoAlpha(11,0)
        holoScale(3,vec(1.6,0.15,0.4))
        holoScale(4,vec(0,0,0))
        holoScale(0,vec(0.4,0.2,0.3))
        holoPos(72,Base:toWorld(vec(3.4,0,1)))
        
        holoAlpha(8,255)
        holoPos(8,Base:toWorld(vec(3.2,0,-3.2)))
        holoScale(8,vec(0.15,0.15,0.5))
        
        holoAlpha(9,0)
        Anim = 100   
    }
}

#Animation
if(SMAnim<Anim){SMAnim+=5}
if(SMAnim>Anim){SMAnim-=5} 
if(Trailer){        #this is to make sure we've finished spawning every hologram before moving them
holoAng(21,Base:toWorld(ang(15 + (0.75*SMAnim),0,0))) #Rear bridge hinge
holoAng(25,Base:toWorld(ang(-10 + (1.9*SMAnim),0,0))) #Top segments hinge
holoAng(33,Base:toWorld(ang(20 + (0.3*SMAnim),0,0))) #Blades hinge
holoAng(38,Base:toWorld(ang(-10 - (0.8*SMAnim),0,0))) #Big arm hinge
holoAng(57,Base:toWorld(ang(-20 - (2.4*SMAnim),0,0))) #Smaller arms hinge
holoAng(60,Base:toWorld(ang(-50 - (3.9*SMAnim),0,0))) #End circle blade hinge
holoAng(69,Base:toWorld(ang(0 - (1.4*SMAnim),0,0))) #Inner flaps hinge
holoPos(16,Base:toWorld(vec(-40 + (0.2 * SMAnim),0,0)))
}
#Firing in gun mode
M1 = PlayerTarget:keyAttack1()

if(Hold==2 & $M1 & M1 & Cd == 0) {
    Cd=50    
    Base:soundPlay(2,0,"weapons/sg552/sg552-1.wav")
    soundPitch(2,80)
    Trailer:setTrails(1,1,0.2,"trails/smoke",vec(255,255,255),255) 
    
    #ifdef entity:setVelocity(vector)
        PlayerTarget:setVelocity(-PlayerTarget:eye()*350)
    #endif
    #ifdef entity:propBreak()
        PlayerTarget:aimEntity():propBreak() #:takeDamage(100,PlayerTarget:aimPos(),PlayerTarget:eye()*PlayerTarget:aimEntity():mass())
    #endif
    #ifdef particle(number,number,number,string,vector,vector,vector)
        particle(0.1,20,15,"effects/muzzleflash" + randint(1,4),vec(255,255,255),Base:toWorld(vec(-35,0,0)),vec(0,0,0))
    #endif
    
    }
        
if(Cd>0)
    {
        Cd--   
        if(Cd>=47)
        {
          holoUnparent(101)
          holoPos(101,PlayerTarget:aimPos())    
        }
        if(Cd<20 && Cd>10){
            holoPos(74,Base:toWorld(vec(-9 + 6,5,0.9)))
                if(Cd==19)
                {
                    Base:soundPlay(3,0,"weapons/sg552/sg552_boltpull.wav")
                    soundPitch(3,80)
                }
            }
            else
            {
                holoPos(74,Base:toWorld(vec(-9,5,0.9)))
            }
    }
    if(Cd==1)
    {
        holoEntity(101):removeTrails()
        holoPos(101,Base:toWorld(vec(-33,0,0))) holoParent(101,Base) 
    }

    if(owner():keyAttack1() && owner():lastSaid() == ":st")
    {
        PlayerTarget = owner():aimEntity()
        print("Target set!")                    #In case you wanna stick it on someone else
    }
}
