# Andrew Kuhn
## CS-499 ePortfolio
## Southern New Hampshire University


## Professional Self-Assessment

	Completing my coursework at Southern New Hampshire University and developing my ePortfolio showcases my strengths in several ways. By completing my coursework at SNHU I have been able to learn many new things that I can help bring to a software development team. I have studied teamwork collaboration and understanding the importance an engineer plays within a team. SNHU has also taught me critical skills in the industry, such as using git hub to work together on a team projects, work on my own branch of code and deploy, as necessary. Communication has been one of the most important values that I have taken away from SNHU. To be able to develop code is great but communicating your ideas and problems in an effective manner can make like that much easier. When working with stake holders and scoping out a project, communication is the number one asset you can have. I have learned that if topics are not effectively communicated it can lead a project to fail quickly. While studying at SNHU I have had the time to study several types of software including data structures, algorithms, databases, software engineering and security. These are several pieces that all fit together when working towards my career goal as a well-rounded software developer.
	In the artifacts that I have chosen, I decided to pick three different programming languages and three completely different types of code. By doing this, it shows my diversity in the software world. My first artifact is a Python program that I created my very first term at SNHU. This artifact works with dictionaries and arrays. My second artifact is a Java program that I created in a later term at SNHU. I chose this program because it takes users input, allows for several mathematical equations to be performed. My third artifact is the one I feel is most important because I developed this SQL query while working for my current company. This was a small project I took on my own, and by creating this query it allowed me to save around 50 hours of work per year. It is a rather complex query that involves select statements within select statements. Putting these three artifacts together, shows how my abilities have changed and grown since beginning my studies.

 
 
## Code Review for 3 pieces of code (2 links)

