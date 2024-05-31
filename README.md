# ConfluxPortals

End-game player controlled point-to-point portals for Minecraft.

Inspired by https://github.com/bundabrg/PortalNetwork

## Brain dump

- crafting
    - only one type
    - embed the network into the crafting recipe
      ```
      ES EP ES
      ES WO ES
      ES NI ES

      ES = end-stone
      EP = ender-pearl
      WO = wool block (network)
      ```

- portal
    - legend
      ```
      ?? = anything
      -- = air
      ~~ = particles in air
      WO = wool (block or carpet); sets this portal's colour
      CO = coloured concrete, for this portal's colour (or maybe glass)
      RD = reinforced deepslate
      PB = portal block
      ```

    - building
      ```
      ?? WO ??
      ?? PB ??
      ```

    - active
      ```
      CO -- CO
      RD ~~ RD
      RD PB RD
      ```

    - inactive
      ```
      CO -- CO
      RD -- RD
      RD PB RD
      ```


- mechanics
    - crafted portal block
        - need to find a suitable block that can be mined (red glazed terracotta?)
        - add enchantment and lore (network colour)
    - place block, wool or carpet on top
        - two short columns, topped with concrete (or glass?) with the colour from the wool block/carpet
        - breaks and drops blocks that are in the way
            - if there are unbreakable blocks (eg. bedrock) then don't activate
    - prticles between indicate the dialed colour
    - rewrite player detection code to make it less janky
    - no support for flight or minecarts (1.21's portals makes this unnecessary)
    - right click either of the columns to cycle
    - must break portal block to destroy the portal, this will drop just the block

```
