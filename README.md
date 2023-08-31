class StoryNode:
    def __init__(self, text, choices=None):
        self.text = text
        self.choices = choices or []

def play_story(start_node):
    current_node = start_node
    
    while True:
        print(current_node.text)
        
        if not current_node.choices:
            print("The end of the story.")
            break
        
        for idx, choice in enumerate(current_node.choices, start=1):
            print(f"{idx}: {choice[0]}")
        
        choice_num = int(input("Choose an option: ")) - 1
        
        if 0 <= choice_num < len(current_node.choices):
            current_node = current_node.choices[choice_num][1]
        else:
            print("Invalid choice. Please select a valid option.")

# Define your story nodes and choices
ending_node = StoryNode("Congratulations, you've reached the end!")
choice3 = ("Take the left path.", ending_node)
choice2 = ("Climb the mountain.", choice3)
choice1 = ("Cross the river.", choice2)
start_node = StoryNode("You find yourself at a crossroads. What will you do?", [choice1, choice2])

# Start the game
play_sto
