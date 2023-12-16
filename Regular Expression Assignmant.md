# ANS1
import re
text='Python Exercises, PHP exercises.'
Textn=re.sub('[ ,.]', ':', text)
Textn



# ANS2
import pandas as pd
import re
data={'SUMMARY': ['hello, world!', 'XXXXX test', '123four, five:; six...']}
df=pd.DataFrame(data)
df['SUMMARY']=df['SUMMARY'].apply(lambda x: re.sub(r'[^a-zA-Z\s]', '', x))
df



#ANS3
x = "Through its separation of Europe, Africa, and Asia from the Americas, the Atlantic Ocean has played a central role in the development of human society, globalization, and the histories of many nations."
def text(x):
    pattern = re.compile(r'\b\w{4,}\b')
    return pattern.findall(x)
output = text(x)
output



#ANS4
x = "Through its separation of Europe, Africa, and Asia from the Americas, the Atlantic Ocean has played a central role in the development of human society, globalization, and the histories of many nations."
def n(x):
    pattern = re.compile(r'\b\w{3,5}\b')
    return pattern.findall(x)
five_chr_word = n(x)
five_chr_word



#ANS5
def AA(c):
    pattern = re.compile(r'\(|\)')
    return [pattern.sub('', s) for s in c]
BB = AA(c)
BB



#ANS6
data = "example (.com)", "hr@fliprobo (.com)", "github (.com)", "Hello (Data Science World)", "Data (Scientist)"
def rem(data):
    pattern = re.compile(r'\(|\)')
    return [pattern.sub('', s) for s in data]
new=rem(data)
new



#ANS7
#Please help in this question



#ANS8
text = 'RegularExpression1IsAn2ImportantTopic3InPython'
def space(text):
    pattern = re.compile(r'(?<=\d)(?=\D)')
    return pattern.sub(' ', text)
nn=space(text)
nn



#ANS9
p="RegularExpression1IsAn2ImportantTopic3InPython"
def ins(p:str)->str:
    return re.sub(r'(?<=[a-z])(?=[A-Z0-9])', ' ', p)
o=ins(p)
o

#ANS10
#Please help in this question



#ANS11
#Please help in this question



#ANS12
#Please help in this question



#ANS13
def r(ip_address):
    oc = ip_address.split(".")
    oc = [str(int(o)) for o in oc]
    new_ip_address = ".".join(oc)
ip_address = "192.168.002.001"
new_ip_address = r(ip_address)
print(f"The new IP address is", new_ip_address)
The new IP address is None



#ANS14
#Please help in this question



#ANS15
string = "The quick brown fox jumps over the lazy dog."
def sear(string, pat):
    for pattern in pat:
        if re.search(pattern, string):
            print("The string '{string}' contains the pattern '{pattern}'.")
        else:
            print("The string '{string}' does not contain the pattern '{pattern}'.")
patterns = ["fox", "dog", "horse"]
sear(string, patterns)

#ANS16
import re
string = "The quick brown fox jumps over the lazy dog."
def searchx(string, pattern):
    match = re.search(pattern, string)
    if match:
        start = match.start()
        end = match.end()
        print("The pattern '{pattern}' was found in '{string}' from index {start} to {end}.")
    else:
        print("The pattern '{pattern}' was not found in '{string}'.")
pattern = "fox"
searchx(string, pattern)



#ANS17
text = 'Python exercises, PHP exercises, C# exercises'
pattern = 'exercises'
matches = re.findall(pattern, text)

if matches:
    print(f'The following substrings were found: {", ".join(matches)}')
else:
    print('No matches found.')



#ANS18
text = 'Through its separation of Europe, Africa, and Asia from the Americas, the Atlantic Ocean has played a central role in the development of human society, globalization, and the histories of many nations.'

matches = [(match.start(), match.end()) for match in re.finditer(pattern, text)]

pattern = 'the'

if matches:
    print(f'The pattern "{pattern}" was found {len(matches)} times at the following positions: {matches}')

else:
    print('The pattern "{pattern}" was not found in the text.')



#ANS19
from datetime import datetime    
def convert(date_str: str) -> str:
    date_obj = datetime.strptime(date_str, '%Y-%m-%d')
    return date_obj.strftime('%d-%m-%Y')
date_str = '2023-12-16'
print(f'The converted date is {convert(date_str)}')



#ANS20
import re
text = "01.12 0132.123 2.31875 145.8 3.01 27.25 0.25"
def find(text: str) -> list:
    pattern = re.compile(r'\d+\.\d{1,2}')
    return pattern.findall(text)
print('The input text is: {text}')
print('The decimal numbers with precision of 1 or 2 are: {find(text)}')



#ANS21
#Please help in this question



#ANS22
def extract(text: str) -> int:
    pattern = re.compile(r'\d+')
    numbers = [int(match) for match in pattern.findall(text)]
    return max(numbers)

text = 'My marks in each semester are: 947, 896, 926, 524, 734, 950, 642'

print(f'The largest number in the text is:', extract(text))



#ANS23
text = "RegularExpressionIsAnImportantTopicInPython"
def spaces(text: str) -> str:
    return re.sub(r"(?<!^)(?=[A-Z])", " ", text).strip()

print(f"updated text:", spaces(text))


#ANS24
import re

def find(text: str) -> str:
    pattern = r"[A-Z][a-z]+"
    return re.findall(pattern, text)

sample_text = "Regular expression is An Important topic In python"
print(f"The matched sequences: {find(sample_text)}")



#ANS25
sample = "Hello Hello world world"
def dup(text: str) -> str:
    return re.sub(r"\b(\w+)(?:\W+\1\b)+", r"\1", text, flags=re.IGNORECASE)
print(dup(sample))



ANS26
text = 'Through its separation of Europe, Africa, and Asia from the Americas, the Atlantic Ocean has played a central role in the development of23 human society, globalization, and the 12histories of many nations.'
def check_alphanumeric(text: str) -> bool:
    pattern = r"\w$"
    return bool(re.search(pattern, text))

print(f"The original text: {text}")
if check_alphanumeric(text):
    print("The text ends with an alphanumeric character.")
else:
    print("The text does not end with an alphanumeric character.")



#ANS27
samp = 'RT @kapil_kausik: #Doltiwal I mean #xyzabc is "hurt" by #Demonetization as the same has rendered USELESS <ed><U+00A0><U+00BD><ed><U+00B1><U+0089> "acquired funds" No wo'
def hashtags(text):
    regex = r'#\w+'
    return re.findall(regex, text)
hashtags = hashtags(samp)
print(f'The hashtags in the given text are: {hashtags}')



#ANS28
import re
t1 = "@Jags123456 Bharat band on 28??<ed><U+00A0><U+00BD><ed><U+00B8><U+0082>Those who  are protesting #demonetization  are all different party leaders"
def remove(text):
    regex = r'<U\+\w{4}>'
    return re.sub(regex, '', text)
t2 = remove(t1)
print(f'The cleaned text is: {t2}')



#ANS29
def extract(file1):
    with open(file1, 'r') as file:
        text = file.read()        
       
        pattern = re.compile(r'\b\d{2}-\d{2}-\d{4}\b')        
       
        dates = pattern.findall(text)
       
        return dates

file1 = 'file.txt'

extracted_dates = extract(file1)

print(extracted_dates)



#ANS30
import re
text2 = "The following example creates an ArrayList with a capacity of 50 elements. 4 elements are then added to the ArrayList and the ArrayList is trimmed accordingly."
def word(text):
    regex = re.compile(r'\b\w{2,4}\b')
    return regex.sub('', text)
finaltext = word(text2)
print(f'The cleaned text is: {finaltext}')
