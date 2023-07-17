# rk
C++ Project - TIC-TAC-TOE

/*
Chapter 7 Project 1
Programming Challenge #18
TIC-TAC-TOE Game
Author: <Rania Krourou>
Date: <04/24/2021>
*/
#include <iostream>
using namespace std;
// global variable
const int SIZE = 3;
bool gameOver = true;
char playerOne = 'X';
char playerTwo = 'O';
//function prototypes
void displayBoard(char[][SIZE]);
bool determineWinner(char[][SIZE], char);
void userInput(char[][SIZE], char);
int main() {
    int turns = 0;
    char gameBoard[][SIZE] = {{'*', '*', '*'},
                               {'*', '*', '*'},
                               {'*', '*', '*'}};
    cout << "\nWelcome to a board game of TIC-TAC-TOE!\n";
    while(gameOver){
         if (turns == 9)
         break;
        displayBoard(gameBoard);
        cout << "You are Player 1: \n";
        userInput(gameBoard,playerOne);
        turns++;
        if(determineWinner(gameBoard, playerOne)){
            displayBoard(gameBoard);
            cout << "\nPlayer 1 wins this game! Congrats!\n";
            return 0;
}
 displayBoard(gameBoard);
        cout << "You are Player 2: \n";
        userInput (gameBoard, playerTwo);
        turns++;
        if(determineWinner(gameBoard, playerTwo)){
            displayBoard(gameBoard);
            cout << "\nPlayer 2 wins this game! Congrats!\n";
            return 0;
} }
    displayBoard(gameBoard);
    cout << "It's a tie between both. The game has ended!\n";
    return 0;
}
void displayBoard(char gameBoard[][SIZE])
{
    for (int col = 0; col < SIZE; col++)
        cout << "\t" << col+1;
    cout << endl << endl;
    for (int row = 0; row < SIZE; row++)
    {
        cout << row+1;
        for (int col = 0; col < SIZE; col++)
            cout << "\t" << gameBoard[row][col];
        cout << endl;
}
    cout << endl;
}
void userInput(char gameBoard[][SIZE], char player){
    int row;
int col;
do
{
do {
        cout << "Enter a number between 1-3 for row.";
        cout << "\nRow: ";
        cin >> row;
        }while (row > SIZE || row < 0 );
        do {
        cout << "Enter a number between 1-3 for column.";

 cout << "\nColumn: ";
cin >> col;
}while (col > SIZE || col < 0 );
}while (gameBoard[row-1][col-1] != '*'); gameBoard[row-1][col-1] = player;
}
bool determineWinner(char gameBoard[][SIZE], char){
bool gameOver; char playerOne; char playerTwo;
for(int row = 0; row < SIZE; row++) // PLAYER ONE
{
if ((gameBoard[0][0] == 'X') && (gameBoard[0][1] == 'X') && (gameBoard[0][2] == 'X')) {
return true; }
else if ((gameBoard[1][0] == 'X') && (gameBoard[1][1] == 'X') && (gameBoard[1][2] == 'X')){
return true; }
else if ((gameBoard[2][0] == 'X') && (gameBoard[2][1] == 'X') && (gameBoard[2][2] == 'X')){
return true; }
else if ((gameBoard[0][0] == 'X') && (gameBoard[1][0] == 'X') && (gameBoard[2][0] == 'X')){
return true; }
else if ((gameBoard[0][1] == 'X') && (gameBoard[1][1] == 'X') && (gameBoard[2][1] == 'X')){
return true;
    }
 
else if ((gameBoard[2][0] == 'X') && (gameBoard[1][1] == 'X') &&
(gameBoard[0][2] == 'X')){
           return true;
}
        else if ((gameBoard[0][0] == 'O') && (gameBoard[0][1] == 'O') &&
(gameBoard[0][2] == 'O')) {
            return true;
        }
        else if ((gameBoard[1][0] == 'O') && (gameBoard[1][1] == 'O') &&
(gameBoard[1][2] == 'O')){
            return true;
        }
        else if ((gameBoard[2][0] == 'O') && (gameBoard[2][1] == 'O') &&
(gameBoard[2][2] == 'O')){
           return true;
        }
        else if ((gameBoard[0][0] == 'O') && (gameBoard[1][0] == 'O') &&
(gameBoard[2][0] == 'O')){
           return true;
        }
        else if ((gameBoard[0][1] == 'O') && (gameBoard[1][1] == 'O') &&
(gameBoard[2][1] == 'O')){
           return true;
        }
        else if ((gameBoard[0][2] == 'O') && (gameBoard[1][2] == 'O') &&
(gameBoard[2][2] == 'O')){
           return true;
        }
        else if ((gameBoard[0][0] == 'O') && (gameBoard[1][1] == 'O') &&
(gameBoard[2][2] == 'O')){
           return true;
        }
        else if ((gameBoard[2][0] == 'O') && (gameBoard[1][1] == 'O') &&
(gameBoard[0][2] == 'O')){
           return true;
        }
    }
         return false;
}
