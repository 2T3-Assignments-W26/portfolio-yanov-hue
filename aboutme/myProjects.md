# My projects 

## Alien Shooter Console Video Game  

### Description 

This was a project I worked on for my programming final it was a game run in the console which included mutliple mechanics like movement, shooting, teleportation, emp blasts, enemy alien ships and rounds that progressed in difficulty. 
 
### Technologies Used  

This project was created inside of Visual Studio code and ran inside of the terminal. The project was coded in the c# language using .NET framework. 

### Code Snippets  

**Snippet of draw function for ship teleportation** 

``` 
oldship(ShipX, ShipY);
DrawPortal(ShipX, ShipY, " ");

int topMargin = 2;
int bottomMargin = 2;
int minY = topMargin;
int maxY = Console.WindowHeight - 1 - bottomMargin;
int minX = 0;
int maxX = Console.WindowWidth - 1;

int newX = ShipX + rand.Next(-100, 100);
int newY = ShipY + rand.Next(-100, 100);

ShipX = Math.Max(minX, Math.Min(maxX, newX));
ShipY = Math.Max(minY, Math.Min(maxY, newY));

oldShipX = ShipX;
oldShipY = ShipY;   
```    

**Snippet of lazer Ability**  
```
if (k == ConsoleKey.Q && energy > 5)
{
 for (int i = 0; i < MaxLasers; i++)
{
if (LaserY[i] < 0) 
{     LaserX[i] = ShipX; 
   LaserY[i] = ShipY - 1; 
      energy = energy - 5;
   break;
   }
 } 
}
```    

**Snippet of lazer Collision with enemies code** 

``` 
for (int i = 0; i < LaserX.Length; i++)
{
    if (LaserY[i] >= 0)
    {
        for (int j = 0; j < EnemyX.Length; j++)
        {
            if (EnemyActive[j])
            {
                if (LaserX[i] >= EnemyX[j] - 1 && LaserX[i] <= EnemyX[j] + 1 && LaserY[i] == EnemyY[j])
                {
                    EnemyHealth[j] -= 50;
                    if (EnemyHealth[j] <= 0)
                    {
                        enemiesKilled++;
                        EnemyActive[j] = false;
                        Console.SetCursorPosition(EnemyX[j], EnemyY[j]);
                        Console.Write("*");
                        System.Threading.Thread.Sleep(10);
                        Console.Write(" ");

                    }
                }
            }
        }
    }
}
```   

### ScreenShots 

**Menu**  

![menu](./Screenshot%202026-02-28%20222624.png) 

**Game Look**  

![look](./Screenshot%202026-02-28%20222652.png) 

**Code Length**  

![code](./Screenshot%202026-02-28%20222730.png) 

### What I learned 

This project was invaluable for me when it comes to developping my knowledge and practical skills that are needed for programming it helped me  dive head first into more complicated topics like how to use arrays and functions in synergy with  multiple useful features for video game developement like drawing and simulating game experience on the terminal this includes things like creating smouth movement, drawing out beams, checking and managing positioning among many others. More then anything else this project allowed me to improve my critical thinking and problem solving skills as it allowed me to think critically in order to bring my ideas to life. 

 

 ## Rainfall Calculation Project  

 ### Description 
 This was one of my programming projects which worked by prompting the user to input the amount of rainfall for each month of the year, store those inputs in an array and calculate statistics like average rainfall per month, total rainfall that year and the months that had the most and least amounts of rainfall. 

 ### Technologies Used 

 This project was created inside of Visual Studio code and ran inside of the terminal. The project was coded in the c# language using .NET framework. 
 
 ### Code Snippets  

 **Snippet of array storing code**   
```
 for (int i = 0; i < ARRAYSIZE; i++)
{
    Console.WriteLine("What was the total rainfall in mm during the month of " + months[i] + ".");
    while (!int.TryParse(Console.ReadLine(), out rainfallval) || rainfallval < 0)
    {
        Console.WriteLine("Please enter a whole, positive number");
    }
    montharray[i] = rainfallval;
    Console.Clear();
} 
```  

**Snippet of statistics calculation code** 

```  
static int calctotalrain(Int32[] montharray)
{
    return montharray.Sum();

}

static double calcaveragerain(Int32[] montharray)
{
    return montharray.Average();
}

static int highestrain(Int32[] montharray)
{
    Int32 highestnum = montharray[0];
    Int32 chosenmonth = 0;
    for (int i = 0; i < ARRAYSIZE; ++i)
    {
        if (montharray[i] > highestnum)
        {
            highestnum = montharray[i];
            chosenmonth = i;
        }

    }
    return chosenmonth;
}  
```   

### ScreenShots 

**Code Length** 

![length](./Screenshot%202026-02-28%20225426.png) 

**Code output** 

![output](./Screenshot%202026-02-28%20225625.png) 

### What I Learned 
 
This project help me explore and solidify my understanding for a mirade of different features in c# programming which includes arrays, loops, functions, switch cases, and how all of them can be formed together to accomplish useful tasks. 

