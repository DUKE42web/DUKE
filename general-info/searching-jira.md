# Searching JIRA



<details>

<summary>Jira Advanced Search</summary>



## Advanced searching

**On this page**

* [Advanced searching](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-QueryAdvancedsearching)
* [Understanding advanced searching](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-Understandingadvancedsearching)
* [Constructing JQL queries](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-ConstructingJQLqueries)
* [Precedence in JQL queries](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-parenthesesPrecedenceinJQLqueries)
* [Restricted words and characters](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-restrictionsRestrictedwordsandcharacters)
* [Performing text searches](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-textPerformingtextsearches)
* [Reference](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-referenceReference)
* [Running a saved search](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-Runningasavedsearch)
* [Next steps](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-Nextsteps)

**In this section**

* [Advanced searching - fields reference](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-fields-reference-981156848.html)
* [Advanced searching - development fields reference](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-development-fields-reference-981156849.html)
* [Advanced searching - keywords reference](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-keywords-reference-981156850.html)
* [Advanced searching - operators reference](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-operators-reference-981156851.html)
* [Advanced searching - functions reference](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-functions-reference-981156852.html)

**Related content**

* [Basic searching](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Basic+searching)
* [Searching for issues](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Searching+for+issues)
* [Working with search results](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Working+with+search+results)
* [Advanced searching - keywords reference](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Advanced+searching+-+keywords+reference)
* [Advanced searching - fields reference](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Advanced+searching+-+fields+reference)
* [Search syntax for text fields](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Search+syntax+for+text+fields)
* [Advanced searching - operators reference](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Advanced+searching+-+operators+reference)
* [Saving your search as a filter](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Saving+your+search+as+a+filter)
* [Customize the team board](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Customize+the+team+board)
* [Advanced searching - functions reference](https://confluence.atlassian.com/display/JIRASOFTWARESERVER085/Advanced+searching+-+functions+reference)

**Still need help?**

The Atlassian Community is here for you.

[Ask the community](https://community.atlassian.com/t5/custom/page/page-id/create-post-step-1?add-tags=Jira+Software)

The advanced search allows you to build structured queries using the Jira Query Language (JQL) to search for issues. You can specify criteria that cannot be defined in the quick or basic searches (e.g. `ORDER BY` clause).&#x20;

* If you don't have complex search criteria, you may want to use [quick search](https://confluence.atlassian.com/jirasoftwareserver085/quick-searching-981156830.html) instead.
* If you are not comfortable with the Jira Query Language (JQL), you may want to use [basic search](https://confluence.atlassian.com/jirasoftwareserver085/basic-searching-981156808.html) instead.

Note, JQL is not a database query language, even though it uses SQL-like syntax.&#x20;

_Screenshot: Advanced search_

![](https://confluence.atlassian.com/jirasoftwareserver085/files/981156836/981156837/1/1575972955279/advanced\_search2.png)

### Advanced searching <a href="#advancedsearching-queryadvancedsearching" id="advancedsearching-queryadvancedsearching"></a>

1. Navigate to **Issues** (in header) > **Search for issues**.\

   * If there are existing search criteria, click the **New filter** button to reset the search criteria.
   *   If the basic search is shown instead of the advanced search, click **Advanced** (next to the **Search** button).

       [Why can't I switch between basic and advanced search?](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#)

       *
         *
       *
       *
       *
       *
2.  Enter your JQL query. As you type, Jira will offer a list of "auto-complete" suggestions based on the context of your query. Note, auto-complete suggestions only include the first 15 matches, displayed alphabetically, so you may need to enter more text if you can't find a match.

    [Why aren't the auto-complete suggestions being shown?](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#)

    *
    *
    *
3. Press Enter or click **Search** to run your query. Your search results will display in the issue navigator.

### Understanding advanced searching <a href="#advancedsearching-understandingadvancedsearching" id="advancedsearching-understandingadvancedsearching"></a>

Read the following topics to learn how to get the most out of advanced searching:

[Constructing JQL queries](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-ConstructingJQLqueries) | [Precedence in JQL queries](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-parenthesesPrecedenceinJQLqueries) | [Restricted words and characters](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-restrictionsRestrictedwordsandcharacters) | [Performing text searches](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-textPerformingtextsearches)

#### Constructing JQL queries <a href="#advancedsearching-constructingjqlqueries" id="advancedsearching-constructingjqlqueries"></a>

A simple query in JQL (also known as a 'clause') consists of a _field_, followed by an _operator_, followed by one or more _values_ or _functions_. For example:

```
project = "TEST"
```

This query will find all issues in the "TEST" project. It uses the "project" _field_, the EQUALS _operator_, and the _value_ `"TEST"`.

A more complex query might look like this:

```
project = "TEST" AND assignee = currentuser()
```

This query will find all issues in the "TEST" project where the assignee is the currently logged in user. It uses the "project" _field_, the EQUALS _operator_, the _value_ `"TEST",`the "AND" keyword and the "currentuser()" function.

For more information on fields, operators, keywords and functions, see the [Reference section](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#Advancedsearching-reference) below.

#### Precedence in JQL queries <a href="#advancedsearching-parenthesesprecedenceinjqlqueries" id="advancedsearching-parenthesesprecedenceinjqlqueries"></a>

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

#### Restricted words and characters <a href="#advancedsearching-restrictionsrestrictedwordsandcharacters" id="advancedsearching-restrictionsrestrictedwordsandcharacters"></a>

**Reserved characters**

JQL has a list of reserved characters:

If you wish to use these characters in queries, you need to:

* surround them with quote-marks (you can use either single quote-marks (`'`) or double quote-marks (`"`));\
  **and,**
* if you are searching a **text field** and the character is on the list of [special characters in text searches](https://confluence.atlassian.com/jirasoftwareserver085/search-syntax-for-text-fields-981156853.html), precede them with two backslashes. This will let you run the query that contains a reserved character, but the character itself will be ignored in your query. For more info, see _Special characters_ in [Search syntax for text fields](https://confluence.atlassian.com/jirasoftwareserver085/search-syntax-for-text-fields-981156853.html).

\


For example:

* ```
  version = "[example]"
  ```
* ```
  summary ~ "\\[example\\]"
  ```

**Reserved words**

JQL also has a list of reserved words. These words need to be surrounded by quote-marks (single or double) if you wish to use them in queries.

[Show me...](https://confluence.atlassian.com/jirasoftwareserver085/advanced-searching-981156836.html#)

_Note for Jira administrators: this list is hard coded in the `JqlStringSupportImpl.java` file._

#### Performing text searches <a href="#advancedsearching-textperformingtextsearches" id="advancedsearching-textperformingtextsearches"></a>

You can use Lucene's text-searching features when performing searches on the following fields, using the CONTAINS operator:

Summary, Description, Environment, Comments, custom fields that use the "Free Text Searcher" (i.e. custom fields of the following built-in custom field types: Free Text Field, Text Field, Read-only Text Field).

For more information, see [Search syntax for text fields](https://confluence.atlassian.com/jirasoftwareserver085/search-syntax-for-text-fields-981156853.html).

### Reference <a href="#advancedsearching-referencereference" id="advancedsearching-referencereference"></a>

### Running a saved search <a href="#advancedsearching-runningasavedsearch" id="advancedsearching-runningasavedsearch"></a>

Saved searches (also known as [Saving your search as a filter](https://confluence.atlassian.com/jirasoftwareserver085/saving-your-search-as-a-filter-981156854.html)) are shown in the left panel, when using advanced search. If the left panel is not showing, hover your mouse over the left side of the screen to display it.

To run a filter, e.g. **My Open Issues**, simply click it. The JQL for the advanced search will be set, and the search results will be displayed.

![](https://confluence.atlassian.com/jirasoftwareserver085/files/981156836/981156846/1/1575972956125/saved\_search.png)

### Next steps <a href="#advancedsearching-nextsteps" id="advancedsearching-nextsteps"></a>

Read the following related topics:

* [Searching for issues](https://confluence.atlassian.com/jirasoftwareserver085/searching-for-issues-981156778.html)
* [Basic searching](https://confluence.atlassian.com/jirasoftwareserver085/basic-searching-981156808.html)
* [Search syntax for text fields](https://confluence.atlassian.com/jirasoftwareserver085/search-syntax-for-text-fields-981156853.html)
* [JQL: The most flexible way to search Jira (on the Atlassian blog)](https://blogs.atlassian.com/2013/01/jql-the-most-flexible-way-to-search-jira-14/)
* [Saving your search as a filter](https://confluence.atlassian.com/jirasoftwareserver085/saving-your-search-as-a-filter-981156854.html)
* [Working with search results](https://confluence.atlassian.com/jirasoftwareserver085/working-with-search-results-981156915.html)—find out how to use the issue navigator, export your search results, bulk modify issues, and share your search results.

</details>
