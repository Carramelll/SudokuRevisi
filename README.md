// SudokuRevisi
// Perbaikan Sudoku 
//Board 

#include "UI.h"
#include "Game.h" // Include Game.h for Game class definition
#include <iostream>

UI::UI() {}

void UI::setGame(Game* g) {
    game = g;
}

void UI::displayMessage(const std::string& message) {
    std::cout << message << std::endl;
}

void UI::displayMenu() {
    std::cout << "Select difficulty level:" << std::endl;
    std::cout << "1. Easy" << std::endl;
    std::cout << "2. Medium" << std::endl;
    std::cout << "3. Hard" << std::endl;
}

std::string UI::getDifficultyInput() {
    int choice;
    std::cout << "Enter your choice: ";
    std::cin >> choice;

    switch (choice) {
        case 1:
            return "easy";
        case 2:
            return "medium";
        case 3:
            return "hard";
        default:
            std::cout << "Invalid choice! Please enter a number between 1 and 3." << std::endl;
            return getDifficultyInput();
    }
}

void UI::displayBoard() {
    // Display the Sudoku board
    // You'll need to implement this function
}

void UI::getMoveInput(int& row, int& col, int& value) {
    std::cout << "Enter row (1-9), column (1-9), and value (1-9) separated by spaces: ";
    std::cin >> row >> col >> value;
}

bool UI::playAgain() {
    char choice;
    std::cout << "Play again? (y/n): ";
    std::cin >> choice;
    return (choice == 'y' || choice == 'Y');
}
