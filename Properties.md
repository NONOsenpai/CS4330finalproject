## Java
* getter and setter
package greetings;
```java
import javax.inject.Inject;
import javax.enterprise.context.RequestScoped;
import javax.inject.Named;

@Named
@RequestScoped
public class Printer {

    @Inject @Informal Greeting greeting;
    
    private String name;
    private String salutation;

    public void createSalutation() {
        this.salutation = greeting.greet(name);
    }

    public String getSalutation() {
        return salutation;
    }

    public void setName(String name) {
       this.name = name;
    }

    public String getName() {
       return name;
    }
}
```
## C++
```C++
 class Employee
{
 int id;
//..
};
As setter of this class looks as follows:

 
class Employee
{
public:
 void set_id(int n) {id=n;}
};
A classic getter returns a value and takes no arguments; it's declared as a const member function to document the fact that it only observes an object's state but doesn't change it. For example:

 
class Employee
{
public:
 int get_id() const { return id;}
};

if (not_div_by_0)
{
    x1 = (a*a + b*b) / (x*x - 2*(y1*y1 + y2*y2) + y*y);
}
// other statements required before computing x2 and x3
if (not_div_by_0)
{
    x2 = (a*a - c*c) / (x*x - 2*(y1*y1 + y2*y2) + y*y);
}
// other statements required before computing x3
if (not_div_by_0)
{
    x3 = (2*a*a + 3*b*b) / (x*x - 2*(y1*y1 + y2*y2) + y*y);
}
```
