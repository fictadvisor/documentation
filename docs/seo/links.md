# Human-readable links

Let's say `slug(x)` is a function that takes a string input and returns a URL-safe human readable slug.

Current implementation of `slug` function should be provided by [slugify](https://www.npmjs.com/package/slugify) npm package with following settings:

```
slug(x) = slugify(x, { replacement: '-', lower: true })
```

### General link generation rules

On duplicates, an increment should be added to the end of the link. Example: `lisovichenko-oleg-ivanovich-1`.

### Subject

Subject.link = `slug(Subject.name)`

### Teacher

**With a middle name:**

Teacher.link = `slug(Teacher.last_name + " " + Teacher.first_name + " " + Teacher.middle_name)`

**Without a middle name:**

Teacher.link = `slug(Teacher.last_name + " " + Teacher.first_name)`

### Course

Course.link = `Subject.link + "-" + Teacher.link`

