#вариант 31. Целые восьмеричные числа, начинающиеся с нечетных цифр и не превышающие 5 цифр. Четные цифры выводить словами.
import re  # Импортируем модуль re для работы с регулярными выражениями

slovar = {
    '0': 'ноль',
    '2': 'два',
    '4': 'четыре',
    '6': 'шесть'
}

def replace(num):  
    result = []  
    for d in num:  
        if d in slovar:  
            result.append(slovar[d])  
        else:  
            result.append(d)  
    return ''.join(result)  

def read_file(file): 
    with open(file, 'r') as f:  
        data = f.read()  
        pattern = r'\b[0-7]+\b'

        numbers = re.findall(pattern, data)

        for num in numbers:  
            if len(num) <= 5 and num[0] in '1357':
                modified_num = replace(num) 
                print(modified_num) 

read_file('numbers.txt') 

