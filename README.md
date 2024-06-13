# InteractionSystem
General simple interaction component-based system. With using two components ISTriggerComponent and ISReceiverComponent you can easily trigger any actors abilities in level. Part of TypicoGames plugin system. Usage of IS found in TransformChanger, PalleteSwitcher, BoidSystem, etc.

- collision definitions for different interactions 


## ISReceiverComponent

- place this to any actor 
- define OnAction1, OnAction2, etc. events in Blueprint (e.g. InAction1 - enable gravity, OnAction2 - disable gravity)


## ISTriggerComponent
- place on Actor and call ActivateInteraction, whenever you want to implement triggering interaction. 
- use some of defined TriggerActors (BoxTrigger, HitTrigger, IntervalTrigger) 



## Existing trigger reference

### BoxTrigger
- box where trigger is made by overlaping 
### HitTrigger
- Mesh that triggers on HitCollision 
### IntervalTrigger 
- Both TRIGGER and RECEIVER 
- define intervals of triggering 

### Make your own trigger
- have some fancy system? (e.g. cool rocket laucher? add TriggerComponent and define it on shooting! use that trigger for spawning enemies ) 

## Use Cases 
- ThunderEffect: Trigger + PalleteSwitcher + AudioPlayer 
- Magic Stairs: Trigger + TransformChanger 
- Day & Night cycle: IntervalTrigger + PalleteSwitcher + <ThunderEffect>
- Health Indication: Health trigger + PalleteSwitcher + AudioPlayer 
- Megic Harry Potter stairs: Interval Trigger + AxisRotator + TransformChanger
- AsteroidSystem: TrigonometricMover 
- Morphing Asteroid System: Trigonometric Mover + Transform Changer 
- Health Systems: player can define death on trigger from enemy AI 

