# Hackerrank3_446

##Rectangle Area
```
class Rectangle{
    public:
    int height,width;
    
    void display(){
        cout<<width<<" "<<height<<endl;
    }
};
class RectangleArea : public Rectangle{
    public:
    void read_input()
    {
        cin>>width>>height;
    }
    void display(){
        cout<<width*height;
    }
};
```

##Virtual Functions
```
class Person {
public:
    string name;
    int age;
    virtual void getdata() {
        cin >> this->name >> this->age;
    }
    virtual void putdata() {
        cout << this->name << " " << this->age << endl;
    }
};

class Professor : public Person {
public:
    Professor() {
        this->cur_id = ++id;
    }
    int publications;
    static int id;
    int cur_id;
    void getdata() {
        cin >> this->name >> this->age >> this->publications;
    }
    void putdata() {
        cout << this->name << " "
            << this->age << " "
            << this->publications << " "
            << this->cur_id << endl;
    }
};
int Professor::id = 0;

class Student : public Person {
#define NUM_OF_MARKS 6
public:
    Student() {
        this->cur_id = ++id;
    }
    int marks[NUM_OF_MARKS];
    static int id;
    int cur_id;
    void getdata() {
        cin >> this->name >> this->age;
        for (int i=0; i<NUM_OF_MARKS; i++) {
            cin >> marks[i];
        }
    }
    void putdata() {
        int marksSum = 0;
        for (int i=0; i<NUM_OF_MARKS; i++) {
            marksSum += marks[i];
        }
        cout << this->name << " "
            << this->age << " "
            << marksSum << " "
            << this->cur_id << endl;
    }
};
int Student::id = 0;
```

##Overloading Ostream Operator
```
ostream& operator<<(ostream& Output, Person& p) 
{
  Output << "first_name=" << p.get_first_name() << ","
         << "last_name=" << p.get_last_name();
  return Output;
}
```

##Overload Operators
```
Complex operator+(const Complex X, const Complex Y) 
{
    Complex Z;
    Z.a = X.a + Y.a;
    Z.b = X.b + Y.b;

    return Z;
}
ostream& operator<<(ostream& os, const Complex C) 
{
    return os << C.a << "+" << "i" << C.b;
}
```

##Operator Overloading
```
class Matrix 
{
    public:
        vector<vector<int>> a;

        Matrix() {}
        Matrix operator+(const Matrix &o) 
        {
            Matrix sum(*this);
            for (size_t i = 0; i < sum.a.size(); i++) 
            {
                for (size_t j = 0; j < sum.a[i].size(); j++) 
                {
                    sum.a[i][j] += o.a[i][j];
                }
            }
            return sum;
        }
};
```
