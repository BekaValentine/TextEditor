# TextEditor

A new terminal-based text editor with scripting and stuff.

## Ideas

- A functional, possibly post-fix-y or composition-oriented scripting language

- Live script previewing

- Navigation commands include things like going to previous locations

- ~Good non-moded key combos for navigation, selection, deletion, etc. in a nano-like way~ Everything except local navigation is through the command interface

- Commands are typed. Some need to operate at a location, some operate on selections

- Fundamental non-deterministism in certain aspects (e.g. selections, locations, etc.) -- tho possibly done using type formers instead of actually being non-deterministic?

## Commands

- Setting the name
- Saving
- Changing display info?
- Navigation
- Selection
- Insertion
- Deletion
- Regex Replacement?
- Search
- Cut, Copy, Paste
- History

## Example Code

### Function Application

```
  f x
= x | f
```

### Lambdas

```
  1 + 2
= 1 > {_ + 2}
= {_ + _} 1 2
= {_0 + _1} 1 2
= {_1 + _0} 2 1
= (\x y -> x + y) 1 2
```

### Bigger Examples

Given

```
-- Selection ~= [String] but not precisely
select : Nat -> Direction -> Selection
forward : Direction
next : Nat -> Unit -> Selection
to_length : Selection -> Int
i_to_s : Int -> String
replace : (String -> String) -> Selection -> Action
```
Code:

`select 5 forward` selects the 5 characters from the cursor forward

`next 3 words` selects the next three words, each as a separate string

`next 3 words | replace_with (_ | to_length | i_to_s)` selects the next three words, each as a separate string, and replaces them with their lengths
