# ceedling-cheat-sheet

## Running

Run all tests
```
ceedling test:all
```

Run all tests in __test_my_lib.c__
```
ceedling test:test_my_lib
```


## Asserting

### TEST_ASSERT
```
int my_var = 5;
TEST_ASSERT(my_var == 5);
```

## Ignoring Arguments

### Internal Pointers

Given the function:
```
uint32_t time_remaining( timer_t * timer )
{
...
}
```
We may not have access to the __timer__ pointer to check it, so ignore it:
```
time_remaining_ExpectAndReturn(NULL, 10); //function returns 10
time_remaining_IgnoreArg_timer();
```
