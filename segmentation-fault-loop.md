### P: Segmentation fault inside a for loop when accessing struct variables (PortAudio callback function)

- Project: [Ava](https://github.com/funktional-stdo/ava)
- File: [PortAudioCallbacks.cpp](https://github.com/funktional-stdo/ava/blob/main/src/PortAudioCallbacks.cpp)

#### Description:

I wanted to access the elements of an array inside a struct pointer in a loop, as well as some float and integer variables inside the same struct inside the same loop. It was obvious that there shouldn't be any problems accessing array elements inside the loop given that only allocated parts of memory are trying to be accessed. However, I still was getting segmentation fault errors.

#### Solution that worked:

I created **static** pointer objects before the for loop, and copied the contents of the pointers and variables inside the struct. Then I used the new pointers inside the loop. Also, not that much memory get lost because pointers are being used; the values inside just get re-written.

#### Failed solution:

I tried to copy the array inside a non-pointer array, it prevented core dumped errors in some cases but it still happened a lot + even if it worked it'd be not clean because I only wanted to use the struct that I was passing to the function.

#### Cause of the error:

I don't know yet.
