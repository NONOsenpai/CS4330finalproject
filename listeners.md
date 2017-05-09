## JAVA
* example
public class MultiListener ... implements ActionListener {
    ...
    //where initialization occurs:
        button1.addActionListener(this);
        button2.addActionListener(this);

        button2.addActionListener(new Eavesdropper(bottomTextArea));
    }

    public void actionPerformed(ActionEvent e) {
        topTextArea.append(e.getActionCommand() + newline);
    }
}

class Eavesdropper implements ActionListener {
    ...
    public void actionPerformed(ActionEvent e) {
        myTextArea.append(e.getActionCommand() + newline);
    }
}
public class Beeper ... implements ActionListener {
    ...
    //where initialization occurs:
        button.addActionListener(this);
    ...
    public void actionPerformed(ActionEvent e) {
        ...//Make a beep sound...
    }
}
## C++
* #include <functional>
#include <list>


template <typename ... Args> struct event:public std::shared_ptr<std::list<std::function<void(Args...)>>>{

  using handler = std::function<void(Args...)>;
  using listener_list = std::list<handler>;

  struct listener{
    std::weak_ptr<listener_list> the_event;
    typename listener_list::iterator it;

    listener(){ }

    listener(event & s,handler f){
      observe(s,f);
    }

    listener(listener &&other){
      the_event = other.the_event;
      it = other.it;
      other.the_event.reset();
    }

    listener(const listener &other) = delete;

    listener & operator=(const listener &other) = delete;

    listener & operator=(listener &&other){
      reset();
      the_event = other.the_event;
      it = other.it;
      other.the_event.reset();
      return *this;
    }
    #include <iostream>

using click_event = event<float,float>;

struct gui_element{
  click_event click;
  void mouse_down(float x,float y){ click.notify(x, y); }
};

int main(int argc, char **argv) {
  gui_element A,B;
  click_event::listener listener_1,listener_2;

  listener_1.observe(A.click,[](float x,float y){ std::cout << "l1 : A was clicked at " << x << ", " << y << std::endl; });
  listener_2.observe(B.click,[](float x,float y){ std::cout << "l2 : B was clicked at " << x << ", " << y << std::endl; });

  {
  auto temporary_listener = A.click.connect([](float x,float y){ std::cout << "tmp: A was clicked at " << x << ", " << y << std::endl; });
  // A has two listeners, B has one listeners
  A.mouse_down(1, 0);
  B.mouse_down(0, 1);
  }

  listener_2 = std::move(listener_1);

  // A has one listener, B has no listeners
  A.mouse_down(2, 0);
  B.mouse_down(0, 2);
}
