# pythonProject6
# BOD 1, 2, 3 a 4

oddelovac = 40 * "-"
USERNAME = input("Please enter your username: ")
PASSWORD = input("Please enter your password: ")
welcome = "Welcome to the app. Please log in : "
print(oddelovac)
print(welcome)
print("USERNAME: ", USERNAME)
print("PASSWORD: ", PASSWORD)
print(oddelovac)

users = {
    "bob": "123",
    "ann": "pass123",
    "mike": "password123",
    "liz": "pass123"
}

TEXTS = ['''
Situated about 10 miles west of Kemmerer, 
Fossil Butte is a ruggedly impressive 
topographic feature that rises sharply 
some 1000 feet above Twin Creek Valley 
to an elevation of more than 7500 feet 
above sea level. The butte is located just 
north of US 30N and the Union Pacific Railroad, 
which traverse the valley. ''',

         '''At the base of Fossil Butte are the bright 
red, purple, yellow and gray beds of the Wasatch 
Formation. Eroded portions of these horizontal 
beds slope gradually upward from the valley floor 
and steepen abruptly. Overlying them and extending 
to the top of the butte are the much steeper 
buff-to-white beds of the Green River Formation, 
which are about 300 feet thick.''',

         '''The monument contains 8198 acres and protects 
a portion of the largest deposit of freshwater fish 
fossils in the world. The richest fossil fish deposits 
are found in multiple limestone layers, which lie some 
100 feet below the top of the butte. The fossils 
represent several varieties of perch, as well as 
other freshwater genera and herring similar to those 
in modern oceans. Other fish such as paddlefish, 
garpike and stingray are also present.'''
         ]

if USERNAME in users.keys() and PASSWORD == users[USERNAME]:
    print("We have 3 texts to be analyzed.")
    number_text = (1, 2, 3)
    text_number = int(input("Enter a number btw. 1 and 3 to select: "))
    number = text_number - 1
else:
    print("You are not registered user.")
    exit(1)

print(oddelovac)

# 5 - statistiky

vyskyt_slov = {}
item = 0

for item in TEXTS[number:text_number]:
    print("There are", len(item.split()),"words in the selected text.")

muj_text = "".join(TEXTS[number:text_number])

muj_text_up = 0
muj_text_low = 0
muj_text_tit = 0
muj_text_num = 0
muj_text_dig = 0
my_sum = 0
for word in muj_text.split():
    if word[0:].istitle():
        muj_text_tit += 1
    if word[0:].isupper():
        muj_text_up += 1
    if word[0:].islower():
        muj_text_low += 1
    if word[0:].isnumeric():
        muj_text_num += 1


print("There are " + str(muj_text_tit) + " titlecase words")
print("There are " + str(muj_text_up) + " uppercase words")
print("There are " + str(muj_text_low) + " lowercase words")
print("There are " + str(muj_text_num) + " numeric strings")
print(oddelovac)

muj_text = "".join(TEXTS[number:text_number]) # vytiskne text, ten co chci

words = muj_text.replace("." , " ").replace(",", " ").split()
lenghts = [len(word) for word in words]

max_lenght = max(lenghts)

lenght1 = [0 for x in range(max_lenght + 1)]

for lenght in lenghts:
    lenght1[lenght] += 1

for lenght in range(len(lenght1)):
    if lenght1[lenght] > 0:
        print(lenght,"*"*lenght1[lenght],lenght1[lenght])

print(oddelovac)

my_sum = 0

for word in muj_text.split():
    if word[0:].isnumeric():
        my_sum += float(word)

print("If we summed all the numbers in this text we would get: ", str(my_sum))
print(oddelovac)
