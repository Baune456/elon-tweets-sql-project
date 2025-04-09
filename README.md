# Elon Musk Tweets SQL Project

Dette projekt analyserer over **54.000 tweets** fra Elon Musk (2010–2025) ved hjælp af **PostgreSQL**. Formålet er at vise praktiske SQL-kompetencer gennem dataimport, databehandling og dybdegående analyser.

---

## Projektstruktur

```
elon-tweets-sql-project/
├── data/
│   └── all_musk_posts.csv
│
├── sql/
│   ├── create_table.sql
│   ├── import_data.sql
│   └── analysis_queries.sql
│
└── README.md
```

---

##️ Opsætning

1. **Start PostgreSQL**
```bash
psql postgres
```

2. **Opret database og skift**
```sql
CREATE DATABASE elon_tweets;
\c elon_tweets
```

3. **Kør SQL scripts**
```sql
\i sql/create_table.sql
\i sql/import_data.sql
\i sql/analysis_queries.sql
```

---

## Eksempler på analyser

**Top 5 mest likede tweets:**
```sql
SELECT fullText, likeCount 
FROM all_musk_posts 
ORDER BY likeCount DESC 
LIMIT 5;
```

**Tweets pr. år:**
```sql
SELECT EXTRACT(YEAR FROM createdAt), COUNT(*) 
FROM all_musk_posts 
GROUP BY 1 
ORDER BY 1;
```

**Antal retweets:**
```sql
SELECT isRetweet, COUNT(*) 
FROM all_musk_posts 
GROUP BY isRetweet;
```

_(Se flere i `sql/analysis_queries.sql`)_

---

## Formål

Projektet er udviklet som portefølje til jobsøgning og erfaring inden for dataanalyse, BI og AI.

---

## Udviklet af

**Emil Baungaard**  
[github.com/Baune456](https://github.com/Baune456)
