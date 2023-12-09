# Rebekah Joy E. Sevial
# BSCPE 2-4
# Merge Two Sorted Linked Lists

# Define a Node class to represent a single node in the linked list
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Function to merge two sorted linked lists
def merge_sorted_lists(list1, list2):
    # Create a new Node as the starting point for the merged list
    merged_list = Node(0)
    current_node = merged_list

    # Merge the two sorted lists
    while list1 is not None and list2 is not None:
        if list1.data <= list2.data:  # Use <= to ensure non-decreasing order
            current_node.next = list1
            list1 = list1.next
        else:
            current_node.next = list2
            list2 = list2.next
        current_node = current_node.next

    # If one of the lists is not fully traversed, append the remaining nodes
    if list1 is not None:
        current_node.next = list1
    elif list2 is not None:
        current_node.next = list2

    return merged_list.next

# Function to print the elements of a linked list
def print_linked_list(head):
    current_node = head
    while current_node is not None:
        print(current_node.data, end=" -> ")
        current_node = current_node.next
    print("None")

# Function to get a valid integer input from the user
def get_valid_input(prompt, min_value, max_value):
    while True:
        try:
            value = int(input(prompt))
            if min_value <= value <= max_value:
                return value
            else:
                raise ValueError(f"Value should be in the range [{min_value}, {max_value}]. Please try again.")
        except ValueError:
            print("Error: Please enter a valid integer.")

# Function to create a linked list based on user input
def create_linked_list(size_prompt, value_prompt):
    head = None
    try:
        while True:
            size = get_valid_input(size_prompt, 0, 50)
            if 0 <= size <= 50:
                break

        values = [get_valid_input(value_prompt.format(i + 1), -100, 100) for i in range(size)]
        values.sort()

        for data in values:
            new_node = Node(data)
            if head is None:
                head = new_node
            else:
                current_node = head
                while current_node.next is not None:
                    current_node = current_node.next
                current_node.next = new_node
    except ValueError as e:
        print(f"Error: {e}. Please enter valid input.")

    return head

# Ask the user for the size of Linked List 1
list1 = create_linked_list("Enter the size of Linked List 1 (0 to 50): ", "Enter value for node {} in Linked List 1 (-100 to 100): ")

# Ask the user for the size of Linked List 2
list2 = create_linked_list("Enter the size of Linked List 2 (0 to 50): ", "Enter value for node {} in Linked List 2 (-100 to 100): ")

# Print the input lists
print("\nLinked List 1:")
print_linked_list(list1)

print("\nLinked List 2:")
print_linked_list(list2)

# Merge the two lists
merged_list = merge_sorted_lists(list1, list2)

# Print the merged list
print("\nMerged List:")
print_linked_list(merged_list)
