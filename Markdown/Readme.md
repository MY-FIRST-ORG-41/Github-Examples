## Markdown Example
- [Headings](#headings)
- [Unorderd lists](#unorderd-lists)
- [Orderd lists](#orderd-lists)
- [Text formating](#text-formating)
- [Code](#code)
- [Blockquote](#blockquote)
- [Tables](#tables)
- [Lists](#lists)
- [Links](#links)
- [Auto lists](#autolist)
- [Auto Links](#autolinks)
- Images


https://github.github.com/gfm/

https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

## Headings

#### Create something new

### Create something new

## Create something new

# Create something new

## Lists

> ## Unorderd lists

- Foo
- You
+ How
+ Now

> ## Orderd lists

1) First item
1) Second item
1. Third item
2. Fourth item

> ## Task list

- [ ] Task not completed
- [x] Task completed

## Text formating

_italics_
*italics*
__bold__
**bold**
-striketrhough-

## Code

> ### Inline Code
> We can print to the terminal using `Print("Hello World")` command in python .

> ### Multiline code
>> ### With Highlighting

```rb
def Hello World
  Print("Hello World")
end
```

>> ### Without Highlighting

```
def Hello World
  Print("Hello World")
end
```

## Blockquote

> This is a single-line blockquote.

> This is a multi-line blockquote.
It continues on the next line.
And even on a third line.

>> This is a double blockquote.

> ## How
 > And
> We

## Tables

> #### For left alignment
```
:---
``` 
> #### For center alignment
```
:---:
``` 
> #### For right alignment
```
---:
``` 

> ### Basic table

| Header 1 | Header 2 |
|---|---|
| Row 1 Col 1 | Row 1 Col 2 |
| Row 2 Col 1 | Row 2 Col 2 |

> ### Alignment table

| Left Aligned | Center Aligned | Right Aligned |
|:---|:---:|---:|
| Left Text | Centered Text | Right Text |
| Another Left | Another Center | Another Right |

> ### Table with Varying Column Widths

| Short | Long Column Header | Medium |
|---|---|---|
| Data | More Data in a long cell | Some Data |
| 1 | 2 | 3 |

## Links

[Github website](https://github.com)

[secret page](secret.md)

## AutoList

<details><summary>My TodoList</summary>

- [ ] List
- [ ] Heading
- [ ] Bold
- [ ] Italic

</details>

This is uses in issues for genrating autolist they are genrating an autolist for us. In the right side of subheadings of todoList we have a three dots when we hower on these dots they shows us genrate a new issue or
genrate a sub issue etc. when we click it they genrate an issue for us.

For example link is given below:

https://github.com/m71443537-a11y/Github-Examples/issues/8

## AutoLinks

GitHub's autolink feature allows for the automatic creation of clickable links within issues.

we genrate an autolink like this.

(link of repo in which you have an issue) (number of issue) 

link of repo is this(m71443537-a11y/Github-Examples)

number of an issue is this(#9)

m71443537-a11y/Github-Examples#9

Now they create an auto link for us.
