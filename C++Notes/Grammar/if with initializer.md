# if statement with initializer

```C++
int foo(int arg) {
    return arg;
}

int main() {
    if (auto x = foo(42); x > 30){
        // do something
    }else{
        // fo something
    }
}
```
