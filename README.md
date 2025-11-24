# Freedictionaryapi
api for freedictionaryapi.com site for getting entries of word
# main
```cpp
#include "Freedictionaryapi.h"
#include <iostream>

int main() {
   Freedictionaryapi api;
    auto entries = api.get_entries("en","fragment").then([](json::value result) {
        std::cout << result<< std::endl;
    });
    entries.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```
