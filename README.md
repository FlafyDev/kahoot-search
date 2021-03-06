# About
kahoot-search is an API for searching kahoot.
![NPM](https://nodei.co/npm/kahoot-search.png)

# Basic Example
```js
const Searcher = require("kahoot-search");
const search = new Searcher("node js");
search.search().then(results=>{
  //do stuff
});
```

## Documentation / How to use
### `new Searcher(query, config)` - Base class.
*query (string)* - The search term.
*config (object)* - Config settings.
#### Config Variables
`cursor` - This number is basically like the "load more" button on kahoot.
`limit` - A number that specifies how many items to be in the search. (1-100). It is recommended to use small numbers, like 25. Kahoot has issues with larger numbers sometimes.
`order` - A string to sort by "relevance", "quality", or "played"
`usage` - A list of who the quiz was made by ("teacher","student","businuess","social")
`type` - A list of the type of quiz ("quiz","poll","jumble","survey")
`language` - A list of language codes (en, es, fr, ...)
`questionLength` - A number that specifies how man questions the results must have. Requires includeKahoot to be true.
`author` - A string that specifies the user who made the quiz. Results will only include the ones made by the author.
`includeKahoot` - A boolean that specifies whether the results should include the kahoot data. Default is true
`includeCard` - A boolean that specifies whether the results should include the card data which include images, base description and tags
`searchStrictly` -  A boolean that only returns the results where the names exactly match the query.
`grades` - A list of numbers to filter by grades. ex: `[2,3,4,12]`
`topics` - A list of numbers pertaining to specific topics. See below.

### `searcher.search(function)`
`function` - the custom filter function. Optional.
Returns `Promise`
- An Array of kahoots
- Has property `totalHits` for total number of items that match the query.

### Topics
1. Elementary Math
2. Algebra
3. Geometry
4. Trigonometry
5. Calculus
6. Applied Math and Stats
7. Biology
8. Chemistry
9. Physics
10. Earth Sciences
11. Spelling and Vocab
12. Grammar
13. Literature and Drama
14. Spanish
15. French
16. Latin
17. German
18. Other (Chinese & Japanese)
19. Economics
20. World History
21. US History
22. Civics
23. General Trivia
24. Music
25. Sports
26. Movies
27. Computers

## Examples
See `tests/`.
