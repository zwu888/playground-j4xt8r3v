```C++ runnable
#include <iostream>

struct mybase
{
  int x;
  
  template <int RANGE>
  virtual void print()
  {
    std::cout << RANGE + x + 1 << std::endl;
  }
};

struct myderived : public mybase
{
  template <int RANGE> 
  void print()
  {
    std::cout << RANGE + x + 2 << std::endl;
  }
};

int main(int argc, char** argv)
{
  mybase* b = new myderived;

  b->x = 1;

  b->print<5>();

  return 0;
}
