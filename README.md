README
================
Robert West
6/8/2020

# Describe JSON data. What is it, where does it get used, and why is it a good way to store data? This should be detailed enough that someone that hasn’t seen JSON data would have a good idea what they are dealing with. You should link to references where applicable.

*Java Script Object Notation* (or JSON) is a way to store
data.

# Discuss the possible packages/functions that are available for reading JSON data into R. (There are three major packages for JSON data.) Choose one and explain why you’ve chosen it.

The package that I chose to work with is the `jsonlite` package. I chose
this because it offers the functionality to return a nested list as a
data frame without parsing the data yourself.

# PLAYING AROUND WITH THE API

You should have a function to return parsed data from the following
calls: ∗ /franchise (Returns id, firstSeasonId and lastSeasonId and name
of every team in the history of the NHL)

∗ /franchise-team-totals (Returns Total stats for every franchise (ex
roadTies, roadWins, etc))

∗ /site/api/franchise-season-records?cayenneExp=franchiseId=ID
(Drill-down into season records for a specific franchise) · User should
be able to specify the franchise

∗ /franchise-goalie-records?cayenneExp=franchiseId=ID (Goalie records
for the specified fran- chise) · User should be able to specify the
franchise

∗ /franchise-skater-records?cayenneExp=franchiseId=ID (Skater records,
same interaction as goalie endpoint) · User should be able to specify
the franchise
