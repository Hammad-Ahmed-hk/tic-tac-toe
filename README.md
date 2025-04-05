1
import random
import jpg

def print_board(board):
    """Prints the Tic-Tac-Toe board."""
    for row in board:
        print(" | ".join(row))
        print("-" * 9)

def check_winner(board):
    """Checks for a winner in the board."""
    # Check rows, columns, and diagonals for a winner
    for i in range(3):
        if board[i][0] == board[i][1] == board[i][2] != ' ':
            return board[i][0]  # Row winner
        if board[0][i] == board[1][i] == board[2][i] != ' ':
            return board[0][i]  # Column winner
    if board[0][0] == board[1][1] == board[2][2] != ' ':
        return board[0][0]  # Diagonal winner
    if board[0][2] == board[1][1] == board[2][0] != ' ':
        return board[0][2]  # Other diagonal winner
    return None  # No winner yet

def is_board_full(board):
    """Checks if the board is full."""
    return all(cell != ' ' for row in board for cell in row)

def get_available_moves(board):
    """Returns a list of available moves."""
    return [(i, j) for i in range(3) for j in range(3) if board[i][j] == ' ']

def user_move(board):
    """Handles the user's move."""
    while True:
        try:
            move = int(input("Enter your move (1-9): ")) - 1
            row, col = divmod(move, 3)
            if board[row][col] == ' ':
                board[row][col] = 'X'  # User is 'X'
                break
            else:
                print("Invalid move. Cell already occupied.")
        except (ValueError, IndexError):
            print("Invalid input. Please enter a number between 1 and 9.")

def computer_move(board):
    """Handles the computer's move."""
    move = random.choice(get_available_moves(board))
    board[move[0]][move[1]] = 'O'  # Computer is 'O'

def play_game():
    """Main function to play the game."""
    board = [[' ' for _ in range(3)] for _ in range(3)]
    print("Welcome to Tic-Tac-Toe!")
    print_board(board)
    while True:
        user_move(board)
        print_board(board)
        if check_winner(board) == 'X':
            print("Congratulations! You win!")
            break
        if is_board_full(board):
            print("It's a draw!")
            break
        computer_move(board)
        print_board(board)
        if check_winner(board) == 'O':
            print("Computer wins! Better luck next time.")
            break
        if is_board_full(board):
            print("It's a draw!")
            break

if __name__ == "__main__":
    play_game()
