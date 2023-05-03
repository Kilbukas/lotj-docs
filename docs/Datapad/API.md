
# API

`Datapad` is a class that represents a player's datapad. It can be used to access the datapad's usual functions through lua. That means you can write self-modifying scripts, among other exciting things.

A good number of datapad functions deal with the `Note` structure, which looks like this:

```lua
{
    name = "Glup Shitto",
    text = "&OI'd like to join the Rebellion.\r\n &YYou can contact me on channel &k420&k, encryption &k69&k.",
    subject = "Rebel Recruitment",
    to = "@50963",
}
```

##

## getCapacity

`Datapad.getCapacity()` returns the maximum number of notes your datapad can hold.

### Example

```lua
return Datapad.getCapacity()
```

> `dataprog` Output, using a MSTR datapad:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: 35
```

##

## getFreeSpace

`Datapad.getFreeSpace()` returns the number of notes your datapad can hold before it is full.

### Example

```lua
return Datapad.getFreeSpace()
```

> `dataprog` Output, using a MSTR datapad with 3 notes:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: 32
```

##

## getDiskCount

`Datapad.getDiskCount()` returns the number of disks your datapad currently holds.

```lua
return Datapad.getDiskCount()
```

> `dataprog` Output, using a MSTR datapad with 3 disks:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: 3
```

##

## isFull

`Datapad.isFull()` returns `true` if your datapad is full, `false` otherwise.

### Example

```lua
return Datapad.isFull()
```

> `dataprog` Output, using a MSTR datapad with 3 notes:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: false
```

> `dataprog` Output, using a MSTR datapad with 35 notes:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: true
```

##

## isLocked

`Datapad.isLocked()` returns `true` if your datapad is locked, `false` otherwise.

##

## hasBiometrics

`Datapad.hasBiometrics()` returns `true` if your datapad is biometrically locked, `false` otherwise.

##

## isReceiving

`Datapad.isReceiving()` returns `true` if your datapad is receiving data, `false` otherwise.

##

## canReceive

`Datapad.canReceive()` returns `true` if your datapad can receive data, `false` otherwise.

##

## setReceiveMode

`Datapad.setReceiveMode()` sets your datapad to receive messages.

##

## getDisk

`Datapad.getDisk(slot)` returns the disk in the specified slot.

### Parameters

| Parameter | Required | Description                                                                                                                  |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `slot`    | Yes      | The slot to get the disk from. Has to be a positive number.                                                                                               |

### Example

```lua
-- Dataprog to simply print the text of a disk.
return Datapad.getDisk(tonumber(args)).text
```

> `dataprog` Output, using `dataprog run 1`:

```
You boot program '(no subject)' on your datapad.
Program finished. Result: -- Dataprog to simply print the text of a disk.\r\nreturn Datapad.getDisk(tonumber(args)).text\r\n
```

##

## disks

`Datapad.disks()` returns all the disks in your datapad.

##

## newDisk

`Datapad.newDisk(disk)` creates a new disk in your datapad.

### Parameters

| Parameter | Required | Description                                                                                                                  |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `disk`    | Yes      | The disk to create. Has to be a table with the following keys: `name`, `text`, `subject`, `to`.                                                                                               |

### Example

```lua
local disk = {
    name = "My Disk",
    text = "This is my disk.",
    subject = "My Disk",
    to = "Disk police",
}

Datapad.newDisk(disk)
```

##

## deleteDisk

`Datapad.deleteDisk(slot)` deletes the disk in the specified slot.

### Parameters

| Parameter | Required | Description                                                                                                                  |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `slot`    | Yes      | The slot to delete the disk from. Has to be a positive number.                                                                                               |

### Example

```lua
-- Deletes the disk in slot provided as argument. Equivalent to `datamem delete <slot>`.
Datapad.deleteDisk(tonumber(args))
```

##

## ejectDisk

`Datapad.ejectDisk(slot)` ejects the disk in the specified slot.

### Parameters

| Parameter | Required | Description                                                                                                                  |
| --------- | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| `slot`    | Yes      | The slot to eject the disk from. Has to be a positive number with an existing disk.                                                                                               |

### Example

```lua
-- Ejects the disk in slot provided as argument. Equivalent to `datamem eject <slot>`.
Datapad.ejectDisk(tonumber(args))
```

##
