#include <iostream>
#include <cmath>
#include <iomanip>
#include <string>
#include <fstream>

int main ()
{
   std::cout << "Part 1:\n";
   
   //coordinate variables
   int x1 = 0, y1 = 0;
   int x2 = 6, y2 = 6;
   
   //calculate the differences
   int dx = x2 - x1;
   int dy = y2 - y1;
   
   //calculate Pythagorean Distance
   double pythagoreanDistance = sqrt(pow(dx,2) + pow(dy, 2));
   
   //calculate Manhattan Distance
   int manhattanDistance = abs(dx) + abs(dy);
   
   //display distances to two decimals
   std::cout << std::fixed << std::setprecision(2);
   std::cout << "Pythagorean distance: " << pythagoreanDistance << std::endl;
   std::cout << "Manhattan distance: " << manhattanDistance << std::endl;
   
   std::cout << "\nPart 2:";
   
   //user puts in tweet
   std::string tweet;
   std::cout << "\nPlease enter your tweet: ";
   getline(std::cin,tweet); //reads everything rather than the first space character
   
   //determine if string exceeds X's limit
   int tweetLength = tweet.length();
   
   if (tweetLength > 280) 
   {
       std::cout << "\nYour tweet exceeds the 280 character limit...No bueno!!" << std::endl;
   } else {
       std::cout << "\nYour tweet is within the limit!" << std::endl;
       
   }
   
   //write the string and length to an output file
    std::ofstream outputFile ("tweetOutput.txt");
    if (outputFile.is_open())
    {
        outputFile << "Tweet: " << tweet << std::endl;
        outputFile << "Length: " << tweetLength << std::endl;
        outputFile.close();
    }   else {
        
        std::cout << "Error: Could not open file for writing." << std::endl;
    }
   
}
