```
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
