class VacuumCleaner:
    print("192372261-narasimha")
    def __init__(self, grid):
        self.grid = grid
        self.position = (0, 0)  # Starting position

    def clean(self):
        x, y = self.position
        if self.grid[x][y] == 'D':
            self.grid[x][y] = 'C'  # Clean the dirty cell
            print(f"Cleaned cell at {self.position}")

    def move(self, direction):
        x, y = self.position
        if direction == 'up' and x > 0:
            self.position = (x - 1, y)
        elif direction == 'down' and x < len(self.grid) - 1:
            self.position = (x + 1, y)
        elif direction == 'left' and y > 0:
            self.position = (x, y - 1)
        elif direction == 'right' and y < len(self.grid[0]) - 1:
            self.position = (x, y + 1)

        self.clean()

# Example grid: 'C' for clean, 'D' for dirty, 'X' for obstacle
grid = [
    ['C', 'D', 'C'],
    ['D', 'X', 'D'],
    ['C', 'C', 'C']
]

vacuum = VacuumCleaner(grid)
vacuum.move('down')
vacuum.move('right')
