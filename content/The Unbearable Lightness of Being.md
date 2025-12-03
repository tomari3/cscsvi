---
title: The Unbearable Lightness of Being
author: Milan Kundera
isbn: 9780571224388
genre: Fiction, Philosophy, Literature, Novels, Romance, Czech Literature, Classics
pages: 314
format: paperback
language: english
publish_date: 01-01-1999
publisher: 
purchase_date: 12-08-2024
purchase_price: 
start_date: 12-08-2024
finish_date: 20-08-2024
reading_time: 
rating: 8
tags: [book, {{genre}}]
---

## Summary
<!-- Brief synopsis or your own summary -->

## Themes
<!-- Main themes or topics covered in the book -->

## Key Characters
<!-- List of important characters (for fiction) -->

## Favorite Quotes
<!-- Memorable quotes or passages -->

## Personal Thoughts
<!-- Your reflections, criticisms, or interpretations -->

## Recommendations
<!-- Who would you recommend this book to? -->

## Related Books
<!-- Other books by the same author or in the same genre/topic -->

## Re-readability
<!-- Would you read it again? Why or why not? -->

## Action Items
<!-- Any actions or ideas inspired by the book -->

## Notes
<!-- Detailed notes, chapter summaries, etc. -->

```dataviewjs
dv.header(3, "Reading Stats")
const currentPage = dv.current()
const readingDays = (date) => {
    if (!currentPage.start_date || !date) return "N/A"
    return Math.ceil((new Date(date) - new Date(currentPage.start_date)) / (1000 * 60 * 60 * 24))
}
const pagesPerDay = (pages, days) => {
    if (days === "N/A" || !pages) return "N/A"
    return (pages / days).toFixed(1)
}
dv.table(["Metric", "Value"], [
    ["Days to finish", readingDays(currentPage.finish_date)],
    ["Pages per day", pagesPerDay(currentPage.pages, readingDays(currentPage.finish_date))]
])
```