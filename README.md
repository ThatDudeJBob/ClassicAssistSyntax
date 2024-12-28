# ClassicAssistSyntax
a Markdown Doc on the Classic Assist Scripting Syntax Compiled into a single file.


## Abilities  
### ActiveAbility  
  
Method Signature:  
  
**Boolean ActiveAbility()**  
  
Description:  
  
**Returns True if either the primary or secondary ability is set**  
  
Example:  
  
```python  
if not ActiveAbility():
 SetAbility("primary", "on")  
```  
  
### ClearAbility  
  
Method Signature:  
  
**Void ClearAbility()**  
  
Description:  
  
**Clear weapon ability.**  
  
Example:  
  
```python  
ClearAbility()  
```  
  
### Fly  
  
Method Signature:  
  
**Void Fly()**  
  
Description:  
  
**(Garoyle) Start flying if not already flying.**  
  
Example:  
  
```python  
Fly()  
```  
  
### Flying  
  
Method Signature:  
  
**Boolean Flying(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if mobile is currently flying.**  
  
Example:  
  
```python  
if Flying("self"):  
```  
  
### Land  
  
Method Signature:  
  
**Void Land()**  
  
Description:  
  
**(Garoyle) Stop flying if currently flying.**  
  
Example:  
  
```python  
Land()  
```  
  
### SetAbility  
  
Method Signature:  
  
**Void SetAbility(System.String, System.String)**  
  
#### Parameters  
* ability: The name of the ability, "primary", "secondary", "stun" or "disarm".  
* onoff: "on" or "off". (Optional)  
  
Description:  
  
**Set weapon ability, parameter "primary" / "secondary".**  
  
Example:  
  
```python  
SetAbility("primary")  
```  
  

## Actions  
### Attack  
  
Method Signature:  
  
**Void Attack(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Attack mobile (parameter can be serial or alias).**  
  
Example:  
  
```python  
Attack("last")  
```  
  
### BandageSelf  
  
Method Signature:  
  
**Boolean BandageSelf()**  
  
Description:  
  
**Applies a bandage to the player.**  
  
Example:  
  
```python  
BandageSelf()  
```  
  
### ClearHands  
  
Method Signature:  
  
**Void ClearHands(System.String)**  
  
#### Parameters  
* hand: Hand - "left", "right", or "both". (Optional)  
  
Description:  
  
**Clear hands, "left", "right", or "both"**  
  
Example:  
  
```python  
ClearHands("both")  
```  
  
### ClearUseOnce  
  
Method Signature:  
  
**Void ClearUseOnce()**  
  
Description:  
  
**Clear UseOnce list.**  
  
Example:  
  
```python  
ClearUseOnce()  
```  
  
### ClickObject  
  
Method Signature:  
  
**Void ClickObject(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Single click object (parameter can be serial or alias).**  
  
Example:  
  
```python  
ClickObject("last")  
```  
  
### Contents  
  
Method Signature:  
  
**Int32 Contents(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns the item count for given container.**  
  
Example:  
  
```python  
if Contents("backpack") > 120:  
```  
  
### ContextMenu  
  
Method Signature:  
  
**Void ContextMenu(System.Object, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* entry: Context menu entry index number.  
  
Description:  
  
**Request a context menu option.**  
  
Example:  
  
```python  
ContextMenu(0x00aabbcc, 1)  
```  
  
### EquipItem  
  
Method Signature:  
  
**Void EquipItem(System.Object, System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* layer: String representing a layer, such as "OneHanded" or "Talisman" etc. See Also: [Layer](#Layer)  
  
Description:  
  
**Equip a specific item into a given layer. Use object inspector to determine layer value.**  
  
Example:  
  
```python  
EquipItem("axe", "TwoHanded")  
```  
  
### EquipLastWeapon  
  
Method Signature:  
  
**Void EquipLastWeapon()**  
  
Description:  
  
**Send quick switch weapon packet (probably not supported on pre-AoS servers.**  
  
Example:  
  
```python  
EquipLastWeapon()  
```  
  
### EquipType  
  
Method Signature:  
  
**Void EquipType(Int32, System.Object)**  
  
#### Parameters  
* id: ItemID / Graphic such as  0x3db.  
* layer: String representing a layer, such as "OneHanded" or "Talisman" etc. See Also: [Layer](#Layer)  
  
Description:  
  
**Equip a specific type into a given layer. Use object inspector to determine layer value.**  
  
Example:  
  
```python  
EquipType(0xff, "TwoHanded")  
```  
  
### Feed  
  
Method Signature:  
  
**Void Feed(System.Object, Int32, Int32, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* graphic: ItemID / Graphic such as  0x3db.  
* amount: Integer representing an amount, ie 10. (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
  
Description:  
  
**Feed a given alias or serial with graphic.**  
  
Example:  
  
```python  
Feed("mount", 0xff)  
```  
  
### FindLayer  
  
Method Signature:  
  
**Boolean FindLayer(System.Object, System.Object)**  
  
#### Parameters  
* layer: String representing a layer, such as "OneHanded" or "Talisman" etc. See Also: [Layer](#Layer)  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns true and updates found alias if an item exists in the specified layer, option serial/alias for mobile to check.**  
  
Example:  
  
```python  
if FindLayer("OneHanded"):  
```  
  
### InRegion  
  
Method Signature:  
  
**Boolean InRegion(System.String, System.Object)**  
  
#### Parameters  
* attribute: String value - See description for usage. See Also: [RegionAttributes](#RegionAttributes)  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the region of the target has the specified attribute.**  
  
Example:  
  
```python  
if InRegion("Guarded", "self")  
```  
  
### Ping  
  
Method Signature:  
  
**Int64 Ping()**  
  
Description:  
  
**Retrieve an approximated ping with server. -1 on failure.**  
  
Example:  
  
```python  
Ping()  
```  
  
### Rename  
  
Method Signature:  
  
**Void Rename(System.Object, System.String)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* name: String representing a name, ie "Snoopy".  
  
Description:  
  
**Sends rename request.**  
  
Example:  
  
```python  
Rename("mount", "Snoopy")  
```  
  
### ShowNames  
  
Method Signature:  
  
**Void ShowNames(System.String)**  
  
#### Parameters  
* showtype: Show type - "mobiles" or "corpses". See Also: [ShowNamesType](#ShowNamesType)  
  
Description:  
  
**Display corpses and/or mobiles names (parameter "mobiles" or "corpses".**  
  
Example:  
  
```python  
ShowNames("corpses")  
```  
  
### ToggleMounted  
  
Method Signature:  
  
**Void ToggleMounted()**  
  
Description:  
  
**Unmounts if mounted, or mounts if unmounted, will prompt for mount if no "mount" alias.**  
  
Example:  
  
```python  
ToggleMounted()  
```  
  
### UseObject  
  
Method Signature:  
  
**Void UseObject(System.Object, Boolean)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* skipqueue: Not specified - See description for usage. (Optional)  
  
Description:  
  
**Sends use (doubleclick) request for given object (parameter can be serial or alias).**  
  
Example:  
  
```python  
UseObject("mount")  
```  
  
### UseOnce  
  
Method Signature:  
  
**Boolean UseOnce(Int32, Int32)**  
  
#### Parameters  
* graphic: ItemID / Graphic such as  0x3db.  
* hue: Item Hue or -1 for any. (Optional)  
  
Description:  
  
**Use a specific item type (graphic) from your backpack, only once**  
  
Example:  
  
```python  
UseOnce(0xff)  
```  
  
### UseTargetedItem  
  
Method Signature:  
  
**Void UseTargetedItem(System.Object, System.Object)**  
  
#### Parameters  
* item: An entity serial in integer or hex format, or an alias string such as "self".  
* target: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Uses specified item and targets target in one action. Requires server support (OSI / ServUO)**  
  
Example:  
  
```python  
UseTargetedItem('bandage', 'pet')  
```  
  
### UseType  
  
Method Signature:  
  
**Void UseType(System.Object, Int32, System.Object, Boolean)**  
  
#### Parameters  
* type: An entity serial in integer or hex format, or an alias string such as "self".  
* hue: Item Hue or -1 for any. (Optional)  
* container: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
* skipqueue: Not specified - See description for usage. (Optional)  
  
Description:  
  
**Sends use (doubleclick) request for given type, optional parameters of hue and container object (defaults to player backpack) (parameters can be serial or alias).**  
  
Example:  
  
```python  
UseType(0xff)  
```  
  
### WaitForContents  
  
Method Signature:  
  
**Boolean WaitForContents(System.Object, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* timeout: Timeout specified in milliseconds. (Optional)  
  
Description:  
  
**Wait for container contents for given container.**  
  
Example:  
  
```python  
WaitForContents("backpack", 5000)  
```  
  
### WaitForContext  
  
Method Signature:  
  
**Boolean WaitForContext(System.Object, Int32, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* entry: Context menu entry index number.  
* timeout: Timeout specified in milliseconds.  
  
Description:  
  
**Request or wait for a context menu option.**  
  
Example:  
  
```python  
# select by index number
WaitForContext('self', 2, 5000)
# select by entry name
WaitForContext('self', "Open Item Insurance Menu", 5000)  
```  
  
### WaitForContext  
  
Method Signature:  
  
**Boolean WaitForContext(System.Object, System.String, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* entryname: String value - See description for usage.  
* timeout: Timeout specified in milliseconds.  
  
Description:  
  
**Request or wait for a context menu option.**  
  
Example:  
  
```python  
# select by index number
WaitForContext('self', 2, 5000)
# select by entry name
WaitForContext('self', "Open Item Insurance Menu", 5000)  
```  
  



## Types  
### Layer  
* Invalid  
* OneHanded  
* TwoHanded  
* Shoes  
* Pants  
* Shirt  
* Helm  
* Gloves  
* Ring  
* Talisman  
* Neck  
* Hair  
* Waist  
* InnerTorso  
* Bracelet  
* Unused_xF  
* FacialHair  
* MiddleTorso  
* Earrings  
* Arms  
* Cloak  
* Backpack  
* OuterTorso  
* OuterLegs  
* InnerLegs  
* Mount  
* ShopBuy  
* ShopResale  
* ShopSell  
* Bank  
* LastValid  
  
### RegionAttributes  
* None  
* Guarded  
* Jail  
* Wilderness  
* Town  
* Dungeon  
* Special  
* Default  
  
### ShowNamesType  
* Mobiles  
* Corpses  


## Agents  
### Autoloot  
  
Method Signature:  
  
**Void Autoloot(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Causes autoloot to check a particular container, even when not enabled, and bypassing the corpse type check**  
  
Example:  
  
```python  
Autoloot("found")  
```  
  
### Autolooting  
  
Method Signature:  
  
**Boolean Autolooting()**  
  
Description:  
  
**Returns True if currently checking corpse / autolooting items.**  
  
Example:  
  
```python  
if Autolooting():  
```  
  
### ClearTrapPouch  
  
Method Signature:  
  
**Void ClearTrapPouch()**  
  
Description:  
  
**Clears the items in the trap pouch agent...**  
  
Example:  
  
```python  
ClearTrapPouch()  
```  
  
### Counter  
  
Method Signature:  
  
**Int32 Counter(System.String)**  
  
#### Parameters  
* name: Agent entry name.  
  
Description:  
  
**Returns the count of the given counter agent.**  
  
Example:  
  
```python  
Counter("bm")  
```  
  
### Dress  
  
Method Signature:  
  
**Void Dress(System.String)**  
  
#### Parameters  
* name: Agent entry name. (Optional)  
  
Description:  
  
**Dress all items in the specified dress agent.**  
  
Example:  
  
```python  
Dress("Dress-1")  
```  
  
### DressConfig  
  
Method Signature:  
  
**Void DressConfig()**  
  
Description:  
  
**Adds all equipped items to a temporary list that isn't persisted on client close.**  
  
Example:  
  
```python  
DressConfig()  
```  
  
### Dressing  
  
Method Signature:  
  
**Boolean Dressing()**  
  
Description:  
  
**Returns true if the Dress agent is currently dressing or undressing.**  
  
Example:  
  
```python  
if Dressing():  
```  
  
### Organizer  
  
Method Signature:  
  
**Void Organizer(System.String, System.Object, System.Object)**  
  
#### Parameters  
* name: Agent entry name.  
* sourcecontainer: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
* destinationcontainer: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Executes the named Organizer agent.**  
  
Example:  
  
```python  
Organizer("Organizer-1")  
```  
  
### Organizing  
  
Method Signature:  
  
**Boolean Organizing()**  
  
Description:  
  
**Returns true if currently running an organizer agent, or false if not.**  
  
Example:  
  
```python  
if Organizing():  
```  
  
### SetAutolootContainer  
  
Method Signature:  
  
**Void SetAutolootContainer(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Sets the container for the Autoloot agent to put items into...**  
  
Example:  
  
```python  
SetAutolootContainer("backpack")  
```  
  
### SetOrganizerContainers  
  
Method Signature:  
  
**Void SetOrganizerContainers(System.String, System.Object, System.Object)**  
  
#### Parameters  
* entryname: Agent entry name.  
* sourcecontainer: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
* destinationcontainer: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Set the source and destination for the specified Organizer name**  
  
Example:  
  
```python  
SetOrganizerContainers("Organizer-1", "backpack", "bank")  
```  
  
### SetScavenger  
  
Method Signature:  
  
**Void SetScavenger(System.String)**  
  
#### Parameters  
* onoff: "on" or "off". (Optional)  
  
Description:  
  
**Enable/Disable/Toggle the Scavenger agent**  
  
Example:  
  
```python  
SetScavenger("off")  
```  
  
### SetTrapPouch  
  
Method Signature:  
  
**Void SetTrapPouch(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Adds the specified item to the trap pouch agent item list...**  
  
Example:  
  
```python  
ClearTrapPouch()

if FindType(0xe79, -1, 'backpack'):
    Cast('Magic Trap', 'found')
    SetTrapPouch('found')  
```  
  
### SetVendorBuyAutoBuy  
  
Method Signature:  
  
**Void SetVendorBuyAutoBuy(System.String, System.String)**  
  
#### Parameters  
* listname: List name.  
* onoff: "on" or "off". (Optional)  
  
Description:  
  
**Enables or disables autobuying of the specified vendor buy list name...**  
  
Example:  
  
```python  
# set on
SetVendorBuyAutoBuy("regs", "on")
# set off
SetVendorBuyAutoBuy("regs", "off")
# default will toggle
SetVendorBuyAutoBuy("regs")  
```  
  
### StopDress  
  
Method Signature:  
  
**Void StopDress()**  
  
Description:  
  
**Stops the dress agent is it is currently running**  
  
Example:  
  
```python  
StopDress()  
```  
  
### StopOrganizer  
  
Method Signature:  
  
**Void StopOrganizer()**  
  
Description:  
  
**Stops the organizer agent if currently running**  
  
Example:  
  
```python  
StopOrganizer()  
```  
  
### Undress  
  
Method Signature:  
  
**Void Undress(System.String)**  
  
#### Parameters  
* name: Agent entry name.  
  
Description:  
  
**Undress all items in the specified dress agent.**  
  
Example:  
  
```python  
Undress("Dress-1")  
```  
  
### UseTrapPouch  
  
Method Signature:  
  
**Void UseTrapPouch()**  
  
Description:  
  
**Uses the first item in the Trap Pouch agent list...**  
  
Example:  
  
```python  
UseTrapPouch()  
```  
  
## Aliases  
### FindAlias  
  
Method Signature:  
  
**Boolean FindAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Returns true if alias serial can be found on screen, false if not.**  
  
Example:  
  
```python  
if FindAlias("mount"):  
```  
  
### GetAlias  
  
Method Signature:  
  
**Int32 GetAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Gets the value of the given alias name.**  
  
Example:  
  
```python  
GetAlias("mount")  
```  
  
### GetPlayerAlias  
  
Method Signature:  
  
**Int32 GetPlayerAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Gets the value of the given alias name, for the current player.**  
  
Example:  
  
```python  
GetPlayerAlias("mount")  
```  
  
### PromptAlias  
  
Method Signature:  
  
**Int32 PromptAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Prompt with an in-game target cursor to supply value for given alias name.**  
  
Example:  
  
```python  
PromptAlias("mount")  
```  
  
### PromptMacroAlias  
  
Method Signature:  
  
**Int32 PromptMacroAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Prompt with an in-game target cursor to supply value for given alias name, alias is valid only in the current macro.**  
  
Example:  
  
```python  
PromptMacroAlias("mount")  
```  
  
### PromptPlayerAlias  
  
Method Signature:  
  
**Int32 PromptPlayerAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Prompt with an in-game target cursor to supply value for given alias name, for the current player.**  
  
Example:  
  
```python  
PromptPlayerAlias("mount")  
```  
  
### SetAlias  
  
Method Signature:  
  
**Void SetAlias(System.String, System.Object)**  
  
#### Parameters  
* aliasname: Alias name.  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Sets the value of the given alias name.**  
  
Example:  
  
```python  
SetAlias("mount", 0x40000001)  
```  
  
### SetMacroAlias  
  
Method Signature:  
  
**Void SetMacroAlias(System.String, System.Object)**  
  
#### Parameters  
* aliasname: Alias name.  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Sets the value of the given alias name, alias is valid only in the current macro.**  
  
Example:  
  
```python  
SetMacroAlias("mount", 0x40000001)  
```  
  
### SetPlayerAlias  
  
Method Signature:  
  
**Void SetPlayerAlias(System.String, System.Object)**  
  
#### Parameters  
* aliasname: Alias name.  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Sets the value of the given alias name, for the current player.**  
  
Example:  
  
```python  
SetPlayerAlias("mount", 0x40000001)  
```  
  
### UnsetAlias  
  
Method Signature:  
  
**Void UnsetAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Removes the alias name given.**  
  
Example:  
  
```python  
UnsetAlias("mount")  
```  
  
### UnsetPlayerAlias  
  
Method Signature:  
  
**Void UnsetPlayerAlias(System.String)**  
  
#### Parameters  
* aliasname: Alias name.  
  
Description:  
  
**Removes the alias name given, for the current player.**  
  
Example:  
  
```python  
UnsetPlayerAlias("mount")  
```  
  
## Entity  
### AddFriend  
  
Method Signature:  
  
**Int32 AddFriend(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Adds a mobile to friends list, will display target cursor if no serial/alias supplied.**  
  
Example:  
  
```python  
AddFriend()  
```  
  
### Ally  
  
Method Signature:  
  
**Boolean Ally(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the mobile's notoriety is Ally**  
  
Example:  
  
```python  
if Criminal("mount"):  
```  
  
### AutoColorPick  
  
Method Signature:  
  
**Void AutoColorPick(Int32)**  
  
#### Parameters  
* hue: Item Hue or -1 for any.  
  
Description:  
  
**Setup an automated reply to the incoming dye color gump, allowing you to define dye tubs color.
That command should be added prior to the action that opens the color pick gump.**  
  
Example:  
  
```python  
AutoColorPick(666)
UseObject('dyes')
WaitForTarget(1000)
Target('tub')  
```  
  
### BuffExists  
  
Method Signature:  
  
**Boolean BuffExists(System.String)**  
  
#### Parameters  
* name: Buff name.  
  
Description:  
  
**Check for a specific buff**  
  
Example:  
  
```python  
if BuffExists("Blood Oath"):  
```  
  
### BuffTime  
  
Method Signature:  
  
**Double BuffTime(System.String)**  
  
#### Parameters  
* name: Buff name.  
  
Description:  
  
**Returns milliseconds remaining for given buff name, or 0 if expired/not enabled.**  
  
Example:  
  
```python  
if not BuffExists('Enemy Of One') or BuffTime('Enemy Of One') < 5000:
    Cast('Enemy Of One')
  
```  
  
### ClearIgnoreList  
  
Method Signature:  
  
**Void ClearIgnoreList()**  
  
Description:  
  
**Clears the ignore list.**  
  
Example:  
  
```python  
ClearIgnoreList()  
```  
  
### ClearObjectQueue  
  
Method Signature:  
  
**Void ClearObjectQueue()**  
  
Description:  
  
**Clears all actions in action packet queue**  
  
Example:  
  
```python  
ClearObjectQueue()  
```  
  
### CountType  
  
Method Signature:  
  
**Int32 CountType(Int32, System.Object, Int32)**  
  
#### Parameters  
* graphic: ItemID / Graphic such as  0x3db.  
* source: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
  
Description:  
  
**Amount comparison of item type inside a container.**  
  
Example:  
  
```python  
CountType(0xff, "backpack")  
```  
  
### CountTypeGround  
  
Method Signature:  
  
**Int32 CountTypeGround(Int32, Int32, Int32)**  
  
#### Parameters  
* graphic: ItemID / Graphic such as  0x3db.  
* hue: Item Hue or -1 for any. (Optional)  
* range: Range, ie 10. (Optional)  
  
Description:  
  
**Amount comparison of item or mobile type on the ground.**  
  
Example:  
  
```python  
if CountGround(0xff, 0, 10) < 1:  
```  
  
### Criminal  
  
Method Signature:  
  
**Boolean Criminal(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the mobile's notoriety is Criminal**  
  
Example:  
  
```python  
if Criminal("mount"):  
```  
  
### Dead  
  
Method Signature:  
  
**Boolean Dead(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns true if given mobile is dead, false if not, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
if Dead("self"):  
```  
  
### Dex  
  
Method Signature:  
  
**Int32 Dex()**  
  
Description:  
  
**Returns the dexterity of the player**  
  
Example:  
  
```python  
if Str() < 100:  
```  
  
### DiffHits  
  
Method Signature:  
  
**Int32 DiffHits(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles difference between max and current hits, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
if DiffHits("self") > 50:  
```  
  
### DiffHitsPercent  
  
Method Signature:  
  
**Double DiffHitsPercent(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles different between max and currents hits as a percentage, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
if DiffHitsPercent("self") > 30: # 70% health  
```  
  
### DiffWeight  
  
Method Signature:  
  
**Int32 DiffWeight()**  
  
Description:  
  
**Returns the difference between max weight and weight.**  
  
Example:  
  
```python  
if DiffWeight() > 50:  
```  
  
### Direction  
  
Method Signature:  
  
**System.String Direction(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the Direction the given alias/serial is facing**  
  
Example:  
  
```python  
if Direction('enemy') == 'West':  
```  
  
### DirectionTo  
  
Method Signature:  
  
**System.String DirectionTo(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns the Direction the entity is in relative to the player.**  
  
Example:  
  
```python  
Run(DirectionTo("enemy"))  
```  
  
### Distance  
  
Method Signature:  
  
**Int32 Distance(Int32, Int32)**  
  
#### Parameters  
* x: X Coordinate.  
* y: Y Coordinate.  
  
Description:  
  
**Returns the distance to the given coordinates.**  
  
Example:  
  
```python  
location = (1000, 1000, 0)

while Distance(location[0], location[1]) > 2:
 Pathfind(location[0], location[1], location[2])
 Pause(1000)  
```  
  
### Distance  
  
Method Signature:  
  
**Int32 Distance(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the distance to the given entity.**  
  
Example:  
  
```python  
if Distance("mount") < 4:  
```  
  
### Enemy  
  
Method Signature:  
  
**Boolean Enemy(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the mobile's notoriety is Enemy**  
  
Example:  
  
```python  
if Criminal("mount"):  
```  
  
### EquipWand  
  
Method Signature:  
  
**Boolean EquipWand(System.String, Int32)**  
  
#### Parameters  
* wandname: Wand name. See Also: [WandTypes](#WandTypes)  
* minimumcharges: Integer value - See description for usage. (Optional)  
  
Description:  
  
**Search for a wand inside your backpack and equip it**  
  
Example:  
  
```python  
#Equip a fireball wand if one can be found in our backpack..
if FindWand("fireball", "backpack", 5):
 #Remove current item in hand
 if FindLayer("OneHanded"):
  ClearHands("left")
 #Equip the wand
 EquipWand("fireball")  
```  
  
### FasterCasting  
  
Method Signature:  
  
**Double FasterCasting()**  
  
Description:  
  
**Return faster casting value.**  
  
Example:  
  
```python  
fc = FasterCasting()  
```  
  
### FasterCastRecovery  
  
Method Signature:  
  
**Double FasterCastRecovery()**  
  
Description:  
  
**Return faster cast recovery value.**  
  
Example:  
  
```python  
fcr = FasterCastRecovery()  
```  
  
### FindObject  
  
Method Signature:  
  
**Boolean FindObject(System.Object, Int32, System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* range: Range, ie 10. (Optional)  
* findlocation: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Searches for entity by serial and sets found alias, defaults to ground if no source given.**  
  
Example:  
  
```python  
# Find on ground
FindObject("mount")

# Find on ground with range
FindObject("mount", 10)

# Find in container, must specify search level or -1
FindObject("weapon", -1, "backpack")    
```  
  
### FindType  
  
Method Signature:  
  
**Boolean FindType(Int32, Int32, System.Object, Int32, Int32)**  
  
#### Parameters  
* graphic: ItemID / Graphic such as  0x3db.  
* range: Range, ie 10. (Optional)  
* findlocation: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
* minimumstackamount: Integer representing an amount, ie 10. (Optional)  
  
Description:  
  
**Searches for entity by graphic ID and sets found alias, defaults to ground if no source given.**  
  
Example:  
  
```python  
# Look for a food item from a list and eat 1 if found.
if not ListExists("food"):
 CreateList("food")
 PushList("food", 0x9b7) #bird
 PushList("food", 0x9d3) #ham
 PushList("food", 0x97d) #cheese
 PushList("food", 0x9d0) #apple
 PushList("food", 0x9eb) #muffin
 PushList("food", 0x97b) #fishsteak
 PushList("food", 0x9c0) #sausage
 PushList("food", 0x9f2) #ribs
 PushList("food", 0x9d1) #grapes
 PushList("food", 0x9d2) #peach

for i in GetList("food"):
 if FindType(i, -1, "backpack"):
  UseObject("found")
  break  
```  
  
### FindWand  
  
Method Signature:  
  
**Boolean FindWand(System.String, System.Object, Int32)**  
  
#### Parameters  
* wandname: Wand name. See Also: [WandTypes](#WandTypes)  
* containersource: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
* minimumcharges: Integer value - See description for usage. (Optional)  
  
Description:  
  
**Search for a wand and set alias "found".**  
  
Example:  
  
```python  
FindWand("fireball", "backpack", 10)  
```  
  
### Followers  
  
Method Signature:  
  
**Int32 Followers()**  
  
Description:  
  
**Returns the number of current followers as per status bar data.**  
  
Example:  
  
```python  
if Followers() < 1:  
```  
  
### Gold  
  
Method Signature:  
  
**Int32 Gold()**  
  
Description:  
  
**Returns the gold value as per status bar data.**  
  
Example:  
  
```python  
if Gold() < 2000:  
```  
  
### Graphic  
  
Method Signature:  
  
**Int32 Graphic(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns Item ID of given object (parameter can be serial or alias).**  
  
Example:  
  
```python  
Graphic("mount")  
```  
  
### Gray  
  
Method Signature:  
  
**Boolean Gray(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the mobile's notoriety is Attackable**  
  
Example:  
  
```python  
if Criminal("mount"):  
```  
  
### Hidden  
  
Method Signature:  
  
**Boolean Hidden(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns true if given mobile is hidden, false if not, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
if Hidden("self"):  
```  
  
### Hits  
  
Method Signature:  
  
**Int32 Hits(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles hitpoints, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
hits = Hits("self")  
```  
  
### Hue  
  
Method Signature:  
  
**Int32 Hue(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns Hue of given object (parameter can be serial or alias).**  
  
Example:  
  
```python  
if Hue("mount") == 0:  
```  
  
### IgnoreObject  
  
Method Signature:  
  
**Void IgnoreObject(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Ignores the given object from find commands**  
  
Example:  
  
```python  
IgnoreObject("self")  
```  
  
### InFriendList  
  
Method Signature:  
  
**Boolean InFriendList(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if supplied mobile exists in the friends list.**  
  
Example:  
  
```python  
if InFriendList("last"):  
```  
  
### InIgnoreList  
  
Method Signature:  
  
**Boolean InIgnoreList(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Check whether the given serial / alias exists in the ignore list.**  
  
Example:  
  
```python  
if InIgnoreList("mount"):  
```  
  
### Innocent  
  
Method Signature:  
  
**Boolean Innocent(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the mobile's notoriety is Innocent**  
  
Example:  
  
```python  
if Criminal("mount"):  
```  
  
### InParty  
  
Method Signature:  
  
**Boolean InParty(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Return the true if the given serial/alias is in party with you.**  
  
Example:  
  
```python  
if InParty("friend"):  
```  
  
### InRange  
  
Method Signature:  
  
**Boolean InRange(System.Object, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* distance: Distance.  
  
Description:  
  
**Check for range between your character and another mobile or an item**  
  
Example:  
  
```python  
if InRange("enemy", 10):  
```  
  
### Int  
  
Method Signature:  
  
**Int32 Int()**  
  
Description:  
  
**Returns the intelligence of the player**  
  
Example:  
  
```python  
if Str() < 100:  
```  
  
### Invulnerable  
  
Method Signature:  
  
**Boolean Invulnerable(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the mobile's notoriety is Invulnerable**  
  
Example:  
  
```python  
if Criminal("mount"):  
```  
  
### Luck  
  
Method Signature:  
  
**Int32 Luck()**  
  
Description:  
  
**Returns the luck value as per status bar data.**  
  
Example:  
  
```python  
if Luck() < 800:  
```  
  
### Mana  
  
Method Signature:  
  
**Int32 Mana(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles mana, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
if Mana("self") < 25:  
```  
  
### Map  
  
Method Signature:  
  
**Int32 Map()**  
  
Description:  
  
**Returns the current map of the Player**  
  
Example:  
  
```python  
Map()  
```  
  
### MaxFollowers  
  
Method Signature:  
  
**Int32 MaxFollowers()**  
  
Description:  
  
**Returns the number of max followers as per status bar data.**  
  
Example:  
  
```python  
if Followers() == MaxFollowers():  
```  
  
### MaxHits  
  
Method Signature:  
  
**Int32 MaxHits(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles max hitpoints, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
hits = MaxHits("self")  
```  
  
### MaxMana  
  
Method Signature:  
  
**Int32 MaxMana(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles max mana, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
mana = MaxMana("self")  
```  
  
### MaxStam  
  
Method Signature:  
  
**Int32 MaxStam(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles max stamina, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
stam = MaxStam("self")  
```  
  
### MaxWeight  
  
Method Signature:  
  
**Int32 MaxWeight()**  
  
Description:  
  
**Returns the max weight as per status bar data.**  
  
Example:  
  
```python  
if MaxWeight() < 300:  
```  
  
### Mounted  
  
Method Signature:  
  
**Boolean Mounted(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the specified mobile is mounted.**  
  
Example:  
  
```python  
if Mounted("self"):  
```  
  
### MoveItem  
  
Method Signature:  
  
**Void MoveItem(System.Object, System.Object, Int32, Int32, Int32)**  
  
#### Parameters  
* item: An entity serial in integer or hex format, or an alias string such as "self".  
* destination: An entity serial in integer or hex format, or an alias string such as "self".  
* amount: Integer representing an amount, ie 10. (Optional)  
* x: X Coordinate. (Optional)  
* y: Y Coordinate. (Optional)  
  
Description:  
  
**Move item to container (parameters can be serials or aliases).**  
  
Example:  
  
```python  
MoveItem("source", "destination")  
```  
  
### MoveItemOffset  
  
Method Signature:  
  
**Void MoveItemOffset(System.Object, Int32, Int32, Int32, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* xoffset: X Coordinate offset.  
* yoffset: Y Coordinate offset.  
* zoffset: Z Coordinate offset.  
* amount: Integer representing an amount, ie 10. (Optional)  
  
Description:  
  
**Move the given serial/alias to the specified x,y,z offset of the player, no amount specified or -1 will move the full stack.**  
  
Example:  
  
```python  
MoveItemOffset("trashitem", 0, 1, 0, -1)  
```  
  
### MoveType  
  
Method Signature:  
  
**Void MoveType(Int32, System.Object, System.Object, Int32, Int32, Int32, Int32, Int32)**  
  
#### Parameters  
* id: ItemID / Graphic such as  0x3db.  
* sourcecontainer: An entity serial in integer or hex format, or an alias string such as "self".  
* destinationcontainer: An entity serial in integer or hex format, or an alias string such as "self".  
* x: X Coordinate. (Optional)  
* y: Y Coordinate. (Optional)  
* z: Z Coordinate. (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
* amount: Integer representing an amount, ie 10. (Optional)  
  
Description:  
  
**Move a type from source to destintion.**  
  
Example:  
  
```python  
#To move a type to another container...

MoveType(0x170f, "backpack", "bank")

#Destination can be the ground by specifying destination container to -1 and specifying the coordinates...

MoveType(0x170f, "backpack", -1, 1928, 2526, 0)

#Optional parameters exist for Hue and Amount, to move 10 maximum with the a Hue of 50...
MoveType(0x170f, "backpack", "bank", -1, -1, 0, 50, 10)  
```  
  
### MoveTypeOffset  
  
Method Signature:  
  
**Boolean MoveTypeOffset(Int32, System.Object, Int32, Int32, Int32, Int32, Int32, Int32)**  
  
#### Parameters  
* id: ItemID / Graphic such as  0x3db.  
* findlocation: An entity serial in integer or hex format, or an alias string such as "self".  
* xoffset: X Coordinate offset.  
* yoffset: Y Coordinate offset.  
* zoffset: Z Coordinate offset.  
* amount: Integer representing an amount, ie 10. (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
* range: Distance. (Optional)  
  
Description:  
  
**Move the given type from the specified source container to the specified x,y,z offset of the player, no amount specified or -1 will move the full stack.**  
  
Example:  
  
```python  
MoveTypeOffset(0xf0e, "backpack", 0, 1, 0, -1)  
```  
  
### Murderer  
  
Method Signature:  
  
**Boolean Murderer(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the mobile's notoriety is Murderer**  
  
Example:  
  
```python  
if Criminal("mount"):  
```  
  
### Name  
  
Method Signature:  
  
**System.String Name(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Return the name of the given mobile.**  
  
Example:  
  
```python  
if Name("self") == "Shmoo":  
```  
  
### Paralyzed  
  
Method Signature:  
  
**Boolean Paralyzed(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the specified mobile is frozen.**  
  
Example:  
  
```python  
if Paralyzed("self"):  
```  
  
### Poisoned  
  
Method Signature:  
  
**Boolean Poisoned(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the specified mobile is poisoned.**  
  
Example:  
  
```python  
if Poisoned("self"):  
```  
  
### Rehue  
  
Method Signature:  
  
**Void Rehue(System.Object, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* hue: Item Hue or -1 for any.  
  
Description:  
  
**Rehue an item/mobile the specified hue value, set to 0 to remove. (Experimental)**  
  
Example:  
  
```python  
Rehue("mount", 1176)  
```  
  
### RemoveFriend  
  
Method Signature:  
  
**Void RemoveFriend(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Removes a mobile from the friends list, will display target cursor if no serial/alias supplied.**  
  
Example:  
  
```python  
RemoveFriend()  
```  
  
### SpecialMoveExists  
  
Method Signature:  
  
**Boolean SpecialMoveExists(System.String)**  
  
#### Parameters  
* name: Special move name.  
  
Description:  
  
**Check for a specific special move**  
  
Example:  
  
```python  
if SpecialMoveExists("Death Strike"):  
```  
  
### Stam  
  
Method Signature:  
  
**Int32 Stam(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns the given mobiles stamina, if parameter is null, then returns the value from the player (parameter can be serial or alias).**  
  
Example:  
  
```python  
if Stam("self") < 25:  
```  
  
### Str  
  
Method Signature:  
  
**Int32 Str()**  
  
Description:  
  
**Returns the strength of the player**  
  
Example:  
  
```python  
if Str() < 100:  
```  
  
### TithingPoints  
  
Method Signature:  
  
**Int32 TithingPoints()**  
  
Description:  
  
**Returns the current players' tithing points.**  
  
Example:  
  
```python  
if TithingPoints() < 1000:  
```  
  
### UseLayer  
  
Method Signature:  
  
**Boolean UseLayer(System.Object, System.Object)**  
  
#### Parameters  
* layer: String representing a layer, such as "OneHanded" or "Talisman" etc.  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Uses object in the specified layer, optional parameter for mobile**  
  
Example:  
  
```python  
UseLayer("Talisman")  
```  
  
### War  
  
Method Signature:  
  
**Boolean War(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Checks whether a mobile is in war mode.**  
  
Example:  
  
```python  
if War("self"):  
```  
  
### Weight  
  
Method Signature:  
  
**Int32 Weight()**  
  
Description:  
  
**Returns the current weight as as per status bar data.**  
  
Example:  
  
```python  
if Weight() > 300:  
```  
  
### X  
  
Method Signature:  
  
**Int32 X(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns X coordinate of given object (parameter can be serial or alias).**  
  
Example:  
  
```python  
x = X("self")  
```  
  
### Y  
  
Method Signature:  
  
**Int32 Y(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns Y coordinate of given object (parameter can be serial or alias).**  
  
Example:  
  
```python  
y = Y("self")  
```  
  
### YellowHits  
  
Method Signature:  
  
**Boolean YellowHits(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Returns true if the specified mobile is yellowhits.**  
  
Example:  
  
```python  
if YellowHits("self"):  
```  
  
### Z  
  
Method Signature:  
  
**Int32 Z(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Returns Z coordinate of given object (parameter can be serial or alias).**  
  
Example:  
  
```python  
y = Y("self")  
```  
  



## Types  
### WandTypes  
* Clumsy  
* Identification  
* Heal  
* Feeblemind  
* Weaken  
* Magic_Arrow  
* Harm  
* Fireball  
* Greater_Heal  
* Lightning  
* Mana_Drain  
  
## Gumps  
### CloseGump  
  
Method Signature:  
  
**Void CloseGump(Int32)**  
  
#### Parameters  
* serial: An entity serial such as 0xf00ff00f.  
  
Description:  
  
**Close a specified gump serial**  
  
Example:  
  
```python  
CloseGump(0x454ddef)  
```  
  
### ConfirmPrompt  
  
Method Signature:  
  
**Boolean ConfirmPrompt(System.String, Boolean)**  
  
Description:  
  
**Displays an ingame prompt with the specified message, returns True if Okay was pressed, False if not.**  
  
Example:  
  
```python  
res = ConfirmPrompt("Play macro?")

if res:
 PlayMacro("Macro")  
```  
  
### GumpExists  
  
Method Signature:  
  
**Boolean GumpExists(UInt32)**  
  
Description:  
  
**Checks if a gump id exists or not.**  
  
Example:  
  
```python  
if GumpExists(0xff):  
```  
  
### InGump  
  
Method Signature:  
  
**Boolean InGump(UInt32, System.String)**  
  
#### Parameters  
* gumpid: An entity serial in integer or hex format, or an alias string such as "self".  
* text: String value - See description for usage.  
  
Description:  
  
**Check for a text in gump.**  
  
Example:  
  
```python  
if InGump(0xf00f, "lethal darts"):  
```  
  
### ItemArrayGump  
  
Method Signature:  
  
**Int32[] ItemArrayGump(System.Collections.Generic.IList`1[System.Object], Boolean, Int32, Int32, Boolean)**  
  
Description:  
  
**Displays a gump with the selected serials / aliases in a grid, similar to the UOSteam loot grid, returns array of serials selected**  
  
Example:  
  
```python  
from Assistant import Engine

#single select, specified items
result = ItemArrayGump([0x462d3373, 0x462d6029])

if result.Length == 0:
 print 'Nothing was selected'
else:
 print 'Serial {} was selected'.format(result[0])

#showing backpack items, multi select, at coords 200, 200
items = Engine.Player.Backpack.Container.GetItems()
results = ItemArrayGump(items, True, 200, 200)

if results.Length == 0:
 print 'Nothing was selected'
else:
 print '{} item(s) were selected'.format(results.Length)
 
 for serial in results:
  print 'Serial {} was selected'.format(serial)
  
```  
  
### MessagePrompt  
  
Method Signature:  
  
**System.ValueTuple`2[System.Boolean,System.String] MessagePrompt(System.String, System.String, Boolean)**  
  
#### Parameters  
* message: String value - See description for usage.  
* initialtext: String value - See description for usage. (Optional)  
* closable: True/False value, see description for usage. (Optional)  
  
Description:  
  
**Displays an ingame gump prompting for a message**  
  
Example:  
  
```python  
res, name = MessagePrompt("Enter Name?", "Whiskers")

if res:
 Rename(0xc1b, name)  
```  
  
### OpenGuildGump  
  
Method Signature:  
  
**Void OpenGuildGump()**  
  
Description:  
  
**Opens the Guild gump**  
  
Example:  
  
```python  
OpenGuildGump()  
```  
  
### OpenHelpGump  
  
Method Signature:  
  
**Void OpenHelpGump()**  
  
Description:  
  
**Opens the Help gump**  
  
Example:  
  
```python  
OpenHelpGump()  
```  
  
### OpenQuestsGump  
  
Method Signature:  
  
**Void OpenQuestsGump()**  
  
Description:  
  
**Opens the Quests gump**  
  
Example:  
  
```python  
OpenQuestsGump()  
```  
  
### OpenVirtueGump  
  
Method Signature:  
  
**Void OpenVirtueGump(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Opens the Virtue gump of the given serial/alias (defaults to current player)**  
  
Example:  
  
```python  
OpenVirtueGump("enemy")  
```  
  
### ReplyGump  
  
Method Signature:  
  
**Void ReplyGump(UInt32, Int32, Int32[], System.Collections.Generic.Dictionary`2[System.Int32,System.String])**  
  
#### Parameters  
* gumpid: ItemID / Graphic such as  0x3db.  
* buttonid: Gump button ID.  
* switches: Integer value - See description for usage. (Optional)  
* textentries: Not specified - See description for usage. (Optional)  
  
Description:  
  
**Sends a button reply to server gump, parameters are gumpID and buttonID.**  
  
Example:  
  
```python  
ReplyGump(0xff, 0)  
```  
  
### SelectionPrompt  
  
Method Signature:  
  
**System.ValueTuple`2[System.Boolean,System.Int32] SelectionPrompt(System.Collections.Generic.IEnumerable`1[System.String], System.String, Boolean)**  
  
#### Parameters  
* options: An array of strings.  
* message: String value - See description for usage. (Optional)  
* closable: True/False value, see description for usage. (Optional)  
  
Description:  
  
**Produces an in-game gump to choose from a list of options

Returns a tuple with a boolean signifying whether the OK button was pressed, and the index of the entry selected**  
  
Example:  
  
```python  
res, index = SelectionPrompt(['Sex', 'Drugs', 'Rock and Roll'])

if res:
 print 'Option {} was selected'.format(index)
else:
 print 'Cancel was pressed'  
```  
  
### WaitForGump  
  
Method Signature:  
  
**Boolean WaitForGump(UInt32, Int32)**  
  
#### Parameters  
* gumpid: ItemID / Graphic such as  0x3db. (Optional)  
* timeout: Timeout specified in milliseconds. (Optional)  
  
Description:  
  
**Pauses until incoming gump packet is received, optional paramters of gump ID and timeout**  
  
Example:  
  
```python  
WaitForGump(0xff, 5000)  
```  

## Journal  
### ClearJournal  
  
Method Signature:  
  
**Void ClearJournal()**  
  
Description:  
  
**Clear all journal texts.**  
  
Example:  
  
```python  
ClearJournal()  
```  
  
### InJournal  
  
Method Signature:  
  
**Boolean InJournal(System.String, System.String, Int32, Int32)**  
  
#### Parameters  
* text: String value - See description for usage.  
* author: String value - See description for usage. (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
* timeout: Timeout specified in milliseconds. (Optional)  
  
Description:  
  
**Check for a text in journal, optional source name.**  
  
Example:  
  
```python  
if InJournal("town guards", "system"):  
```  
  
### WaitForJournal  
  
Method Signature:  
  
**Boolean WaitForJournal(System.String, Int32, System.String, Int32)**  
  
#### Parameters  
* text: String value - See description for usage.  
* timeout: Timeout specified in milliseconds.  
* author: String value - See description for usage. (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
  
Description:  
  
**Wait the given timeout for the journal text to appear.**  
  
Example:  
  
```python  
if WaitForJournal("town guards", 5000, "system"):  
```  
  
### WaitForJournal  
  
Method Signature:  
  
**System.ValueTuple`2[System.Nullable`1[System.Int32],System.String] WaitForJournal(System.Collections.Generic.IEnumerable`1[System.String], Int32, System.String)**  
  
#### Parameters  
* entries: An array of strings.  
* timeout: Timeout specified in milliseconds.  
* author: String value - See description for usage. (Optional)  
  
Description:  
  
**Wait up the given timeout for one of any of provided array of string to appear in journal**  
  
Example:  
  
```python  
(idx, text) = WaitForJournal(['sex', 'drugs'], 5000)

if idx != None:
 print "Found text '{}' at index {}".format(text, idx)
else:
 print 'None of them were found :('  
```  
  
## Lists  
### ClearList  
  
Method Signature:  
  
**Void ClearList(System.String)**  
  
#### Parameters  
* listname: List name.  
  
Description:  
  
**Clear a list by name.**  
  
Example:  
  
```python  
ClearList("list")  
```  
  
### CreateList  
  
Method Signature:  
  
**Void CreateList(System.String)**  
  
#### Parameters  
* listname: List name.  
  
Description:  
  
**Create list with given name, if list already exists, it is overwritten.**  
  
Example:  
  
```python  
CreateList("list")  
```  
  
### GetList  
  
Method Signature:  
  
**System.Object[] GetList(System.String)**  
  
#### Parameters  
* listname: List name.  
  
Description:  
  
**Returns array of all entries in the list, for use with for loop etc.**  
  
Example:  
  
```python  
GetList("list")  
```  
  
### InList  
  
Method Signature:  
  
**Boolean InList(System.String, System.Object)**  
  
#### Parameters  
* listname: List name.  
* value: Integer value - See description for usage.  
  
Description:  
  
**Checks whether a list contains a given element.**  
  
Example:  
  
```python  
if InList("shmoo", 1):  
```  
  
### List  
  
Method Signature:  
  
**Int32 List(System.String)**  
  
#### Parameters  
* listname: List name.  
  
Description:  
  
**Returns the number of entries in the list.**  
  
Example:  
  
```python  
if List("list") < 5:  
```  
  
### ListExists  
  
Method Signature:  
  
**Boolean ListExists(System.String)**  
  
#### Parameters  
* listname: List name.  
  
Description:  
  
**Returns true if list exist, or false if not.**  
  
Example:  
  
```python  
if ListExists("list"):  
```  
  
### PopList  
  
Method Signature:  
  
**Int32 PopList(System.String, System.Object)**  
  
#### Parameters  
* listname: List name.  
* elementvalue: Element value to remove from list, or 'front' to remove the first item, or 'back' to remove last entry, default 'back'. (Optional)  
  
Description:  
  
**Remove elements from a list, returns the number of elements removed**  
  
Example:  
  
```python  
CreateList("hippies")
PushList("hippies", 1)
PushList("hippies", 2)
PushList("hippies", 3)

PopList("hippies", "front") # Removes 1
PopList("hippies", "back") # Removes 3
PopList("hippies", "2") # Removes any 2's that exist in the list


for x in GetList("hippies"):
 print x # Never reached because list is empty
  
```  
  
### PushList  
  
Method Signature:  
  
**Void PushList(System.String, System.Object)**  
  
#### Parameters  
* listname: List name.  
* value: Integer value - See description for usage.  
  
Description:  
  
**Pushes a value to the end of the list, will create list if it doesn't exist.**  
  
Example:  
  
```python  
PushList("list", 1)  
```  
  
### RemoveList  
  
Method Signature:  
  
**Void RemoveList(System.String)**  
  
#### Parameters  
* listname: List name.  
  
Description:  
  
**Removes the list with the given name.**  
  
Example:  
  
```python  
RemoveList("list")  
```  

## Macros  
### IsRunning  
  
Method Signature:  
  
**Boolean IsRunning(System.String)**  
  
#### Parameters  
* name: Macro name.  
  
Description:  
  
**Returns True if the specified macro name is currently running**  
  
Example:  
  
```python  
if IsRunning('macro'):  
```  
  
### PlayCUOMacro  
  
Method Signature:  
  
**Void PlayCUOMacro(System.String)**  
  
#### Parameters  
* name: Macro name.  
  
Description:  
  
**Plays the specified CUO macro name**  
  
Example:  
  
```python  
PlayCUOMacro('Paperdoll')  
```  
  
### PlayMacro  
  
Method Signature:  
  
**Void PlayMacro(System.String, System.Object[])**  
  
#### Parameters  
* name: Macro name.  
* args: Comma seperated list of parameters.  
  
Description:  
  
**Plays the given macro name.**  
  
Example:  
  
```python  
# Play another macro

PlayMacro("beep")

# Play another macro passing parameters to it

PlayMacro("beep", 1, "moo")

# In the played macro, args[0] will be 1 and args[1] will be "moo"  
```  
  
### Replay  
  
Method Signature:  
  
**Void Replay(System.Object[])**  
  
#### Parameters  
* args: Comma seperated list of parameters.  
  
Description:  
  
**Replay the current macro**  
  
Example:  
  
```python  
Replay()  
```  
  
### Stop  
  
Method Signature:  
  
**Void Stop(System.String)**  
  
#### Parameters  
* name: Macro name. (Optional)  
  
Description:  
  
**Stops the current macro.**  
  
Example:  
  
```python  
# Stop the current macro
Stop()
# Stop a macro by name
Stop("Background Macro")  
```  
  
### StopAll  
  
Method Signature:  
  
**Void StopAll()**  
  
Description:  
  
**Stops all running macros including background macros.**  
  
Example:  
  
```python  
StopAll()  
```  
  
## Main  

### BringClientWindowToFront  
  
Method Signature:  
  
**Void BringClientWindowToFront()**  
  
Description:  
  
**Bring client window to front**  
  
Example:  
  
```python  
BringClientWindowToFront()  
```  
  
### DisplayQuestPointer  
  
Method Signature:  
  
**Void DisplayQuestPointer(Int32, Int32, Boolean)**  
  
#### Parameters  

* x: X Coordinate.  
* y: Y Coordinate.  
* enabled: True/False value, see description for usage. (Optional)  
  
Description:  
  
**Display quest arrow pointer to specified coordinates**  
  
Example:  
  
```python  
# add pointer
DisplayQuestPointer(1000, 1000, True)
Pause(2000)
# remove pointer
DisplayQuestPointer(1000, 1000, False)  
```  
  
### HideEntity  
  
Method Signature:  
  
**Void HideEntity(System.Object)**  
  
#### Parameters  

* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Remove an item/mobile from the screen**  
  
Example:  
  
```python  
ClearIgnoreList()
# Hide all corpses on screen
while FindType(0x2006):
 HideEntity('found')
 IgnoreObject('found')  
```  
  
### Hotkeys  
  
Method Signature:  
  
**Void Hotkeys(System.String)**  
  
#### Parameters  

* onoff: "on" or "off". (Optional)  
  
Description:  
  
**Enable and disable hotkeys.**  
  
Example:  
  
```python  
Hotkeys()  
```  
  
### Info  
  
Method Signature:  
  
**Void Info(System.Object)**  
  
#### Parameters  

* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Show object inspector for supplied serial / alias, will prompt for target if no parameter given.**  
  
Example:  
  
```python  
Info("self")  
```  
  
### InvokeVirtue  
  
Method Signature:  
  
**Void InvokeVirtue(System.String)**  
  
#### Parameters  

* virtue: String value - See description for usage. See Also: [Virtues](#Virtues)  
  
Description:  
  
**Use a virtue by name.**  
  
Example:  
  
```python  
InvokeVirtue("Honor")  
```  
  
### Logout  
  
Method Signature:  
  
**Void Logout()**  
  
Description:  
  
**Disconnects from the server and returns to the login screen**  
  
Example:  
  
```python  
Logout()  
```  
  
### MessageBox  
  
Method Signature:  
  
**Void MessageBox(System.String, System.String)**  
  
#### Parameters  

* title: String value - See description for usage.  
* body: String value - See description for usage.  
  
Description:  
  
**Show a simple message box with a custom title and body.**  
  
Example:  
  
```python  
MessageBox("title", "message")  
```  
  
### OpenECV  
  
Method Signature:  
  
**Void OpenECV(System.Object)**  
  
#### Parameters  

* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Open entity collection viewer for specified container serial/alias**  
  
Example:  
  
```python  
OpenECV('backpack')  
```  
  
### Pause  
  
Method Signature:  
  
**Void Pause(Int32)**  
  
#### Parameters  

* milliseconds: Timeout specified in milliseconds.  
  
Description:  
  
**Pauses execution for the given amount in milliseconds.**  
  
Example:  
  
```python  
Pause(1000)  
```  
  
### Playing  
  
Method Signature:  
  
**Boolean Playing()**  
  
Description:  
  
**Returns true if there is a macro, use in background macros.**  
  
Example:  
  
```python  
if Playing():  
```  
  
### Playing(macroname)
  
Method Signature:  
  
**Boolean Playing("System.String")**  
  
#### Parameters  

* macroname: Macro name.  
  
Description:  
  
**Returns true if there is a macro, use in background macros.**  
  
Example:  
  
```python  
if Playing("macroname"):  
```  
  
### PlaySound  
  
Method Signature:  
  
**Void PlaySound(System.Object, Boolean)**  
  
Description:  
  
**Play sound by id or system .wav file.**  
  
Example:  
  
```python  
PlaySound("Bike Horn.wav")  
```  
  
### Quit  
  
Method Signature:  
  
**Void Quit()**  
  
Description:  
  
**Closes the client**  
  
Example:  
  
```python  
Quit()  
```  
  
### Resync  
  
Method Signature:  
  
**Void Resync()**  
  
Description:  
  
**Sends Resync request to server.**  
  
Example:  
  
```python  
Resync()  
```  
  
### SetAutologin  
  
Method Signature:  
  
**Void SetAutologin(Boolean, System.String, Int32, Int32)**  
  
Description:  
  
**Configures autologin settings**  
  
Example:  
  
```python  
SetAutologin(False)  
```  
  
### SetQuietMode  
  
Method Signature:  
  
**Void SetQuietMode(Boolean)**  
  
#### Parameters  

* onoff: "on" or "off".  
  
Description:  
  
**Set quiet mode True/False, True reduces the number of messages macro commands emit.**  
  
Example:  
  
```python  
SetQuietMode(True)  
```  
  
### Snapshot  
  
Method Signature:  
  
**System.ValueTuple`2[System.Boolean,System.String] Snapshot(Int32, System.Nullable`1[System.Boolean], System.String)**  
  
#### Parameters 
 
* delay: Integer value - See description for usage. (Optional)  
* fullscreen: True/False value, see description for usage. (Optional)  
* filename: String value - See description for usage. (Optional)  
  
Description:  
  
**Take a screenshot of the window**  
  
Example:  
  
```python  
# Just the game client area, no delay, default filename
Snapshot()

# Fullscreen snapshot, 3 second delay, default filename
Snapshot(3000, True)

# Client area snapshot, no delay, custom filename
Snapshot(0, False, "screenshot.png")  
```  
  
### SysMessage  
  
Method Signature:  
  
**Void SysMessage(System.String, Int32)**  
  
#### Parameters  

* text: String value - See description for usage.  
* hue: Item Hue or -1 for any. (Optional)  
  
Description:  
  
**Send a text message.**  
  
Example:  
  
```python  
# default hue
SysMessage("Hello")
# specifying hue
SysMessage("Hello", 35)  
```  
  
### WarMode  
  
Method Signature:  
  
**Void WarMode(System.String)**  
  
#### Parameters 
 
* onoff: "on" or "off". (Optional)  
  
Description:  
  
**Sets war mode status, parameter on, off, or toggle, defaults to toggle if no parameter given.**  
  
Example:  
  
```python  
WarMode("on")  
```  
  



## Types  

### Virtues  

* None  
* Honor  
* Sacrafice  
* Valor  
* Compassion  
* Honesty  
* Humility  
* Justice  
* Spirituality  
  
## Menu  
### CloseMenu  
  
Method Signature:  
  
**Void CloseMenu(Int32)**  
  
#### Parameters  
* gumpid: ItemID / Graphic such as  0x3db.  
  
Description:  
  
**Closes the specified menu id**  
  
Example:  
  
```python  
CloseMenu(0x1d1)  
```  

## Messages  
### AllyMsg  
  
Method Signature:  
  
**Void AllyMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Sends given message to alliance chat.**  
  
Example:  
  
```python  
AllyMsg("alert")  
```  
  
### CancelPrompt  
  
Method Signature:  
  
**Void CancelPrompt()**  
  
Description:  
  
**Cancels the current prompt.**  
  
Example:  
  
```python  
CancelPrompt()  
```  
  
### ChatMsg  
  
Method Signature:  
  
**Void ChatMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Sends a chat message.**  
  
Example:  
  
```python  
ChatMsg("Mary had a little lamb")  
```  
  
### EmoteMsg  
  
Method Signature:  
  
**Void EmoteMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Emotes the given message**  
  
Example:  
  
```python  
EmoteMsg("hi")  
```  
  
### GetText  
  
Method Signature:  
  
**System.ValueTuple`2[System.Boolean,System.String] GetText(System.String, Int32)**  
  
#### Parameters  
* prompt: String value - See description for usage.  
* timeout: Timeout specified in milliseconds. (Optional)  
  
Description:  
  
**Sends an internal prompt request and returns the text entered**  
  
Example:  
  
```python  
res, name = GetText("Name?", 10000)

if res:
 Rename(0xc1b, name)  
```  
  
### GuildMsg  
  
Method Signature:  
  
**Void GuildMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Sends given message to guild chat.**  
  
Example:  
  
```python  
GuildMsg("alert")  
```  
  
### HeadMsg  
  
Method Signature:  
  
**Void HeadMsg(System.String, System.Object, Int32)**  
  
#### Parameters  
* message: String value - See description for usage.  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
* hue: Item Hue or -1 for any. (Optional)  
  
Description:  
  
**Displays overhead message above given mobile / item.**  
  
Example:  
  
```python  
HeadMsg("hi", "backpack")  
```  
  
### Msg  
  
Method Signature:  
  
**Void Msg(System.String, Int32)**  
  
#### Parameters  
* message: String value - See description for usage.  
* hue: Item Hue or -1 for any. (Optional)  
  
Description:  
  
**Speaks the given message, Optional hue**  
  
Example:  
  
```python  
Msg("hi")  
```  
  
### PartyMsg  
  
Method Signature:  
  
**Void PartyMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Sends given message to party chat.**  
  
Example:  
  
```python  
PartyMsg("alert")  
```  
  
### PromptMsg  
  
Method Signature:  
  
**Void PromptMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Sends the specified message as a prompt response**  
  
Example:  
  
```python  
PromptMsg("hello")  
```  
  
### WaitForPrompt  
  
Method Signature:  
  
**Boolean WaitForPrompt(Int32)**  
  
#### Parameters  
* timeout: Timeout specified in milliseconds.  
  
Description:  
  
**Wait the specified timeout for a prompt packet to be received**  
  
Example:  
  
```python  
WaitForPrompt(5000)  
```  
  
### WhisperMsg  
  
Method Signature:  
  
**Void WhisperMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Whispers the given message**  
  
Example:  
  
```python  
WhisperMsg("hi")  
```  
  
### YellMsg  
  
Method Signature:  
  
**Void YellMsg(System.String)**  
  
#### Parameters  
* message: String value - See description for usage.  
  
Description:  
  
**Yells the given message**  
  
Example:  
  
```python  
YellMsg("hi")  
```  
  
## Movement  
### Follow  
  
Method Signature:

**Void Follow(System.Object)**  
 
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self". (Optional)  
  
Description:  
  
**Instructs ClassicUO to follow the specified alias/serial, supply no parameter to cancel**  
  
Example:  
  
```python  
if FindObject('enemy'):
 Follow('enemy')
 Attack('enemy')
else:
 Follow() # stop following
Pause(1000)  
```  
  
### Following  
  
Method Signature:  
  
**Boolean Following()**  
  
Description:  
  
**Returns True if currently following a target**  
  
Example:  
  
```python  
if not Following():
 Follow('enemy')  
```  
  
### Pathfind  
  
Method Signature:  
  
**Boolean Pathfind(Int32, Int32, Int32, Boolean)**  
  
#### Parameters  
* x: X Coordinate.  
* y: Y Coordinate.  
* z: Z Coordinate.  
* checkdistance: Not specified - See description for usage. (Optional)  
  
Description:  
  
**Requests client to pathfind to given coordinates / entity**  
  
Example:  
  
```python  
#Pathfind to coordinates
Pathfind(1438, 1630, 20)

#Pathfind to entity
SetEnemy(0x3c9)
Pathfind('enemy')

# Cancel pathfind in progress
Pathfind(-1)  
```  
  
### Pathfind  
  
Method Signature:  
  
**Boolean Pathfind(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Requests client to pathfind to given coordinates / entity**  
  
Example:  
  
```python  
#Pathfind to coordinates
Pathfind(1438, 1630, 20)

#Pathfind to entity
SetEnemy(0x3c9)
Pathfind('enemy')

# Cancel pathfind in progress
Pathfind(-1)  
```  
  
### Pathfinding  
  
Method Signature:  
  
**Boolean Pathfinding()**  
  
Description:  
  
**Returns True if ClassicUO is currently pathfinding**  
  
Example:  
  
```python  
Pathfind('enemy')
Pause(25) # there is a delay between calling Pathfind() and Pathfinding() being True

while Pathfinding():
 Pause(50)
 
HeadMsg("die scum", "self")  
```  
  
### Run  
  
Method Signature:  
  
**Boolean Run(System.String)**  
  
#### Parameters  
* direction: Direction, ie "West". See Also: [Direction](#Direction)  
  
Description:  
  
**Run in the given direction.**  
  
Example:  
  
```python  
Run("east")  
```  
  
### SetForceWalk  
  
Method Signature:  
  
**Void SetForceWalk(Boolean)**  
  
Description:  
  
**Set force walk, True or False**  
  
Example:  
  
```python  
SetForceWalk(True)  
```  
  
### ToggleForceWalk  
  
Method Signature:  
  
**Void ToggleForceWalk()**  
  
Description:  
  
**Toggle Force Walk**  
  
Example:  
  
```python  
ToggleForceWalk()  
```  
  
### Turn  
  
Method Signature:  
  
**Void Turn(System.String)**  
  
#### Parameters  
* direction: Direction, ie "West". See Also: [Direction](#Direction)  
  
Description:  
  
**Turn in the given direction.**  
  
Example:  
  
```python  
Turn("east")  
```  
  
### Walk  
  
Method Signature:  
  
**Boolean Walk(System.String)**  
  
#### Parameters  
* direction: Direction, ie "West".  
  
Description:  
  
**Walk in the given direction.**  
  
Example:  
  
```python  
Walk("east")  
```  
  



## Types  
### Direction  
* North  
* Northeast  
* East  
* Southeast  
* South  
* Southwest  
* West  
* Northwest  
* Invalid  
  
## Properties  
### Property  
  
Method Signature:  
  
**Boolean Property(System.Object, System.String)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* value: String value - See description for usage.  
  
Description:  
  
**Returns true if the given text appears in the items item properties.**  
  
Example:  
  
```python  
if Property("item", "Defense Chance Increase"):  
```  
  
### PropertyValue  
  
Method Signature:  
  
**T PropertyValue[T](System.Object, System.String, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* property: String value - See description for usage.  
* argument: Integer value - See description for usage. (Optional)  
  
Description:  
  
**Returns the argument value of the given property name. Optional argument index.**  
  
Example:  
  
```python  
val = PropertyValue[int]("backpack", "Contents")  
```  
  
### WaitForProperties  
  
Method Signature:  
  
**Boolean WaitForProperties(System.Object, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* timeout: Timeout specified in milliseconds.  
  
Description:  
  
**Wait for item properties to be received for specified item.**  
  
Example:  
  
```python  
WaitForProperties("backpack", 5000)  
```  
  
## Skills  
### SetSkill  
  
Method Signature:  
  
**Void SetSkill(System.String, System.String)**  
  
#### Parameters  
* skill: Skill name.  
* status: Lock Status - "up", "down", or "locked". See Also: [LockStatus](#LockStatus)  
  
Description:  
  
**Sets the lock state of the given skill, up, down or locked.**  
  
Example:  
  
```python  
SetSkill("hiding", "locked")  
```  
  
### SetStatus  
  
Method Signature:  
  
**Void SetStatus(System.String, System.String)**  
  
#### Parameters  
* stat: String value - See description for usage. See Also: [StatType](#StatType)  
* lockstatus: Lock Status - "up", "down", or "locked". See Also: [LockStatus](#LockStatus)  
  
Description:  
  
**Sets the lock state of the given stat, up, down or locked.**  
  
Example:  
  
```python  
SetStatus('str', 'locked')  
```  
  
### Skill  
  
Method Signature:  
  
**Double Skill(System.String, Boolean)**  
  
#### Parameters  
* name: Skill name.  
* baseskill: Not specified - See description for usage. (Optional)  
  
Description:  
  
**Returns the value of the given skill name.**  
  
Example:  
  
```python  
if Skill("hiding") < 100:  
```  
  
### SkillCap  
  
Method Signature:  
  
**Double SkillCap(System.String)**  
  
#### Parameters  
* name: Skill name.  
  
Description:  
  
**Returns the skill cap for the specified skill**  
  
Example:  
  
```python  
if SkillCap("Blacksmithy") == 120:  
```  
  
### SkillDelta  
  
Method Signature:  
  
**Double SkillDelta(System.String)**  
  
#### Parameters  
* name: Skill name.  
  
Description:  
  
**Returns the skill value delta since last reset**  
  
Example:  
  
```python  
if SkillDelta('Hiding') > 0.5:
    Stop()  
```  
  
### SkillState  
  
Method Signature:  
  
**System.String SkillState(System.String)**  
  
#### Parameters  
* name: Skill name.  
  
Description:  
  
**Returns the lock status of the given skill, up, down, or locked.**  
  
Example:  
  
```python  
if SkillState("hiding') == "locked":  
```  
  
### UseLastSkill  
  
Method Signature:  
  
**Void UseLastSkill()**  
  
Description:  
  
**Uses the last invoked skill**  
  
Example:  
  
```python  
UseLastSkill()  
```  
  
### UseSkill  
  
Method Signature:  
  
**Void UseSkill(System.String)**  
  
#### Parameters  
* skill: Skill name.  
  
Description:  
  
**Invokes the given skill name.**  
  
Example:  
  
```python  
UseSkill("Hiding")  
```  
  



## Types  
### LockStatus  
* Up  
* Down  
* Locked  
  
### StatType  
* Str  
* Dex  
* Int  
  
## Spells  
### Cast  
  
Method Signature:  
  
**Void Cast(System.String)**  
  
#### Parameters  
* name: Spell name.  
  
Description:  
  
**Cast the given named spell and automatically target given object.**  
  
Example:  
  
```python  
Cast("Recall", "runebook")  
```  
  
### Cast  
  
Method Signature:  
  
**Boolean Cast(System.String, System.Object)**  
  
#### Parameters  
* name: Spell name.  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Cast the given named spell and automatically target given object.**  
  
Example:  
  
```python  
Cast("Recall", "runebook")  
```  
  
### InterruptSpell  
  
Method Signature:  
  
**Void InterruptSpell()**  
  
Description:  
  
**Attempts to interrupt spell by lifting an item briefly.**  
  
Example:  
  
```python  
InterruptSpell()  
```  
  
## Target  
### CancelTarget  
  
Method Signature:  
  
**Void CancelTarget()**  
  
Description:  
  
**Cancel an existing cursor/target.**  
  
Example:  
  
```python  
CancelTarget()  
```  
  
### ClearTargetQueue  
  
Method Signature:  
  
**Void ClearTargetQueue()**  
  
Description:  
  
**Clears the target queue when queue last target/target self is enabled.**  
  
Example:  
  
```python  
ClearTargetQueue()  
```  
  
### GetEnemy  
  
Method Signature:  
  
**Boolean GetEnemy(System.Collections.Generic.IEnumerable`1[System.String], System.String, System.String, System.String, Int32)**  
  
#### Parameters  
* notorieties:  . See Also: [TargetNotoriety](#TargetNotoriety)  
* bodytype:  . (Optional) See Also: [TargetBodyType](#TargetBodyType)  
* distance:  . (Optional) See Also: [TargetDistance](#TargetDistance)  
* infliction:  . (Optional) See Also: [TargetInfliction](#TargetInfliction)  
* maxdistance: Distance. (Optional)  
  
Description:  
  
**Get mobile and set enemy alias.**  
  
Example:  
  
```python  
#get murderer
GetEnemy(['Murderer'])
#get closest murderer, any body type
GetEnemy(['Murderer'], 'Any', 'Closest')
#get next any notoriety, humanoid or transformation - unmounted
GetEnemy(['Any'], 'Both', 'Next', 'Unmounted')  
```  
  
### GetFriend  
  
Method Signature:  
  
**Boolean GetFriend(System.Collections.Generic.IEnumerable`1[System.String], System.String, System.String, System.String, Int32)**  
  
#### Parameters  
* notorieties:  . See Also: [TargetNotoriety](#TargetNotoriety)  
* bodytype:  . (Optional) See Also: [TargetBodyType](#TargetBodyType)  
* distance:  . (Optional) See Also: [TargetDistance](#TargetDistance)  
* infliction:  . (Optional) See Also: [TargetInfliction](#TargetInfliction)  
* maxdistance: Distance. (Optional)  
  
Description:  
  
**Get mobile and set friend alias.**  
  
Example:  
  
```python  
GetFriend(["Murderer"])  
```  
  
### GetFriendListOnly  
  
Method Signature:  
  
**Boolean GetFriendListOnly(System.String, System.String, System.String, Int32)**  
  
#### Parameters  
* distance:  . (Optional) See Also: [TargetDistance](#TargetDistance)  
* targetinfliction:  . (Optional) See Also: [TargetInfliction](#TargetInfliction)  
* bodytype:  . (Optional) See Also: [TargetBodyType](#TargetBodyType)  
* maxdistance: Distance. (Optional)  
  
Description:  
  
**Get friend that only exists in the friends list, parameter distance 'Closest'/'Nearest'/'Next'**  
  
Example:  
  
```python  
GetFriendListOnly("Closest")  
```  
  
### SetEnemy  
  
Method Signature:  
  
**Void SetEnemy(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Sets the enemy to the given serial/alias.**  
  
Example:  
  
```python  
SetEnemy("mount")  
```  
  
### SetFriend  
  
Method Signature:  
  
**Void SetFriend(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Sets the friend to the given serial/alias.**  
  
Example:  
  
```python  
SetFriend("mount")  
```  
  
### SetLastTarget  
  
Method Signature:  
  
**Void SetLastTarget(System.Object)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
  
Description:  
  
**Sets the last target to the given serial/alias.**  
  
Example:  
  
```python  
SetLastTarget("mount")  
```  
  
### Target  
  
Method Signature:  
  
**Void Target(System.Object, Boolean, Boolean)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* checkrange: Not specified - See description for usage. (Optional)  
* usequeue: Not specified - See description for usage. (Optional)  
  
Description:  
  
**Targets the given object (parameter can be serial or alias).**  
  
Example:  
  
```python  
Target("self")  
```  
  
### TargetByResource  
  
Method Signature:  
  
**Void TargetByResource(System.Object, System.String)**  
  
#### Parameters  
* toolobj: An entity serial in integer or hex format, or an alias string such as "self".  
* resourcetype: String value - See description for usage. See Also: [TargetResourceType](#TargetResourceType)  
  
Description:  
  
**Uses tool and targets specified resource type (Requires server support (OSI / ServUO))**  
  
Example:  
  
```python  
TargetByResource('pickaxe', 'Ore')  
```  
  
### TargetExists  
  
Method Signature:  
  
**Boolean TargetExists(System.String)**  
  
#### Parameters  
* targetexiststype: Target type - "harmful", "beneficial", or "neutral". (Optional) See Also: [TargetExistsType](#TargetExistsType)  
  
Description:  
  
**Returns true if a target cursor is displayed and the notoriety matches the supplied value, defaults to 'Any', options are 'Any', 'Beneficial', 'Harmful' or 'Neutral'**  
  
Example:  
  
```python  
if TargetExists("Harmful"):  
```  
  
### TargetGround  
  
Method Signature:  
  
**Void TargetGround(System.Object, Int32, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* hue: Item Hue or -1 for any. (Optional)  
* range: Range, ie 10. (Optional)  
  
Description:  
  
**Target the specified type on the ground, optional parameters for hue and distance.**  
  
Example:  
  
```python  
TargetGround(0x190, -1, 10)  
```  
  
### TargetTileOffset  
  
Method Signature:  
  
**Void TargetTileOffset(Int32, Int32, Int32, Int32)**  
  
#### Parameters  
* xoffset: X Coordinate offset.  
* yoffset: Y Coordinate offset.  
* zoffset: Y Coordinate offset.  
* itemid: ItemID / Graphic such as  0x3db. (Optional)  
  
Description:  
  
**Targets the tile at the given offsets relative to the player**  
  
Example:  
  
```python  
#Targets the tile at the current Y coordinate + 1
TargetTileOffset(0, 1, 0)  
```  
  
### TargetTileOffsetResource  
  
Method Signature:  
  
**Void TargetTileOffsetResource(Int32, Int32, Int32, Int32)**  
  
#### Parameters  
* xoffset: X Coordinate offset.  
* yoffset: Y Coordinate offset.  
* zoffset: Y Coordinate offset.  
* itemid: ItemID / Graphic such as  0x3db. (Optional)  
  
Description:  
  
**Targets the tile at the given offsets relative to the player (automatically targeting trees/cave tiles/water if present)**  
  
Example:  
  
```python  
TargetTileOffsetResource(0, -1, 0)  
```  
  
### TargetTileRelative  
  
Method Signature:  
  
**Void TargetTileRelative(System.Object, Int32, Boolean, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* distance: Integer value - See description for usage.  
* reverse: True/False value, see description for usage. (Optional)  
* itemid: ItemID / Graphic such as  0x3db. (Optional)  
  
Description:  
  
**Target tile the given distance relative to the specified alias/serial, optional boolean for reverse mode.**  
  
Example:  
  
```python  
TargetTileRelative("self", 1, False)  
```  
  
### TargetType  
  
Method Signature:  
  
**Void TargetType(System.Object, Int32, Int32)**  
  
#### Parameters  
* obj: An entity serial in integer or hex format, or an alias string such as "self".  
* hue: Item Hue or -1 for any. (Optional)  
* range: Range, ie 10. (Optional)  
  
Description:  
  
**Target specified type in player backpack, optional parameters for hue and search level.**  
  
Example:  
  
```python  
TargetType(0xff, 0, 3)  
```  
  
### TargetXYZ  
  
Method Signature:  
  
**Void TargetXYZ(Int32, Int32, Int32, Int32)**  
  
#### Parameters  
* x: X Coordinate.  
* y: Y Coordinate.  
* z: Z Coordinate.  
* itemid: ItemID / Graphic such as  0x3db. (Optional)  
  
Description:  
  
**Targets the ground at the given coordinates.**  
  
Example:  
  
```python  
TargetXYZ(1000, 1000, 0)  
```  
  
### WaitForTarget  
  
Method Signature:  
  
**Boolean WaitForTarget(Int32)**  
  
#### Parameters  
* timeout: Timeout specified in milliseconds. (Optional)  
  
Description:  
  
**Wait for target packet from server, optional timeout parameter (default 5000 milliseconds).**  
  
Example:  
  
```python  
WaitForTarget(5000)  
```  
  
### WaitForTargetOrFizzle  
  
Method Signature:  
  
**Boolean WaitForTargetOrFizzle(Int32)**  
  
#### Parameters  
* timeout: Timeout specified in milliseconds.  
  
Description:  
  
**Waits the specified timeout for target cursor whilst returning false if the spell is fizzled / uncastable beforehand.**  
  
Example:  
  
```python  
WaitForTargetOrFizzle(5000)  
```  
  
### WaitingForTarget  
  
Method Signature:  
  
**Boolean WaitingForTarget()**  
  
Description:  
  
**Returns true whenever the core is internally waiting for a server target**  
  
Example:  
  
```python  
if WaitingForTarget():  
```  
  



## Types  
### TargetBodyType  
* Any  
* Humanoid  
* Transformation  
* Both  
  
### TargetDistance  
* Next  
* Nearest  
* Closest  
* Previous  
  
### TargetExistsType  
* Any  
* Beneficial  
* Harmful  
* Neutral  
  
### TargetInfliction  
* Any  
* Lowest  
* Poisoned  
* Mortaled  
* Paralyzed  
* Dead  
* Unmounted  
  
### TargetNotoriety  
* None  
* Innocent  
* Criminal  
* Enemy  
* Murderer  
* Friend  
* Gray  
* Any  
  
### TargetResourceType  
* Ore  
* Sand  
* Wood  
* Graves  
* Red_Mushrooms  
  
## Timers  
### CreateTimer  
  
Method Signature:  
  
**Void CreateTimer(System.String)**  
  
#### Parameters  
* name: Timer name.  
  
Description:  
  
**Create a new named timer.**  
  
Example:  
  
```python  
CreateTimer("shmoo")  
```  
  
### RemoveTimer  
  
Method Signature:  
  
**Void RemoveTimer(System.String)**  
  
#### Parameters  
* name: Timer name.  
  
Description:  
  
**Removes the named timer.**  
  
Example:  
  
```python  
RemoveTimer("shmoo")  
```  
  
### SetTimer  
  
Method Signature:  
  
**Void SetTimer(System.String, Int32)**  
  
#### Parameters  
* name: An entity serial in integer or hex format, or an alias string such as "self".  
* milliseconds: Integer value - See description for usage. (Optional)  
  
Description:  
  
**Set a timer value and create in case it does not exist.**  
  
Example:  
  
```python  
SetTimer("shmoo", 0)  
```  
  
### Timer  
  
Method Signature:  
  
**Int64 Timer(System.String)**  
  
#### Parameters  
* name: Timer name.  
  
Description:  
  
**Check for a named timer value.**  
  
Example:  
  
```python  
if Timer("shmoo") > 10000:  
```  
  
### TimerExists  
  
Method Signature:  
  
**Boolean TimerExists(System.String)**  
  
#### Parameters  
* name: Timer name.  
  
Description:  
  
**Returns true if the timer exists.**  
  
Example:  
  
```python  
if TimerExists("shmoo"):  
```  
  
### TimerMsg  
  
Method Signature:  
  
**Void TimerMsg(System.String)**  
  
#### Parameters  
* name: Timer name.  
  
Description:  
  
**Outputs the elapsed timer value as a SystemMessage**  
  
Example:  
  
```python  
TimerMsg("shmoo")  
```  
  
## Trade  
### TradeAccept  
  
Method Signature:  
  
**Void TradeAccept()**  
  
Description:  
  
**Accepts the current trade window**  
  
Example:  
  
```python  
TradeAccept()  
```  
  
### TradeClose  
  
Method Signature:  
  
**Void TradeClose()**  
  
Description:  
  
**Closes the current trade window**  
  
Example:  
  
```python  
TradeClose()  
```  
  
### TradeCurrency  
  
Method Signature:  
  
**Void TradeCurrency(Int32, Int32)**  
  
Description:  
  
**Sets the gold and platinum in the trade window (for shards that support it)**  
  
Example:  
  
```python  
TradeCurrency(60000, 1)  
```  
  
### TradeReject  
  
Method Signature:  
  
**Void TradeReject()**  
  
Description:  
  
**Rejects (unticks) the current trade window**  
  
Example:  
  
```python  
TradeReject()  
```  
  
### WaitForTradeWindow  
  
Method Signature:  
  
**Boolean WaitForTradeWindow(Int32)**  
  
#### Parameters  
* timeout: Timeout specified in milliseconds. (Optional)  
  
Description:  
  
**Waits the specified number of milliseconds for trade window action, -1 for infinite**  
  
Example:  
  
```python  
WaitForTradeWindow(5000)  
```  
  
## World Map  
### AddMapMarker  
  
Method Signature:  
  
**Void AddMapMarker(System.String, Int32, Int32, Int32, Int32, System.String)**  
  
#### Parameters  
* name: String representing a name, ie "Snoopy".  
* x: X Coordinate.  
* y: Y Coordinate.  
* facet: Integer value - See description for usage.  
* zoomlevel: Integer value - See description for usage. (Optional)  
* iconname: String value - See description for usage. (Optional)  
  
Description:  
  
**Adds a marker on the world map**  
  
Example:  
  
```python  
AddMapMarker("Treasure", 1000, 1000, 0)  
```  
  
### ClearMapMarkers  
  
Method Signature:  
  
**Void ClearMapMarkers()**  
  
Description:  
  
**Clears all map markers**  
  
Example:  
  
```python  
ClearMapMarkers()  
```  
  
### RemoveMapMarker  
  
Method Signature:  
  
**Void RemoveMapMarker(System.String)**  
  
#### Parameters  
* name: String value - See description for usage.  
  
Description:  
  
**Removes all map markers with the specified name from the world map**  
  
Example:  
  
```python  
RemoveMapMarker("Treasure")  
```  
  
