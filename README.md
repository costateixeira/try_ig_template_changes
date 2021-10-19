# Local Template tester

This script gets a FHIR IG template from a github repo / branch, and replaces your local cache. This is used to test the IG templates.

## How to use
Just download this file anywhere, replace the values in the beginning of the file by what you want to replace with what, and run. It will replace your locally cached template





How this works: 
This replaces the entire files except package.json to fool the publisher into thinking the template hasn't been touched, so the publisher does not download a new version.

1. delete the temporary folder in the current folder
2. clone the repo/branch
3. reorganize files in the correct folder structure 
4. remove .git folder
5. renames the package in the cache to append _original at the end (is this a good idea?) 
6. moves the  downloaded content content into the package in cache
7. restores the package.cache from the original template folder 

This could be improved, it's just a first working prototype
Windows only. Uses Robocopy 

To do:
* Fail gracefully
* Review the _Original renaming - what if there is already a _original?
...


