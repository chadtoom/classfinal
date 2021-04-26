#include <iostream> 
#include <string> 

using namespace std; 

string new_mes(string str, int shift); 

int main()
{
    string mes, code;  
    int shift; 

    cout << "Please enter a message: " << endl; 
    getline(cin, mes);  

    cout << "Enter shift amount? ";
    cin >> shift; 

    while (shift < 1)
    {
        cout << "You have entered an invalid number. "<< endl; 
        cout << "Please try again." << endl; 
        cout << "Enter number" << endl; 
        cin >> shift; 
    }

    code = new_mes(mes, shift); 

    cout << "Encoded message: " << code << endl; 


    return 0;
}

string new_mes(string str, int shift)
{
    string num = str; 
    int length; 

    length = (int)num.length(); 

    for (int i = 0; i < length; i++)
    {
        if (isalpha(num[i]))
        {
            for (int j = 0; j < shift; j++)
            {
                if (num[i] == 'z')
                {
                    num[i] = 'a'; 
                }
                else if (num[i] == 'Z')
                {
                    num[i] = 'A'; 
                }
                else 
                {
                    num[i]++; 
                }
            }
        }
    }

    return num; 
}
