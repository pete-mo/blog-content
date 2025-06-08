
# Content Dashboard


## Recent Drafts
```dataview
TABLE title, date, primary_topic, difficulty_level
FROM "01 - Drafts"
SORT date DESC
LIMIT 10


TABLE title, date, status, word_count
FROM "02 - In Review"  
SORT date DESC


TABLE rows.file.link AS "Posts", length(rows) AS "Count"
FROM "03 - Published"
GROUP BY primary_topic
SORT length(rows) DESC

LIST
FROM "Meta/Topic Maps"
WHERE !contains(file.outlinks, "03 - Published")
