# Programming the Farming Drone(Report)

## Inttroduction

In Harvesting Game, players will experience a day in the life of a farmer! The goal is to maximize harvest by planting and cultivating crops and keeping an eye on resource levels on a grid-like farm. Unlike a typical farming game where players control a character directly, here the player’s job is to write Python code that directs the drone to perform tasks such as planting, watering, harvesting crops, and collecting treasures or resources like wood.

### Game Objective

The primary objective of the Python Harvesting Game is to maximize score by planting, growing, and harvesting crops while unlocking new functions and crops. As players progress, they can unlock upgrades like increased speed, an expanded farming grid, and new crops such as sunflowers, cactus and carrots or locating and collecting treasure items scattered across the grid. Players also need to automate tasks by writing functions and loops to optimize the drone’s actions, ensuring it makes the best use of time and resources while navigating the farm grid.

Through code, players can manage:

**Planting and Harvesting**: Directing the drone to plant, water, and harvest crops in an organized manner.

**Collecting Treasures**: Exploring the grid to find and collect treasures that provide additional resources or rewards.

**Resource Management**: Trading or using resources like seeds and water to maintain and expand the farm.

# Table of Contents
-[Code Snippets and Explanation](#code-snippets-and-explanation)

-[Challenges and Learnings](#challenges-and-learnings)

-[References](#references)

## Step 1 : Farming on 1 Tile

**Code**

```python
whileTrue:
    if can_harvest():
        harvest()
```

**Explanation**

The code runs an infinite number of times and harvest the grass with the if condition.


**Demo**

Video Demo :




**Notes**

- Using the code above I was able to get enough hay from which I could expand my farming tiles.

- Some of features I unlocked using the above code were variables and functions.





## Step 2 : Planting Hay

**Code**

```python
while True:
    for 1 in range(get_world_size()):
        move(North)
        if can_harvest():
            harvest()
    move(East)
     
```

**Explanation**

This code creates a pattern where the drone moves northward, harvesting as it goes and then it moves east at the end of each column, effectively covering the farming grid in a sweeping pattern.

**Demo**

Video Demo :
![alt text](step2.mov)


**Notes**

- Using the code above I was able to get enough wood to unlock the speed and operators.




## Step 3 : Planting Bush

**Code**

```python
while True: 
    for i in range (get world_size()):
        move( North)
        if can_harvest():
            harvest()
            if num_items(Items.Hay) < 5000:
                plant（Entities.Grass）
            elif num items(Items-Wood) < 5000:
                plant(Entities.Bush)
            else:
                if num_items(Items.Carrot_Seed < 25000):
                    trade(Items. Carrot_Seed)
                if get_ground_type() == Grounds.Turf:
                    till()
                plant（Entities.Bush）
    move(East)
```

**Explanation**
This code makes the drone move north while repeatedly checking for crops to harvest. It will either plant grass, bushes, or trade for carrot seeds. The character then moves east to continue the pattern.

**Demo**

Video Demo :
[text](step3.mov)


**Notes**

- Using the code above I was able to harvest wood, hay and carrot simultaneously.







## Step 4 : Planting trees

**Code**

```python
while True:
    for i in range(get world_size()):
        move(North)
        x = get_pos_x()
        y = get_pos_y()
        if can_harvest():
            harvest()
            if num_items(Items-Water_Tank) < WaterTankCap:
                trade( Items.Empty_Tank)
            if get_water（） < 0.5: 
                use_item(Items-Water_Tank)
            if num_items(Items-Hay) < HayCap:
                if get_ground_type() == Grounds.Soil:
                    till()
                plant(Entities.Grass)
            elif num_items(Items.Wood) < WoodCap:
                if (x % 2 == 0 and y % 2 == 1) or (x % 2 == 1 and y % 2 == 0):
                    plant(Entities.Tree)
                else：
                if get_ground_type() == Grounds.Soil:
                    plant(Entities.Bush)
                elif num _items(Items.Carrot) < CarrotCap: 
                    if num_items (Items.Carrot_Seed) == 0:
                        trade(Items. Carrot_Seed)
                    if get_ground_type() == Grounds.Turf:
                        till()
                    plant(Entities.Carrots)
    move( East)
```

**Explanation**

This code makes the drone to move North repeatedly across the grid. It trades empty tanks for water tanks if under capacity and Uses a water tank if the water level falls below 0.5.

**Demo**

Video Demo :
[text](step4.mov)


**Notes**

- Using the code above I was able to get huge amount wood to unlock functions and upgrade speed and even expand the field.




## Step 5 : Planting Carrots and Sunflower

**Code**

```python
main:
while True:
    for i in range(get_world_size):
        move(North)
        x = get_pos_(x）
        y = get_pos_(y）
        if can_harvest():
            harvest()
            Watering()
            Planting()
    move(East)
Watering:
def watering():
    if num_items(Items.Water_Tank) < WaterTankCap:
        trade(Items.Empty_Tank, 5)
    if get_water() < 8.75:
        use_item(Items.Water_Tank)
planting:
def Plantingt():
    if x == 0 and y == 0:
        if num_itemsIteMs.SunfLower_Seed）== 0:
            trade（Items.Sunflower_Seed, s）
        if get_ground_type() == Grounds.Turf:
            till()
        plant(Entities.Sunflower)
    elif num_items(Items.Hay) < HayCap:
        if get_ground_type() = Grounds.Soil:
            till()
        plant（Entities.6rass）
    elif num itenstitems.Wood) < WoodCap:
        if （x % 2 == 0 and y % 2 == 1） or （x % 2 == 1 and y % 2 == 0):
            plant(Entities.Tree)
        else:
            if get_ground_type() == Grounds.Soil:
                till()
            plant(Entities.Bush)
    elif num_items(Items.Carrot) < CarrotCap:
        if num_items(Items.Carrot_Seed) == 0:
            trade( Items.Carrot Seed)
        if get_ground_type() = Grounds.Turf:
            till()
        plant(Entities.Carrot)
```

**Explanation**

This code plants trees, bushes, sunflowers, carrots and hays in a checkerboard pattern across the grid, watering each cell, and harvesting as needed until the required amount of each is collected.

**Demo**

Video Demo :
[text](step5.mov)


**Notes**

- Using the code above I was able to get many woods, power, hays and trees from which i unlocked many other functions.



## Step 6 : Planting Pumpkins

**Code**

```python
main:
while True:
    for i in range(get_world_size):
        move(North)
        x = get_pos_(x）
        y = get_pos_(y）
        if can_harvest():
            harvest()
            Watering()
            Planting()
        else:
            if get_ground_type() == Grounds.Soils:
                till()
    move(East)
Watering:
def watering():
    if num_items(Items.Water_Tank) < WaterTankCap:
        trade(Items.Empty_Tank, 5)
    if get_water() < 8.75:
        use_item(Items.Water_Tank)
planting:
def Plantingt():
    if x == 0 and y == 0:
        if num_itemsIteMs.SunfLower_Seed）== 0:
            trade（Items.Sunflower_Seed, s）
        if get_ground_type() == Grounds.Turf:
            till()
        plant(Entities.Sunflower)
    elif num_items(Items.Hay) < HayCap:
        if get_ground_type() = Grounds.Soil:
            till()
        plant（Entities.6rass）
    elif num itenstitems.Wood) < WoodCap:
        if （x % 2 == 0 and y % 2 == 1） or （x % 2 == 1 and y % 2 == 0):
            plant(Entities.Tree)
        else:
            if get_ground_type() == Grounds.Soil:
                till()
            plant(Entities.Bush)
    elif num_items(Items.Carrot) < CarrotCap:
        if num_items(Items.Carrot_Seed) == 0:
            trade( Items.Carrot Seed)
        if get_ground_type() = Grounds.Turf:
            till()
        plant(Entities.Carrot)
    elif num_items(Items.Pumpkin) < PumpkinCap:
        if num_items(Items.Pumpkin_Seed) == 0:
            trade( Items.Pumpkin_Seed, 5)
        if get_ground_type() = Grounds.Turf:
            till()
        plant(Entities.Pumpkin)
        
```

**Explanation**


This code makes the drone to plant, water, and harvest carrots across the grid. If the drone can harvest an item at
its current position, it harvests. After harvesting, it calls Watering() and Planting() to manage water levels and 
plant resources. If no harvestable item is found and the ground type is "Soil," it tills the soil to prepare it for
planting. The Plantingt() function checks resource levels and grid position to decide which plants to grow and
whether to trade for seeds. If the hay supply is low, it checks if the ground type is "Soil." If so, it tills the
ground and plants grass.If the wood supply is low it plants trees at specific positions Otherwise, if the ground
type is "Soil," it tills and plants a bush. It repeats for each harvesting.

**Demo**

Video Demo :
[text](step6.mov)


**Notes**

- Using the code above I was able to get enough carrots, pumpkins and woods to unlock other vegetables and plants.




## Step 7 : Power Harvesting

**Code**

```python
main:
while True:
    for i in range(get_world_size):
        move(North)
        x = get_pos_(x）
        y = get_pos_(y）
        if can_harvest():
            harvest()
            Watering()
            Planting()
        else:
            if get_ground_type() == Grounds.Soils:
                till()
    move(East)
WateringAndHarvesting:
def Harvesting():
    if can harvest():
        if get_entity_type() == Entities.Sunflower:
            if measure() == max(PedalList):
                harvest()
                PedalList.Remove(max(PedalList))
        else:
            harvest()
            Planting(）
        if get_water() < 0.8:
            use_item(Items.Water_Tank)
    else:
        if get_ground_type() == Grounds.Soil:
            till()
planting:
def Plantingt():
    if x == 0 and y == 0:
        if num_itemsIteMs.SunfLower_Seed）== 0:
            trade（Items.Sunflower_Seed, s）
        if get_ground_type() == Grounds.Turf:
            till()
        plant(Entities.Sunflower)
    elif num_items(Items.Hay) < HayCap:
        if get_ground_type() = Grounds.Soil:
            till()
        plant（Entities.6rass）
    elif num itenstitems.Wood) < WoodCap:
        if （x % 2 == 0 and y % 2 == 1） or （x % 2 == 1 and y % 2 == 0):
            plant(Entities.Tree)
        else:
            if get_ground_type() == Grounds.Soil:
                till()
            plant(Entities.Bush)
    elif num_items(Items.Carrot) < CarrotCap:
        if num_items(Items.Carrot_Seed) == 0:
            trade( Items.Carrot Seed)
        if get_ground_type() = Grounds.Turf:
            till()
        plant(Entities.Carrot)
    elif num_items(Items.Pumpkin) < PumpkinCap:
        if num_items(Items.Pumpkin_Seed) == 0:
            trade( Items.Pumpkin_Seed, 5)
        if get_ground_type() = Grounds.Turf:
            till()
        plant(Entities.Pumpkin)
BuyStuff:
def BuyStuff():
    if munLttems（Items.Sunflower_Seed） < 100:
        trade(Items.Sunflower_seed, get_world_size())
    if num_items(Itens.Carrot_seed) < 100:
        trade(Items.Carrot_seed, get_world_size())
    if num_Items(Items.Pumpkin_seed) < 100:
        trade(Items.Pumpkin_Seed, get_world_size())
    if num_items(Items.Water_Tank) < 180:
        if num_items(Items.Empty_Tank) < 588:
            trade(Items.Empty_Tank, 5)
```

**Explanation**



This code makes the drone to plant and harvest sunflowers by traversing the grid, checking and recording empty cells, trading for seeds as needed, replanting at unoccupied positions, and iteratively revisiting and replanting until the required number of sunflowers is collected from which we get the power to unlock other such functions as speed.

**Demo**

Video Demo :
[text](step7.mov)


**Notes**

- Using the code above I was able to get enough sunflowers from which i collected the power to unlock advanced and useful data types which made the coding much simpler and shorter.




## Step 8 : Treasure Harvesting

**Code**

```python
SolveMaze:
def SolveMaze():
    direction = North
    while set.entity_type() != Entities.Treasure:
        direction = TurnLeft(direction)
        if move(direction) == False:
            direction = TurnRight(direction)
        if move(direction) == False:
            direction = TurnRight(direction)
        else:
            direction = TurnLeft(direction)
            if move(direction) == False:
                direction = TurnRight(direction)
    harvest()
ChangeDirections:
def TurnRight(direction): 
    if direction == North:
        return East
    if direction == East:
        return South
    if direction == South:
        return west
    if direction == West:
        return North
def TurnLeft(direction):
    if direction == North:
        return West
    if direction == West:
        return South
    if direction == South:
        return East
    if direction == East:
        return North
            
                
                
                
```

**Explanation**


This code is designed to navigate a maze, adjusting directions to reach a treasure by turning left or right as
needed. If it can't move, it turns right (twice if needed) to try a different path. If movement is possible, it
continues forward, following the pattern of checking left, and then right if needed. The loop continues until the
bot detects the "Treasure" entity type, at which point it performs a harvest() to collect it. TurnRight: Adjusts the
direction 90° clockwise. TurnLeft: Adjusts the direction 90° counterclockwise.

**Demo**

Video Demo :
[text](step8.mov)


**Notes**

- Using the code above I was able to get enough treausre for me to unlock the cactus function.



# Challenges and Learnings

## Challenges

In the Farmer is Replaced Python game, several challenges made gameplay both engaging and complex:

**1. Resource Management**: Players must carefully manage limited resources like water, seeds, and tools to ensure
steady crop production. Mismanaging these resources lead to shortages, impacting the farm’s overall efficiency.

**2. Time and Space Optimization**: Efficient pathfinding and time management are essential, as players must program their drone to cover the entire farming grid. This can be challenging when balancing movement efficiency with crop-specific requirements.

**3. Scalability of Functions**: As new crops and functions are unlocked, the player must update their bot's programming to handle additional tasks, which increases the game’s complexity and encourages thoughtful coding strategies.

**4. Prioritizing High-Yield Harvests**: When faced with limited resources, choosing which crops to prioritize (such as high-yield crops like pumpkins) adds strategic depth. Measuring factors like yield and growth time becomes essential to maximize output within constraints.




## Learnings

Playing and solving Farmer is Replaced provided valuable insights and learning experiences in several areas:

**1. Algorithm Design and Problem-Solving**: The need to program a bot for farming tasks highlighted the importance of crafting efficient algorithms. From pathfinding to resource management, every action needed careful planning to ensure smooth and productive gameplay.

**2.Resource Management and Planning**: The game reinforced lessons on managing limited resources such as water, seeds, and space. This translated into understanding the principles of allocation and prioritization, which are crucial in both programming and real-world applications.

**3.Time and Space Efficiency**: Planning movements and tasks to cover the grid efficiently emphasized the importance of optimizing time and space in code execution. This aspect of gameplay taught practical lessons on designing efficient, effective solutions under constraints.

**4.Debugging and Avoiding Infinite Loops**: Encountering infinite loops or unexpected recursion due to resource shortages underscored the importance of setting clear exit conditions and using error handling to maintain control flow.

**5.Grid-Based Movement and Coordination**: Developing precise algorithms to direct the drone across the grid and handle edge cases (like boundaries or revisiting cells) was a practical exercise in spatial reasoning and algorithm design.



## References

1.[Nathan](https://youtu.be/gmJ357XAAdE?si=uT6o0wMdZGzuN3LB)

2.[Jack Hodkinson](www.youtube.com/@jack.hodkinson)

3.[Chatgpt](https://chatgpt.com)
