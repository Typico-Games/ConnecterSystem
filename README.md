# InteractionSystem
Simple, general all-purpose interaction system used with a set of plugins developed by Typico Games.

## BoxTrigger
`AISBoxTrigger` is a critical component of the `InteractionSystem`, designed to facilitate player or object-triggered interactions within the game environment. This actor is highly configurable within the Unreal Editor and plays a pivotal role in activating various functionalities based on player interactions.

### Overview
`AISBoxTrigger` extends `AActor` and is geared towards initializing triggers and managing overlap events that activate different game functionalities. It features a plethora of configurable properties and editor-specific functions designed to enhance level design and streamline gameplay mechanics.

### Features
- **Dynamic Overlap Events**: Capable of detecting entries and exits in the trigger area, allowing for dynamic interaction responses.
- **Configurable Interaction Targets**: Supports configuration of specific actions triggered by interacting objects during overlap events.
- **Enhanced Editor Tools**: Provides robust tools for configuring trigger parameters directly within the Unreal Editor, facilitating a seamless design workflow.

### Usage
To use `AISBoxTrigger` in your game:
1. Add the `AISBoxTrigger` actor to the desired location within your game world.
2. Adjust the `ActivationCollision` box component to set the physical boundaries of the trigger area.
3. Configure the interaction targets and associated rules via the properties panel in the Unreal Editor.

### Properties
- **MainRoot**: Serves as the primary root component of the trigger.
- **ActivationCollision**: Defines the spatial boundaries of the trigger area through a box component.
- **InteractionTargets_BeginOverlap** and **InteractionTargets_EndOverlap**: Lists of interaction targets for beginning and ending overlap events.
- **bInfiniteHits_BeginOverlap** and **bInfiniteHits_EndOverlap**: Toggle to allow infinite or finite trigger activations.
- **DisableAfterHits_BeginOverlap** and **DisableAfterHits_EndOverlap**: Set the number of activations before the trigger is disabled.
- **bTestInteraction_BeginOverlap** and **bTestInteraction_EndOverlap**: Enables testing interactions without affecting gameplay.

### Editor Configuration
#### Begin Overlap Configuration
- **AddGroupToConfiguration_BeginOverlap**: Adds a predefined group of actors to the configuration for begin overlap events.
- **GroupActorSelection_BeginOverlap**: Allows selection of a group actor whose children will be configured for begin overlap interactions.

#### End Overlap Configuration
- **AddGroupToConfiguration_EndOverlap**: Similar functionality for end overlap configurations, allowing addition of a predefined group of actors.
- **GroupActorSelection_EndOverlap**: Selects a group actor for configuring children in end overlap interactions.

### Development Tools
`AISBoxTrigger` includes blueprint-callable functions for rapid configuration and testing in the Unreal Editor:
- **DuplicateConfiguration**: Duplicates current settings to another instance.
- **AddGroupToConfiguration_BeginOverlap**: Adds all children of a selected group actor to the begin overlap interaction targets.
- **AddGroupToConfiguration_EndOverlap**: Similar functionality for end overlap interaction targets.


## HitTrigger

`AISHitTrigger` is an essential component of the `InteractionSystem`, designed to detect and respond to physical impacts within the game environment. This actor allows for dynamic interaction management and is highly configurable within the Unreal Editor to suit various gameplay needs.

### Overview
`AISHitTrigger` extends `AActor` and specializes in managing and responding to collision-based events. It is equipped with configurable properties and editor-specific functions that enable precise control over how interactions are triggered and managed upon physical impacts.

### Features
- **Collision Detection**: Detects collisions and triggers configured interactions based on those events.
- **Dynamic Interaction Response**: Allows for real-time management of game mechanics in response to detected hits.
- **Configurable Sound and Visual Feedback**: Integrates audio and visual components to enhance interaction feedback.

### Usage
To implement `AISHitTrigger` in your game:
1. Place the `AISHitTrigger` actor within your game world where interactions should occur upon collision.
2. Configure the `HitTriggerMesh` to visually represent the trigger area.
3. Attach the `HitTriggerSound` to provide audio feedback upon interactions.

### Properties
- **MainRoot**: The primary root component of the trigger.
- **HitTriggerMesh**: A static mesh component that visually represents the trigger area.
- **HitTriggerSound**: An audio component that plays sounds when the trigger is activated.

### Interaction Configuration
- **InteractionTargets**: Specifies the targets that this trigger can interact with upon collision.
- **bInfiniteHits**: When enabled, allows unlimited interactions; otherwise, interaction count is limited by `DisableAfterHits`.
- **DisableAfterHits**: Limits the number of times interactions can be triggered when `bInfiniteHits` is false.
- **CurrentHits**: Displays the current count of how many times interactions have been triggered.

### Editor Functions
`AISHitTrigger` includes several blueprint-callable functions that facilitate rapid configuration and testing within the Unreal Editor:
- **AddGroupToConfiguration**: Adds a predefined group of actors to the trigger configuration, allowing for batch configuration of interaction targets.

### Development Tools
In the Unreal Editor, developers can use blueprint-callable functions to quickly adjust trigger settings and test interactions without the need for compiling scripts:
- **OnHitTriggerHit**: Function to handle logic when a collision occurs.
- **ActivateInteractions**: Activates the interactions defined for the hit trigger.

