# How to do stuff in C++

### Classes and objects

```cpp
class naam_class{
    public:
    string mijn-naam;
};


int main()
{
    naam_class naam_obj;
    naam_obj.naam = mohit;
    return 0;
}
```
#### constructors

```cpp
class maak_profile{
    public:
    	string voornaam;
        string achternaam;
    	string birth_year;
    	maak_profile(string entry1, string entry2, string entry3){
            voornaam = entry1;
            achternaam = entry2;
            birth_year = entry3;
        }
};

int main(){
    maak_profile persoon1("Van", "Gogh", "ancient times!");
    maak_profile persoon2("Marie", "Curie", "1867");
    
    cout<< persoon1.voornaam << " "<<persoon1.achternaam<<" was born in "<<persoon1.birth_year << "\n";
    cout<< persoon2.voornaam << " "<<persoon2.achternaam<<" was born in "<<persoon2.birth_year << "\n";
    return 0;
}
```

We can also define a constructor outside the class to keep the code clean.

```cpp
class maak_profile{
    public:
    	string voornaam;
        string achternaam;
    	string birth_year;
    	maak_profile(string entry1, string entry2, string entry3);
};

maak_profile::maak_profile(string entry1, string entry2, string entry3){
    voornaam = entry1;
    achternaam = entry2;
    birth_year = entry3;
}

int main(){
    maak_profile persoon1("Van", "Gogh", "200BC :D");
    maak_profile persoon2("Marie", "Curie", "1867");
    
    cout<< persoon1.voornaam << " "<<persoon1.achternaam<<" was born in "<<persoon1.birth_year << "\n";
    cout<< persoon2.voornaam << " "<<persoon2.achternaam<<" was born in "<<persoon2.birth_year << "\n";
    return 0;
}
```



### `&`

**Reference**
Basically a mirror variable. Defined like:

```cpp
x = 25l;
int& age = x;
```

Change one of these and the other one will also change.

**Memory address**
Assign the memory address of `a` to `b`.
```cpp
b = &a
```
