# Java
## Unpack `.jar`
```
javap -c $(basename XMLErrors.class .class)
```

### Translate `.class` files to `.java`
```
find . -name "*.class" -exec javap -v '-c $(basename "$0" .class)'
```

## List packages in Jar file
```
jar tvf filename.jar
```
