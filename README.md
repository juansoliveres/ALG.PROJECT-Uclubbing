# ALG.PROJECT-Uclubbing
This is a repository where we will work in the Uclubbing MVP.
      
    from random import randrange, uniform


    clubs_availables = {
        # Name_of_the_club : [#number of tables , #Price of one table,#club capacity(for tables),#grade by user]
        "1: Barcelo       ": [15, 120, 90],
        "2: Irish         ": [1, 30, 42],
        "3: Black_house   ": [17, 130, 102],
        "4: Fabrik        ": [10, 110, 60],
        "5: Goya          ": [13, 115, 78],
        "6: Theato_kapital": [20, 180, 120]
        }

    clubs_guide = {
        1: "1: Barcelo       ",
        2: "2: Irish         ",
        3: "3: Black_house   ",
        4: "4: Fabrik        ",
        5: "5: Goya          ",
        6: "6: Theato_kapital"
    }

    def main():
        try:
            for clubs in clubs_availables:
                if clubs == "1: Barcelo       " or clubs ==  "6: Theato_kapital" or clubs ==  "3: Black_house   ":
                    grade = [randrange(4,5) for p in range(0, 3)]
                    average_grade = round(sum(grade)/len(grade),1)
                elif clubs == "2: Irish         ":
                    grade = [randrange(1,2) for p in range(0, 3)]
                    average_grade = round(sum(grade)/len(grade),1)
                else:
                    grade = [randrange(2,4) for p in range(0, 3)]
                    average_grade = round(sum(grade)/len(grade),1)
                clubs_availables[clubs].append(average_grade)
                    #print(clubs_availables[clubs][-1])#shows the grade of each club

        print("Welcome to Ucclub , we will need you to provide some information for us in order to help you")
        name = input("Name :\n>> ")
        name = name.capitalize()
        def user_inputs():
            n_of_people = int(input("Number of people for the reservation :\n>> "))
            def clubbing():
                #club = int(input("What club do you want to make the reservation for ? ( please write the number )\n1: Barcelo\n2: Irish\n3: Black_house\n4: Fabrik\n5: Goya\n6: Theato_kapital\n>>"))

                print("club              |  Grade by users")
                print("_ _ _ _ _ _ _ _ _ |_ _ _ _ _ _ _ _ ")
                for i, p in clubs_availables.items():
                    print(i, "|  ", p[-1])
                club = int(input("\nWhat club do you want to make the reservation for ? ( please write the number )\n>> "))
                urclub = (clubs_guide[club])
                tableu = int((n_of_people/7)+1)
                tablerem = (clubs_availables[urclub][0]) - tableu
                if clubs_availables[urclub][0] > 0:
                    if tablerem >= 1:
                        natable = [tablerem, clubs_availables[urclub][1], clubs_availables[urclub][2], clubs_availables[urclub][3]]
                        ntable = {urclub: natable}
                        clubs_availables.update(ntable)
                        time = input("Time of the reservation (ex: 21h45): \n>> ")
                        price = tableu * (clubs_availables[urclub][1])
                        price_input = input("\nwould you like to get a 15% discount by booking drinks with the table ? each bottle is 50€\n>> ").lower()
                        bottle_price = 50
                        price_discount = ((price + bottle_price) * 0.85)
                        #inputs clubs
                        print(f"Hello {name}, the club you have chosen has {clubs_availables[urclub][0]} tables available, at {time} for {n_of_people} people")
                        if price_input == "yes":
                            print(f"The price would be of {price_discount}")
                        elif price_input == "no":
                            print(f"The price would be of {price}")
                        else:
                            print("Please answer the previous question by 'yes'/'no' next time. Have a good day")
                    else:
                        print(f'{urclub} does not have enough tables.')
                        cont = input('Do you want to book at another disco? ')
                        cont = cont.upper()
                        if cont == 'YES':
                            clubbing()
                        else:
                            return print('Thanks for using Uclubbing. Hope you liked the experience.')
                else:
                    print(f'{urclub} does not have any tables left')
                    cont = input('Do you want to book at another disco? ')
                    cont = cont.upper()
                    if cont == 'YES':
                        clubbing()
                    else:
                        return print('\nThanks for using Uclubbing. Hope you liked the experience.')
            clubbing()

            answer = input('\nDo you want to continue booking? ')
            answer = answer.upper()
            if answer == 'YES':
                user_inputs()
            else:
                print('\nThanks for using Uclubbing. Hope you liked the experience.')

        user_inputs()
    except ValueError:
        print("something went wrong , try again")
    except KeyError:
        print("Please provide the adequate number , start again")

main()
