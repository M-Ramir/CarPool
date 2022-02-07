# CarPool

//CarPool : Asks user a series of questions regarding their daily miles driven, cost of gas, mpg, and any parking 
// fees or tolls. After this the program calculates how much money you could be saving daily, monthly, and yearly if 
// you carpooled.

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace CarPool
{
    internal class Program
    {
        static void Main(string[] args)

        {
            // Message to user before they enter info
            // Lets them know what to expect using this program
            Console.WriteLine(@"
            ***************** WELCOME TO THE CARPOOL CALCULATOR ************************
            ****************************************************************************
            Here you'll be asked your daily miles driven (example. 200, 200.5),*********
            cost per gallon of gas, your average mpg, and any parking fees and/or tolls
            you pay on a daily basis! **************************************************
            ****************************************************************************
            With this information we'll be able to give you an estimate on how much***** 
            you would save carpooling.**************************************************
            ***************************** LETS GET STARTED! ****************************");

            // Puts line between message to user and prompt
            Console.WriteLine("\n");

            // Prompts user to input total miles driven per day
            Console.WriteLine("Enter total miles driven per day : \n");

            // Stores input given by user so it can be used in calculations
            double totalMiles = double.Parse(Console.ReadLine());

            // Prompts user to input their cost per gallon of gasoline
            Console.WriteLine("Enter cost per gallon of gasoline (in cents) : \n");

            // Stores input given by user so it can be used in calculations
            double costOfGas = double.Parse(Console.ReadLine());

            // Prompts user to input their average miles per gallin
            Console.WriteLine("Enter your average miles per gallon : \n");

            // Stores input given by user so it can be used in calculations
            double milesPerGallon = double.Parse(Console.ReadLine());

            // Prompts user to enter their daily parking fees
            Console.WriteLine("Enter parking fees per day (in cents) : \n");

            // Stores input given by user so it can be used in calculations
            double parkingFees = double.Parse(Console.ReadLine());

            // Prompts user to input their daily tolls
            Console.WriteLine("Enter tolls per day (in cents): \n ");

            // Stores input given by user so it can be used in calculations
            double tollsPerDay = double.Parse(Console.ReadLine());

            // Takes user inputs shown above and uses them to calucate their daily driving cost
            double dailyDrivingCost = (totalMiles / milesPerGallon) * costOfGas + parkingFees
                + tollsPerDay;

            // Takes users daily driving cost and multiplies it by average days in a month
            // Gives user an estimated monthly drving savings if they carpooled
            double monthlyDriving = dailyDrivingCost * 30;

            // Gives user their yearly savings from carpooling
            double yearlyDriving = monthlyDriving * 12;

            // Tells user their daily, monthly, and yearly savings with carpooling
            Console.WriteLine($"Your direct daily savings due to carpooling is : ${dailyDrivingCost} \n");
            Console.WriteLine($"This means on average you save ${monthlyDriving} monthly \n" +
                $"and ${yearlyDriving} per year!\n");

            // Says thank you to user and prompts them to exit
            Console.WriteLine(" THANK YOU FOR USING THE CARPOOL CALCULATOR!");
        }
        
        
    }
   
}
