# Code Review & Technical Checklist

## Descriptive

### Stats

`bin/rake stats`

* Ruby vs JS
* Controllers vs Models

### Models

* `gem install erd`
* `erd`

### Tests

* Unit Test
* Integration Tests

### Quality tools

_Rubocop_

`rubocop -a` (fix automatically small things such as styling, make the other problems more visible)

Check the complexity first, good starting point

`rubocop --only AbcSize,ClassLength rubocop --only AbcSize,ClassLength --f html > complexity.html`
(to get an HTML report)

_Brakeman (security)_

```bash
gem install brakeman
brakeman
```

This is security - should end up with an empty list.

_Precommit hook_

If you like getting message/forcing you to keep on quality, enforce a git precommit hook (ex: run quality)

### Code quality

* It's a process
* Boy scout rule
* Don't get good, get better

_CodeClimate_

I would recommend trying CC out (20$ a month)

Why:

* Good stats
* Trends
* Churn vs problems (ie: identify where you have problems AND that changes a lot)

### Performance analysis

[rack-profiler](https://github.com/MiniProfiler/rack-mini-profiler) & usage

### Server good practices

* Get a paying plan on Heroku
* Get backups (autobus)
* Get logentries and set alerts
* Create a separated stating environment
* How to copy data from prod to staging and local using pg:pull & pg:push (careful!)
