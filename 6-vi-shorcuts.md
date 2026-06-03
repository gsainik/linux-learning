# VI Editor Shortcuts

## Modes in VI Editor

### Normal Mode (Default)
Used for:
- Navigation
- Copying
- Deleting
- Searching
- Executing commands

---

### Insert Mode

Used for:
- Text editing
- Adding content

Press ```i``` to Enter Insert Mode

Press ```Esc``` to Exit Insert Mode



### Command Mode

Used for:
- Saving files
- Quitting editor
- Search and replace

Enter Command Mode: press ```:``` (while in Normal Mode)

---

# Basic Navigation

1. `h` – Move left.

2. `l` – Move right.

3. `j` – Move down.

4. `k` – Move up.

5. `0` – Move to the beginning of the line.

6. `^` – Move to the first non-blank character of the line.

7. `$` – Move to the end of the line.

8. `w` – Move to the next word.

9. `b` – Move to the previous word.

10. `gg` – Move to the start of the file.

11. `G` – Move to the end of the file.

12. `:n` – Move to line number `n`.

Example:

```text
:25
```

Moves to line 25.

---

# Insert Mode Shortcuts

13. `i` – Insert before cursor.

14. `I` – Insert at the beginning of the line.

15. `a` – Append after cursor.

16. `A` – Append at the end of the line.

17. `o` – Open a new line below.

18. `O` – Open a new line above.

19. `Esc` – Exit Insert Mode.

---

# Editing Text

20. `x` – Delete a character.

21. `X` – Delete a character before cursor.

22. `dw` – Delete a word.

23. `dd` – Delete a line.

24. `d$` – Delete from cursor to end of line.

25. `d0` – Delete from cursor to beginning of line.

26. `D` – Delete from cursor to end of line.

27. `u` – Undo last action.

28. `Ctrl + r` – Redo an undone change.

29. `yy` – Copy (yank) a line.

30. `yw` – Copy (yank) a word.

31. `p` – Paste after the cursor.

32. `P` – Paste before the cursor.

---

# Search and Replace

33. `/pattern` – Search forward for a pattern.

Example:

```text
/error
```

---

34. `?pattern` – Search backward for a pattern.

Example:

```text
?error
```

---

35. `n` – Repeat last search forward.

36. `N` – Repeat last search backward.

37. `:%s/old/new/g` – Replace all occurrences of "old" with "new" in the file.

Example:

```text
:%s/error/success/g
```

---

38. `:s/old/new/g` – Replace all occurrences in the current line.

---

# Working with Files

39. `:e filename` – Open another file.

Example:

```text
:e notes.txt
```

---

40. `:w` – Save file.

---

41. `:wq` – Save and exit.

---

42. `:q!` – Quit without saving.

---

# Split Screen Operations

43. `:split filename` – Split screen horizontally and open another file.

Example:

```text
:split app.log
```

---

44. `:vsplit filename` – Split screen vertically.

Example:

```text
:vsplit app.log
```

---

45. `Ctrl + w + w` – Switch between split screens.

---

# Most Common Commands

1. `i` – Insert mode.

2. `Esc` – Exit insert mode.

3. `:w` – Save file.

4. `:q` – Quit.

5. `:wq` – Save and quit.

6. `:q!` – Quit without saving.

7. `dd` – Delete line.

8. `yy` – Copy line.

9. `p` – Paste.

10. `/text` – Search text.

11. `gg` – Go to first line.

12. `G` – Go to last line.