# Calendar Heatmap

## Query

```sql
SELECT FORMAT(DATEADD(DAY, -DATEDIFF(DAY, CreationDate, GETDATE()), GETDATE()), 'yyyy-MM-dd'),
COUNT(*) AS 'AnswerCount' FROM Posts
WHERE PostTypeId = 2 /* question = 1, answer = 2 */
AND CreationDate > '2010-04-01'
GROUP BY DATEDIFF(DAY, CreationDate, GETDATE())
```

## Libs

- [CSVTOJSON](https://www.npmjs.com/package/csvtojson)

## Resource

- [Tutorial: Building a D3.js Calendar Heatmap (to visualize StackOverflow Usage Data)](https://blog.risingstack.com/tutorial-d3-js-calendar-heatmap/)
