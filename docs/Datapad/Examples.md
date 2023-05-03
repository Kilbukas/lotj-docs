
# Examples

## Stripping colors

```lua
local disk = Datapad.getDisk(tonumber(args))

-- Strip colors from the disk's text.
disk.text = LOTJ.stripColors(disk.text)

-- Save the colorless disk.
Datapad.newDisk(disk)
```

## Generating an ascii table of your datapad's disks

```lua
-- Check if there's any free space on the datapad first.
if Datapad.isFull() then
    return "Error: Your datapad is full."
end

-- Get all of the disks.
local disks = Datapad.disks()
local newDisk = {
    name = "",
    text = "",
    subject = "Disk Table",
    to = "",
}

-- Generate the table.
local table = "Slot | Name | Subject | To\r\n-----|------|---------|---\r\n"
for i, disk in ipairs(disks) do
    table = table .. i .. " | " .. disk.name .. " | " .. disk.subject .. " | " .. disk.to .. "\r\n"
end

-- Add the table to the new disk.
newDisk.text = table

-- Create the new disk.
Datapad.newDisk(newDisk)
```






