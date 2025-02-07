extends Node3D


# Define the size of the chessboard and the square size
var board_size : int = 8
var square_size : float = 1.0

func _ready():

	# Loop to create an 8x8 grid of squares
	for x in range(board_size):  # Loop through x (columns)
		for z in range(board_size):  # Loop through z (rows)
			var square : MeshInstance3D = MeshInstance3D.new()  # Declare the square variable here
			var plane_mesh : PlaneMesh = PlaneMesh.new()   # Create a flat square (PlaneMesh)
			square.mesh = plane_mesh           # Assign the mesh to the square
			square.scale = Vector3(square_size, 1, square_size)  # Make it thin and flat
			square.position = Vector3(x * square_size - (board_size * square_size) / 2, 0, z * square_size - (board_size * square_size) / 2)



			# Alternate colors for the squares using bitwise XOR
			if (x & 1) == (z & 1):  # Even-even or odd-odd (checkerboard pattern)
				square.material_override = load("res://Materials/black_material.tres")
			else:
				square.material_override = load("res://Materials/white_material.tres")


			add_child(square)  # Add the square to the Chessboard node
