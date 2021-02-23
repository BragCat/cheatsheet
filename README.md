# `cheatsheet`
A command line tool to manage your cheatsheet items.

## Install

## Useful Commands
### Add an item
Adding an item into `cheatsheet` is very simple:

```cs add <name> "<content>"```

The `<name>` and `<content>` support Unicode characters, so you can use almost whatever characters you like in them, except blank characters in `<name>`, since `cheatsheet` regards the second blank character as the sparator of `<name>` and `<content>`. 

You should always use colons `""` to wrap the `<content>`, to tell `cheatsheet` that they should be treated as a whole.

### Search items
cheatsheet supports several ways to search for items.

Search by name like this: 

```cs list --name <keyword>...```

It will return all the items that `name` contains all the `<keyword>`.

Search by content like this:

```cs list --content <keyword>...```

It will return all the items that `content` contains all the `<keyword>`. When search keywords in `content`, keywords seperated by blank characters will be treated as seperated, so if you want `cheatsheet` to search a keyword that contains blank characters, use `""` to wrap them.

You can also combine them together like this:

```cs list --name <keyword>... --content <keyword>...```

If you don't care about whether name or content the keyword appears, but want to return items that contain the keywords in name or content, you can just use `--`:

```cs list -- <keyword>...```

### Delete items
You may delete an item by its name:

```cs delete <name>```

It will list the item to be deleted in a interactive way, and ask you to confirm.

If there are several items that have the same name, then it will list them all labeled with numbers, and ask you to select the ones you want to delete by entering the numbers.


## Examples
### Add an item
```cs add cheatsheet-add "cs add <title> "<content>""```

```cs add 滕王阁序名句 "落霞与孤鹜齐飞， 秋水共长天一色。"```

### Search items
```cs list --name cheatsheet```

```cs list --content 秋水 落霞```

### Delete items
```cs delete cheatsheet```

```cs delete 滕王阁序名句```

## How `cheatsheet` works
