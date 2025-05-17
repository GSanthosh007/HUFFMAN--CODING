# Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
### Step1:

Get the input string
### Step2:

Create tree nodes
### Step3:

Main function to implement huffman coding
### Step4:

calculate frequency of occurence
### Step5:
print the characters and its huffmancode
 
 
## Program:

``` Python
# Get the input String
# Step 1: Get the input string
input_string = "huffman coding"  # Example input string
# Step 2: Calculate frequency of each character in the input string
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1

# Create tree nodes
# Step 3: Create tree nodes
nodes = [[char, freq] for char, freq in frequency.items()]


# Main function to implement huffman coding
# Step 4: Main function to implement Huffman coding
while len(nodes) > 1:
    # Sort nodes based on frequency
    nodes = sorted(nodes, key=lambda x: x[1])

    # Pick two smallest nodes
    left = nodes.pop(0)
    right = nodes.pop(0)

    # Create a new node with combined frequency
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)

# The final node is the Huffman tree
huffman_tree = nodes[0]


# Calculate frequency of occurrence
# Step 5: Generate Huffman codes
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)



# Print the characters and its huffmancode
# Step 6: Print the characters and their Huffman codes
print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")




```
## Output:

### Print the characters and its huffmancode
![Screenshot 2025-05-17 144953](https://github.com/user-attachments/assets/fcfac609-6fec-40af-8c6a-465337da8684)




## Result
Thus the huffman coding was implemented to compress the data using python programming.
