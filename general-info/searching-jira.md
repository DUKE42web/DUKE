# Searching JIRA

## Advanced searching | Jira Software Data Center and Server 8.5 | Atlassian Documentation

> ### Excerpt
>
> The advanced search allows you to build structured queries using the Jira Query Language (JQL) to search for issues. You can specify criteria that cannot be defined in the quick or basic searches (e.g. ORDER BY clause).

***

The advanced search allows you to build structured queries using the Jira Query Language (JQL) to search for issues. You can specify criteria that cannot be defined in the quick or basic searches (e.g. `ORDER BY` clause).&#x20;

Read the following topics to learn how to get the most out of advanced searching:

#### Constructing JQL queries

A simple query in JQL (also known as a 'clause') consists of a _field_, followed by an _operator_, followed by one or more _values_ or _functions_. For example:

This query will find all issues in the "TEST" project. It uses the "project" _field_, the EQUALS _operator_, and the _value_ `"TEST"`.

A more complex query might look like this:

```
project = "TEST" AND assignee = currentuser()
```

This query will find all issues in the "TEST" project where the assignee is the currently logged in user. It uses the "project" _field_, the EQUALS _operator_, the _value_ `"TEST",`the "AND" keyword and the "currentuser()" function.

For more information on fields, operators, keywords and functions, see the [Reference section](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-reference) below.

#### Precedence in JQL queries

Precedence in JQL queries depends on keywords that you use to connect your clauses (a clause being e.g. `project = “Teams in Space”`). The easiest way to look at this is to treat the _AND_ keyword as the one grouping clauses, and _OR_ as the one separating them. The _AND_ keyword takes precedence over other keywords, because it groups clauses together, essentially turning them into one combined clause.

**Example 1**

```
status=resolved AND project=“Teams in Space” OR assignee=captainjoe
```

This query will return all _resolved_ issues from the “Teams in Space” project (clauses grouped by _AND_), and also all existing issues assigned to _captainjoe_. The clause after the _OR_ keyword is treated as separate.

**Example 2**

```
status=resolved OR project="Teams in Space" AND assignee=captainjoe
```

This query, on the other hand, will return _captainjoe’s_ issues from the “Teams in Space” project (clauses grouped by _AND_), and also all existing _resolved_ issues (a clause separated by _OR_).

**Example 3**

```
status=resolved OR projects="Teams in Space" OR assigne=captainjoe
```

When you only use the _OR_ keyword, all clauses will be treated as separate, and equal in terms of precedence.

**Setting the precedence**

You can set precedence in your JQL queries by using parentheses. Parentheses will group certain clauses together and enforce precedence.

**Example 1**

As you can see below, parentheses can turn our example JQL query around. This query would return _resolved_ issues that either belong to the “Teams in Space” project, or are assigned to _captainjoe_.

```
status=resolved AND (project="Teams in Space" OR assignee=captainjoe)
```

**Example 2**

If you used parentheses like in the following example, they wouldn’t have any effect, because the clauses enclosed in parentheses were already connected by _AND_. This query would return the same results with or without the parentheses.

```
(status=resolved AND project="Teams in Space") OR assignee=captainjoe
```

#### Restricted words and characters

**Reserved characters**

JQL has a list of reserved characters:

`**space (" ")**`

`**+**`

`**.**`

`**,**`

`**;**`

`**?**`

`**|**`

`*****`

`**/**`

`**%**`

`**^**`

`**$**`

`**#**`

`**@**`

`**[**`

`**]**`

If you wish to use these characters in queries, you need to:

* surround them with quote-marks (you can use either single quote-marks (`'`) or double quote-marks (`"`));\
  **and,**
* if you are searching a **text field** and the character is on the list of [special characters in text searches](https://confluence.atlassian.com/jirasoftwareserver085/search-syntax-for-text-fields-981156853.html), precede them with two backslashes. This will let you run the query that contains a reserved character, but the character itself will be ignored in your query. For more info, see _Special characters_ in [Search syntax for text fields](https://confluence.atlassian.com/jirasoftwareserver085/search-syntax-for-text-fields-981156853.html).

For example:

* version = "\[example]"
* summary \~ "\\\\\[example\\\\]"

**Reserved words**

JQL also has a list of reserved words. These words need to be surrounded by quote-marks (single or double) if you wish to use them in queries.

[Show me...](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#)

"abort", "access", "add", "after", "alias", "all", "alter", "and", "any", "as", "asc", "audit", "avg", "before", "begin", "between", "boolean", "break", "by", "byte", "catch", "cf", "char", "character", "check", "checkpoint", "collate", "collation", "column", "commit", "connect", "continue", "count", "create", "current", "date", "decimal", "declare", "decrement", "default", "defaults", "define", "delete", "delimiter", "desc", "difference", "distinct", "divide", "do", "double", "drop", "else", "empty", "encoding", "end", "equals", "escape", "exclusive", "exec", "execute", "exists", "explain", "false", "fetch", "file", "field", "first", "float", "for", "from", "function", "go", "goto", "grant", "greater", "group", "having", "identified", "if", "immediate", "in", "increment", "index", "initial", "inner", "inout", "input", "insert", "int", "integer", "intersect", "intersection", "into", "is", "isempty", "isnull", "join", "last", "left", "less", "like", "limit", "lock", "long", "max", "min", "minus", "mode", "modify", "modulo", "more", "multiply", "next", "noaudit", "not", "notin", "nowait", "null", "number", "object", "of", "on", "option", "or", "order", "outer", "output", "power", "previous", "prior", "privileges", "public", "raise", "raw", "remainder", "rename", "resource", "return", "returns", "revoke", "right", "row", "rowid", "rownum", "rows", "select", "session", "set", "share", "size", "sqrt", "start", "strict", "string", "subtract", "sum", "synonym", "table", "then", "to", "trans", "transaction", "trigger", "true", "uid", "union", "unique", "update", "user", "validate", "values", "view", "when", "whenever", "where", "while", "with"

_Note for Jira administrators: this list is hard coded in the `JqlStringSupportImpl.java` file._

#### Performing text searches

You can use Lucene's text-searching features when performing searches on the following fields, using the CONTAINS operator:

Summary, Description, Environment, Comments, custom fields that use the "Free Text Searcher" (i.e. custom fields of the following built-in custom field types: Free Text Field, Text Field, Read-only Text Field).

For more information, see [Search syntax for text fields](https://confluence.atlassian.com/jirasoftwareserver085/search-syntax-for-text-fields-981156853.html).

Saved searches (also known as [Saving your search as a filter](https://confluence.atlassian.com/jirasoftwareserver085/saving-your-search-as-a-filter-981156854.html)) are shown in the left panel, when using advanced search. If the left panel is not showing, hover your mouse over the left side of the screen to display it.

To run a filter, e.g. **My Open Issues**, simply click it. The JQL for the advanced search will be set, and the search results will be displayed.
