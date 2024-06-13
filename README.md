# InteractionSystem
General simple interaction component-based system. With using two components ISTriggerComponent and ISReceiverComponent you can easily trigger any actors abilities in level. Part of TypicoGames plugin system. Usage of IS found in TransformChanger, PalleteSwitcher, BoidSystem, etc.

## ISReceiverComponent

- place this to any actor 
- define OnAction1, OnAction2, etc. events in Blueprint (e.g. InAction1 - enable gravity, OnAction2 - disable gravity)


## ISTriggerComponent
- use some of defined triggers to Trigger actions from actors possessing ReceiverComponent 


## Use Cases 
- ThunderEffect: Trigger + PalleteSwitcher + AudioPlayer 
- Magic Stairs: Trigger + TransformChanger 
- Day & Night cycle: IntervalTrigger + PalleteSwitcher + <ThunderEffect>


