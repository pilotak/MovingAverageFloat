# Moving average filter for float numbers
[![Build Status](https://travis-ci.org/pilotak/MovingAverageFloat.svg?branch=master)](https://travis-ci.org/pilotak/MovingAverageFloat)

# Mbed example
```cpp
#include "mbed.h"
#include "MovingAverageFloat.h"

// Buffer will be 16 samples long, it will take 16 * sizeof(float) = 64 bytes of RAM
MovingAverageFloat <16> filter;

int main() {
    printf("result: %u\n", filter.add(1.5)); // insert new number and get result
    printf("result: %u\n", filter.add(2.5)); // insert new number and get result
    printf("result: %u\n", filter.add(2.4)); // insert new number and get result
    printf("result: %u\n", filter.get()); // get last result, without adding a newone

    return 0;
}
```
# Arduino example
```cpp
#include "MovingAverageFloat.h"

// Buffer will be 16 samples long, it will take 16 * sizeof(float) = 64 bytes of RAM
MovingAverageFloat <16> filter;

void setup(){
    Serial.begin(9600);
    Serial.print("result: ");
    Serial.println(filter.add(1.5)); // insert new number and get result
    Serial.print("result: ");
    Serial.println(filter.add(2.5)); // insert new number and get result
    Serial.print("result: ");
    Serial.println(filter.add(2.4)); // insert new number and get result
    Serial.print("result: ");
    Serial.println(filter.get()); // get last result, without adding a newone
}

void loop(){

}
```

## Output
> result: 1.50
> 
> result: 1.56
> 
> result: 1.62
> 
> result: 1.62
