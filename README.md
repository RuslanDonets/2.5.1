# Вводная часть
def greet()
    print("...............")
    print("Welcome to the game tic-tac-toe")
    print("..........")
    print("Input format: х y")
    print("x - line number")
    print("y - column number")
# Задаём игровую обалсть
def show():
    print()
    print(" │ 0 │ 1 │ 2 │ ")
    print("...............")
    for i, row in enumerate(field):
        row_str = f" {i} │ {'|'.join(row)}|"
        print(row_str)
        print("...............")
        print()
# Координаты от пользователя
def ask():
    while True:
    cords = input("Your turn").split()

    if len(cords) !=2:
        print("Enter second coordinates!")
        continue

    x, y = cords

    if not(x.isdigit()) or not(y.isdigit()):
        print("Enter numbers!")
        continue

    x, y = int(x), int(y)

    if 0 > x or x > 2 or 0 > y or y > 2:
        print("Coordinates out of range!")
        continue
    return x, y
# Проверка выйграшных комбинаций
def chek_win():
    win_cord = (((0, 0), (0, 1), (0, 2)), ((1, 0), (1, 1), (1, 2)), ((2, 0), (2, 1), (2, 2)),
                ((0, 2), (1, 1), (2, 0)), ((0, 0), (1, 1), (2, 2)), ((0, 0), (1, 0), (2, 0)),
                ((0, 1), (1, 1), (2, 1)), ((0, 2), (1, 2), (2, 2)))
    for cord in win_cord:
        symbols = []
        for c in cord:
            symbols.append(field[c[0]][c[1]])
        if symbols == ["X", "X", "X"]:
            print("Won X!")
            return True
        if symbols == ["0", "0", "0"]:
            print(Won 0!)
            return True
    return False
# Игровой цикл
greet()
field = [[" "] * 3 for i in range(3)]
count = 0
wile True:
    count += 1
    show()
    if count %2 == 1:
        print("A cross walks!")
    else:
        print("A zero is moving!")

    x, y = ask()

    if count %2 == 1:
        field[x] [y] = "X"
    else:
        field[x] [y] = "0" 

    if check_win():
        break

    if count == 9:
        print("Draw!")
        break
    
    
        
        


    
