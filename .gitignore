#include<iostream>
#include<string>
using namespace std;


#include "libsqlite.hpp"

int main()
{
    string sqliteFile = "Game";
    
    try
    {
        sqlite::sqlite db( sqliteFile );
        
        string test;
        cout << "Enter a name of enemy, who will fight vs Steve: ";      // Enter the name of enemie, who will fight Steve
        cin >> test;
        
        
        auto cur = db.get_statement();
            
        cur->set_sql("SELECT * FROM Enemies WHERE EnemyName = ?;");      // Takes the information from the table into program
  
        
        cur->prepare();  
        cur->bind(1, test);
        cur->step();
        string boss = cur->get_text(0);    
        
        cur->prepare();
        cur->bind(1, test);
        cur->step();
        string name = cur->get_text(1);        
        
        cur->prepare(); 
        cur->bind(1, test);
        cur->step();
        int health = cur->get_int(2);                       // Retrieving information from the table and applying it to variables.
        
        cur->prepare(); 
        cur->bind(1, test);
        cur->step();
        int damage = cur->get_int(3);
        
        cur->prepare();
        cur->bind(1, test);
        cur->step();
        int speed = cur->get_int(4);
        
        cur->prepare(); 
        cur->bind(1, test);
        cur->step();
        int droprate = cur->get_int(5);
                
        
        cout << "Boss: " << boss << endl;
        cout << "Name: " << name << endl;
        cout << "Health: " << health << endl;                 // Shows the stats/information of each enemie
        cout << "Damage: " << damage << endl;
        cout << "Speed: " << speed << endl;
        cout << "Drop Rate: " << droprate << endl;
        
       
        
    }
    catch( sqlite::exception e )                                // catch all sql issues
    {
        std::cerr << e.what() << std::endl;
        return 1;
    }
    
    
}
