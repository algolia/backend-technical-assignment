# Technical test

The goal of this test is to evaluate your ability to parse and process a large amount of data and to use the appropriate data structures to solve a challenge.

The goal is to extract the popular (most frequent) queries done during a specific time range from a given log dataset.

The provided [sample file](https://www.dropbox.com/s/duv704waqjp3tu1/hn_logs.tsv.gz?dl=0) is a TSV file listing all queries performed on [HN Search](https://hn.algolia.com) during a few days.
Each line contains a timestamp and a query separated by a tab.


## Instructions

Build a small application exposing the following endpoints through a REST API:

 * `GET /1/queries/count/<DATE_PREFIX>`: returns a JSON object specifying the number of distinct queries that have been done during a specific time range
 * `GET /1/queries/popular/<DATE_PREFIX>?size=<SIZE>`: returns a JSON object listing the top `<SIZE>` popular queries that have been done during a specific time range


### Examples

 * Distinct queries done in 2015: `GET /1/queries/count/2015`: `{"count": 573697}`
 * Distinct queries done in Aug: `GET /1/queries/count/2015-08`: `{"count": 573697}`
 * Distinct queries done on Aug 3rd: `GET /1/queries/count/2015-08-03`: `{"count": 198117}`
 * Distinct queries done on Aug 1st between 00:04:00 and 00:04:59: `GET /1/queries/count/2015-08-01 00:04`: `{"count": 617}`

 * Top 3 popular queries done in 2015: `GET /1/queries/popular/2015?size=3`:

```js
    {
      "queries": [
        {"query": "http%3A%2F%2Fwww.getsidekick.com%2Fblog%2Fbody-language-advice", "count": 6675},
        {"query": "http%3A%2F%2Fwebboard.yenta4.com%2Ftopic%2F568045", "count": 4652},
        {"query": "http%3A%2F%2Fwebboard.yenta4.com%2Ftopic%2F379035%3Fsort%3D1", "count": 3100}
      ]
    }
```

 * Top 5 popular queries done on Aug 2nd: `GET /1/queries/popular/2015-08-02?size=5`:

```js
    {
      "queries": [
        {"query": "http%3A%2F%2Fwww.getsidekick.com%2Fblog%2Fbody-language-advice", "count": 2283},
        {"query": "http%3A%2F%2Fwebboard.yenta4.com%2Ftopic%2F568045", "count": 1943},
        {"query": "http%3A%2F%2Fwebboard.yenta4.com%2Ftopic%2F379035%3Fsort%3D1", "count": 1358},
        {"query": "http%3A%2F%2Fjamonkey.com%2F50-organizing-ideas-for-every-room-in-your-house%2F", "count": 890},
        {"query": "http%3A%2F%2Fsharingis.cool%2F1000-musicians-played-foo-fighters-learn-to-fly-and-it-was-epic", "count": 701}
      ]
    }
```

### Guidelines

* You can use third party libraries if you know how to re-implement the features they're providing
* Your application cannot depend on any database or external software (one of the goals being to evaluate your ability to choose the right data structures)
* Provide a solution in one of the following languages: Go, Python
* Don't overthink the assignment. Provide a solution that you would be happy to push to production
* If you have several implementations in mind, pick one and discuss the alternatives in the README of your project

## Evaluation Criteria

* Please push your code to a GitHub repository or send us an archive
* Include a Readme helping us run your service
* Include a section about your thought process explaining your choices and share other alternative designs you considered
* Add any information you deem interesting for us to better understand your assignment

We'll evaluate:
 
 * the complexity & scalability of your algorithm
 * the readability of your code (including readability of your tests)
 * the correctness of the outputs of the API
 * you're ability to share your design choices and clearly weight pros & cons of alternative solutions
 * the overall quality of your written technical communication 

If you have any question, please out to the recruiter you are in touch with. For the evaluation, we do not take into account the fact that you did or did not ask a question.

Good luck!
