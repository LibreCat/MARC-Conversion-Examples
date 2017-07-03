This fix reads the first two characters of field 700 and copies the value into the 'mat_desig' variable.

    marc_map(007/0-1,mat_desig)

Then makes a lookup in the 'field_700.csv' file for this value, hopefully getting the material designation string. On default value of 'mat_desig' becomes 'Unknown'.

    lookup('mat_desig', 'field_700.csv', default:'Unknown')
