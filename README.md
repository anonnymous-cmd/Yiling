# Yiling
# --- Character Definitions (WangXian) ---
define wwx = Character("Wei Wuxian", color="#df0000") # Yunmeng Jiang Red
define lwj = Character("Lan Wangji", color="#00eeee") # Gusu Lan Blue

# --- Game Variables (BL & Cultivation Logic) ---
default soulmate_bond = 0
default golden_core_strength = 10
default resentful_energy = 0

label start:
    "Location: Cloud Recesses - Night"
    
    # Logic for a classic 'The Untamed' encounter
    wwx "Lan Zhan! Look at me! Is the Gusu Lan ribbon really that important?"

    menu:
        "Tug on his forehead ribbon":
            $ soulmate_bond += 50
            $ resentful_energy += 5
            lwj "Stay back! This ribbon is... only for family and soulmates."
            wwx "Then maybe I'm your soulmate, HanGuang-Jun?"
            jump path_romance

        "Offer him Emperor's Smile wine":
            $ soulmate_bond += 10
            $ golden_core_strength -= 5
            lwj "Alcohol is forbidden in Cloud Recesses. Go to the Discipline Hall."
            wwx "So cold! You haven't changed at all."
            jump path_discipline

label path_romance:
    "Lan Wangji's ears turn red. The bond between you has grown."
    "Current Soulmate Bond: [soulmate_bond]"
    "The story continues toward the Burial Mounds..."
    return

label path_discipline:
    "You spent the night copying rules, but Lan Wangji watched over you the whole time."
    "Golden Core Strength: [golden_core_strength]"
    return