Code review [Video 1](https://youtu.be/OmBl6OdzFpI)

Code review [Video 2](https://youtu.be/nfffoUeilz0)

## Software Design and Engineering

### Narrative

This artifact is a python program that I created in my first term at SNHU. It creates a dictionary, and based on a prompt from the user, it sorts and prints the dictionary by different values. I chose this artifact because it was one of the first things that I created, however it shows a lot of potential. It shows the use of Boolean values, loops, dictionaries and taking inputs. To improve this artifact, I chose to strip the users input to be all lowercase letters and remove any possible whitespace. This will help deter any errors in the users input and still have the program work accordingly. I also added comments to the code so it can easily be understood what is being done in every piece of the code. I wrote this when I was newer to coding and did not understand the importance of comments. I feel that I have met the course objectives and have successfully made this code better. I did not face many challenges when enhancing this code as they were very simple changes such as changing the users input to be lower case and stripped of whitespace, python makes this very easy to do. And when it came to adding comments, I already knew what was being done in the code so the commenting was very easy to do.

```python
#Create Dictionary
movie_dictionary = {"Munich": [2005, "Steven Spielberg"],
                    "The Prestige": [2006, "Christopher Nolan"],
                    "The Departed": [2006, "Martin Scorsese"],
                    "Into the Wild": [2007, "Sean Penn"],
                    "The Dark Knight": [2008, "Christopher Nolan"],
                    "Mary and Max": [2009, "Adam Elliot"],
                    "The King's Speech": [2010, "Tom Hooper"],
                    "The Artist": [2011, "Michel Hazanavicius"],
                    "The Help": [2011, "Tate Taylor"],
                    "Argo": [2012, "Ben Affleck"],
                    "12 Years a Slave": [2013, "Steve McQueen"],
                    "Birdman": [2014, "Alejandro G. Inarritu"],
                    "Spotlight": [2015, "Tom McCarthy"],
                    "The BFG": [2016, "Steven Spielberg"]}

#Prompt user to enter a year

promptforyear = True
year = int(input('Enter a year between 2005 and 2016:\n'))

#Based on year chosen, either prints movies from that year or prints "N/A"
if year < 2005 or year > 2016:
    print("N/A")
else:
    for key, value in movie_dictionary.items():
        if value[0] == year:
            print(key + ", " + str(value[1]))
    promptforyear = False

#Define and create menu
menu = 'MENU' \
       '\nSort by:' \
       '\ny - Year' \
       '\nd - Director' \
       '\nt - Movie title' \
       '\nq - Quit\n'
promptuser = True
first_prompt = True
#Print Menu

while promptuser:
    if first_prompt == True:
        print()
        first_prompt = False
    print(menu)

#Prompt user to choose an option

    user_input = input('Choose an option:\n').lower().strip()
#Strip users input of whitespace and make lower case
    
#If user enters 'q' quit program
    if user_input == 'q':
        promptuser = False
#If user enters 'y' sort movie dictionary by year        
    elif user_input == 'y':
        years_sorted = {}
        for key, value in sorted(movie_dictionary.items(), key=lambda item: (item[1], item[0])):
            year = value[0]
            title = key
            director = value[1]
            if year not in years_sorted:
                years_sorted[year] = [[title, director]]
            else:
                years_sorted[year].append([title, director])
        for year in sorted(years_sorted):
            print(year, end=':\n')
            movies = years_sorted[year]
            for movie in movies:
                print("\t" + movie[0] + ", " + movie[1])
            print()
#If user enters 'd' sort movie dictionary by director            
    elif user_input == 'd':
        directors_sorted = {}
        for key, value in sorted(movie_dictionary.items(), key=lambda item: (item[1][1])):
            year = value[0]
            title = key
            director = value[1]
            if director not in directors_sorted:
                directors_sorted[director] = [[title, year]]
            else:
                directors_sorted[director].append([title, year])
        for director in sorted(directors_sorted):
            print(director, end=':\n')
            movies = directors_sorted[director]
            for movie in movies:
                print("\t" + movie[0] + ", " + str(movie[1]))
            print()
#If user enters 't' sort movie dictionary by title
    elif user_input == 't':
        for key, value in sorted(movie_dictionary.items(), key=lambda item: (item[0], item[1])):
            print(key, end=':\n')
            print("\t" + str(value[1]) + ", " + str(value[0]) + "\n")
#If user enters anything else, print 'N/A' which will loop over to print menu again
    else:
        print("N/A")
```

## Algorithm and Data Structures

### Narrative

The second artifact that I have chosen is a Java program that is used to calculate weights. I created this about two years ago in one of my SNHU classes. I can justify putting this into my portfolio because it uses several mathematics, takes input, and gives outputs. By using this piece, it showcases my abilities to use different mathematics in the java language. To improve this artifact, I allowed the user to input how many weights they wanted to input to be calculated. Originally this value was set to 5, but I figured it would be more useful if the user could enter however many weights they wanted to. I would say that I successfully met the requirements of my enhancements since I added this feature, and it works successfully. As I was enhancing this project, I quickly remembered how much I do not like using Java, but it was a great way to reteach myself how it works and what would be needed to adjust the variables it orders to make this code work the way that I wanted.

```java
package com.mycompany.weighttracker;

/**
 *
 * @author akuhn
 */
import java.util.Scanner;

public class PeopleWeights {
      static int WEIGHT_ARRAY_SIZE = 99;
      static double[] weightsOfPeople = new double[WEIGHT_ARRAY_SIZE];
      static double weightElement;
      static double sum = 0.0;
      static Scanner scnr = new Scanner(System.in);


      public static void main(String[] args)
      {
         GetWeights();
         WeightsSum();
         WeightsAverage();
         WeightsMax();
         return;
      }

/**
 * Takes input for the weights and store them inside our array.
 */
      public static void GetWeights()
      {
         int i = 0; // Local count variable.
            System.out.println("How many weights would you like to enter?");
            WEIGHT_ARRAY_SIZE = scnr.nextInt();
    // Take input for the weights and store them in our array.
         for(i = 0; i < WEIGHT_ARRAY_SIZE; i++)
         {
            System.out.println("Enter weight " + (i + 1) + ": ");
            weightElement = scnr.nextDouble();
            weightsOfPeople[i] = weightElement;
         }

    // Display what the user entered
         System.out.print("\nYou entered: ");
         for(i = 0; i < WEIGHT_ARRAY_SIZE; i++)
         {
            System.out.print(weightsOfPeople[i] + " ");
         }

         return;
      }

/**
 * Gets the sum of our weights and then displays that sum.
 */
      static void WeightsSum()
      {
         int i = 0;

         for(i = 0; i < WEIGHT_ARRAY_SIZE; i++)
         {
            sum += weightsOfPeople[i];
         }

         System.out.println("\nTotal weight: " + sum);

         return;
      }

/**
 * Gets the average of our weights and then displays that average.
 */
      static void WeightsAverage()
      {
         double averageWeight = 0.0;

    // Convert WEIGHT_ARRAY_SIZE to a double for good calculation.
         averageWeight = sum / (double)WEIGHT_ARRAY_SIZE;

         System.out.println("Average weight: " + averageWeight);

         return;
      }

/**
 * Gets the max of our weights and then displays that max.
 */
      static void WeightsMax()
      {
         int i= 0;
         double maxWeight = 0.0;

         for(i = 0; i < WEIGHT_ARRAY_SIZE; i++)
         {
            if(weightsOfPeople[i] > maxWeight)
            {
                  maxWeight = weightsOfPeople[i];
            }
         }

         System.out.println("Max weight: " + maxWeight);

         
      return;
   }
}
```

## Database

### Narrative

The artifact that I have chosen to represent my work on databases is a SQL query that I personally developed for my own professional use. It is a SQL query that will search for providers on multiple look up tables and print out which tables a provider is on. I created this in August of 2019. The purpose of creating this query, was for work I was often tasked with finding and removing providers off look up tables, which was often very time consuming. By creating this query, I was able to save approximately 3 or 4 hours per week of work. This case specifically shows my knowledge of take what I have learned at SNHU and using it in the real world. The query was very successful, and although there were not many refinements to it, I did clean up the spacing to make it look nicer. I would say this easily met my objectives from milestone one. Building this query was very time consuming, although it helped me learn how to perform select statements within select statements. And my biggest challenge through out creating it was learning and understanding the different tables that data lives on in our production environment.

```sql
SELECT TableName, KeyName
FROM Ens_Util.LookupTable
WHERE KeyName IN (
    SELECT Extension || '^' || AssigningAuthorityName AS IDString
    FROM HS_Registry_Person.UserIdentifier
    WHERE UserClinician IN (
        SELECT UserClinician
        FROM HS_Registry_Person.UserIdentifier
        WHERE Extension = '###'
        AND AssigningAuthorityName = 'NPI'
    )
)
OR KeyName LIKE '###^%'
OR KeyName IN (
    SELECT Extension AS IDString
    FROM HS_Registry_Person.UserIdentifier
    WHERE UserClinician IN (
        SELECT UserClinician
        FROM HS_Registry_Person.UserIdentifier
        WHERE Extension = '###'
        AND AssigningAuthorityName = 'NPI'
    )
)
ORDER BY TableName,KeyName
```
