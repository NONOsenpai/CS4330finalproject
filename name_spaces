
## C++
* Namespaces provide a method for preventing name conflicts in large projects.
* Symbols declared inside a namespace block are placed in a named scope that prevents them from being mistaken for identically-named symbols in other scopes.
  Multiple namespace blocks with the same name are allowed. All declarations within those blocks are declared in the named scope.
* implement:
  You can specify the namespace in test.cc as well. To do this, you would do something like:

  #include "test.h"
  namespace test
  {
    ...
    names[a] = "yum yum"; 
    names[c] = "pum pum"; 
    ...
  }
  
 * used
  Defining a Namespace
    namespace namespace_name {
        // code declarations
      }
  To call the namespace-enabled version of either function or variable, prepend the namespace name as follows:
    name::code;  // code could be variable or function.
  Let us see how namespace scope the entities including variable and functions:
    #include <iostream>
      using namespace std;
      // first name space
      namespace first_space{
         void func(){
            cout << "Inside first_space" << endl;
         }
      }
      // second name space
      namespace second_space{
         void func(){
            cout << "Inside second_space" << endl;
         }
      }
      int main () {
          // Calls function from first name space.
         first_space::func();
         // Calls function from second name space.
         second_space::func(); 
      return 0;
      }
## JAVA
* Java doesn't use this term but there is similar concept which is used Java which is called packages.
* Packages are used to organize files or public types to avoid 
  type conflicts. 
* Package constructs can be mapped to a file system.
* implement:
  To declare a class that implements an interface, you include an implements clause in the class declaration. Your class can implement more than one interface, so the implements keyword is followed by a comma-separated list of the interfaces implemented by the class. By convention, the implements clause follows the extends clause, if there is one.
* Used:
  While creating a package, you should choose a name for the package and include a package statement along with that name at the top of every source file that contains the classes, interfaces, enumerations, and annotation types that you want to include in the package.
  The package statement should be the first line in the source file. There can be only one package statement in each source file, and it applies to all types in the file.
  If a package statement is not used then the class, interfaces, enumerations, and annotation types will be placed in the current default package.
  To compile the Java programs with package statements, you have to use -d option as shown below.
      javac -d Destination_folder file_name.java
  Then a folder with the given package name is created in the specified destination, and the compiled class files will be placed in that folder.
