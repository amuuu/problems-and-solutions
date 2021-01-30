### P: Empty std::list object even after appending new members
- Project: [Ava](https://github.com/funktional-stdo/ava)

#### Description:

I was trying to append new items to a std::list object in one method, and accessing the newly appended member in another method. But the list was empty on the other method! It didn't give any seg. faults because it was not a pointer. I thought that, logically, there shouldn't have been any problems since both methods are inside the same class and are trying to access the *same* object. But apparently, that was not the case.

#### Solution that worked:

Use std::list* instead of std::list inside the class, so that both method are guaranteed to access the same object in the same place inside the memory all the time.
