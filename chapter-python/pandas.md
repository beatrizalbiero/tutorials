## What it is <a id="what"></a>

Pandas is a python module that is used to manipulate datasets. It could be considered a better version of numpy, since some methods used in pandas are similar to the used in numpy, but better and easier.

## Basics Commands <a id="basics"></a>

**OBS** : You can get the csv in the repository path/example/datasets

Install Pandas with the pip command in terminal
```Shell
$ pip install pandas
```
Import the pandas module and define it as pd
```Python
import pandas as pd
```

Open a csv dataset and put it in the food_info variable

```Python
food_info = pd.read_csv("food_info.csv")
```
Shows the first three rows of the open dataset

```Python
print(food_info.head(3))
```

Gets the dimensions of the open dataset and put it in the dimensions variable

```Python
dimensions = food_info.shape
```

Puts the number of rows, that is in the first position of the list dimensions in the num_rows variable

```Python
num_rows = dimensions[0]
```

Puts the number of columns, that is in the second position of the list dimensions in the num_cols variable

```Python
num_cols = dimensions[1]
```

Gets the row 8620 of theopen dataset

```Python
food_info.loc[8620]
```

Shows the rows 3,4 and 5 of the open dataset

```Python
print(food_info[3:6])
```

Shows the rows 3,4,5 and 6

```Python
print(food_info.loc[3:6])
```

Shows the rows 2,5 and 10

```Python
print(food_info.loc[[2,5,10]])
```

Shows the rows 2,5 and 10 using a list

```Python
two_five_ten = [2,5,10]
print(food_info.loc[two_five_ten])
```

Shows all the registers of the open dataset, but only the column NDB_No

```Python
ndb_col = food_info["NDB_No"]
print(ndb_col)
```

Shows all the registers of the open dataset, but only the column Zinc_(mg) e Copper_(mg)

```Python
columns = ["Zinc_(mg)", "Copper_(mg)"]
zinc_copper = food_info[columns]
print(zinc_copper)
```

Converts all the rows of the column DATE to datetime

```Python
df['DATE'] = pd.to_datetime(df['DATE'])
```

Shows the dataset sorted increasingly

```Python
Sorted = df.sort_values(['UNRATE'])
print(Sorted)
```

Sorts the dataset through the column DATE decreasingly and shows it

```Python
Sorted = df.sort_values(['UNRATE'], ascending=False)
```

Shows the first row of the Sorted dataset

```Python
print(Sorted.head(1))
```
Shows the maximun value among the rows of the UNRATE columns

```Python
MaxValue = df['UNRATE'].max()
print(MaxValue)
```


## Examples <a id="examples"></a>

Example 1
Shows the columns that use grams (g) as measure

```Python
food_info = pd.read_csv("food_info.csv")
columns = food_info.columns #gets all the columns of the open dataset and and put it in the columns variable
columns_list = columns.tolist() #transforms columns in a list
final_list = [] #creates an empty list
for column in columns_list: #walks over the dataset and verifies the columns that has (g) in the end and puts in final_list
    tamanho = len(column)#gets the number of columns
    if (column[tamanho-3:]=="(g)"):#tests if last three letters of the column are (g)
        final_list.append(column)#puts the columns in a list
show_final_list = food_info[final_list]#forms a new dataset, only with the columns selected
print(show_final_list)
```

Example 2
Shows only the rows in which the rate was caught in 2000  
```Python
import pandas as pd
df = pandas.read_csv("unrate.csv")

dimensions = df.shape
num_rows = dimensions[0]#gets the number of rows of the dataset

new = []
for i in range (num_rows):
    if (df['DATE'][i][0:4]=="2000"):
        new.append(True)
    else:
        new.append(False)
print(df[new][:])
```

Example 3
The result is the same of the example 2, but using another strategy.

```Python
import pandas as pd
df = pd.read_csv("unrate.csv")

def check2000(Date):
    if (Date[0:4]=="2000"):
        return True
    else:
        return False
lista2000 = df['DATE'].apply(check2000)
display(df[lista2000])
```

Example 4

Modifies the rows with values less than 5 to the values + 0.23. This example uses 2 functions.

```Python
import pandas as pd
df = pd.read_csv("unrate.csv")

def checklessoreuqualtofive(unrate):#identifies the rows with value less or equal to 5
    if unrate <= 5 :
        return True
    else:
        return False

def modify(unrate):#modifies the value, adding 0.23
    return unrate + 0.23

s = selected["UNRATE"].apply(checklessoreuqualtofive)#walks over the dataset and send each of the rows to checklessoreuqualtofive

modified = df[selected]['UNRATE'].apply(modify)#walks over the dataset(only the rows with value less than 5) and send each of the rows to modifica

df.loc[selected,'UNRATE'] = modified #modifies the rows of the dataset(only the rows with value less than 5)

display(df)
```

Example 5
Modifies the rows with values less than 5 to the values + 0.23. This example is the same of the example 4 and uses 1 function.

```Python
import pandas as pd
df = pd.read_csv("unrate.csv")
def checklessoreuqualtofive(Unrate): #identifies the rows with value less or equal to 5 and modifies it to the value + 0.23
    if (Unrate<=5):
        return Unrate+0.23
    else:
        return Unrate

df['UNRATE'] = df['UNRATE'].apply(checklessoreuqualtofive)#walks over the dataset and send each of the rows to checklessoreuqualtofive

print(df)
```

Example 6

Modifies the rows with values less than 5 to the values + 0.23. This example is the same of the example 4 and 5 and uses only 3 lines.

```Python
import pandas as pd
df = pd.read_csv("unrate.csv")
df.loc[df.UNRATE<=5, 'UNRATE'] = df.UNRATE + 0.23 #walks over the dataset, identifies the UNRATES with value less or equal to 5 and adds 0.23 to them.
display(df)
```
