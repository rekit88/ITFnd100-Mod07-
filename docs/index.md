# Assignment07
**Dev:** *P.Timchenko*   
**Date:** *5/23/2021*

## “Pickling” is the process whereby a Python object hierarchy is converted into a byte stream, and “unpickling” is the inverse operation, whereby a byte stream (from a binary file or bytes-like object) is converted back into an object hierarchy.
## Description: A simple example of storing data in a binary file.

### Result of this script see Figure 1-2.
```
# ------------------------------------------------- #
# Title: Assignment07
# Description: A simple example of storing data in a binary file
# ChangeLog: P.Timchenko, Initial script. 
# Pavel Timchenko, 5/23/2021, Created Script
# ------------------------------------------------- #

import pickle
strFileName = 'AppData.dat'
lstCustomer = []
readCustomer = []

# Processing -------------------------------------- #
# Now we store the data with the pickle.dump method
def save_data_to_file(file_name, list_of_data):

    objFile = open(file_name, "ab")
    pickle.dump(list_of_data, objFile)
    objFile.close()


# And, we read the data back with the pickle.load method
def read_data_from_file(file_name):

    objFile = open(file_name, "rb")
    objFileData = pickle.load(objFile)  # load() only loads one row of data.
    objFile.close()

    return objFileData


intId = int(input("Enter an Id: "))
strName = str(input("Enter a Name: "))
lstCustomer = [intId, strName]
save_data_to_file(strFileName, lstCustomer)
readCustomer = read_data_from_file(strFileName)
print("\n", str(readCustomer), "\n")
```


![alt text](https://github.com/rekit88/ITFnd100-Mod07-/blob/main/docs/Pickling1.jpg)
Figure 1
![alt text](https://github.com/rekit88/ITFnd100-Mod07-/blob/main/docs/PickleFileCreated.jpg)
Figure 2
