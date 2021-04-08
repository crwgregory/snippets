# Jira

## Clean csv export to remove Support Desk characters:
```
cat data.md | sed -E 's/{[^{}]*}//g' > data_clean.md
```
