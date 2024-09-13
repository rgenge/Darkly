# Exposure exploit

# Tools
Shell script to crawls folders and subfolders in /.hidden

# How to solve it
When checking the .hidden folder there are a lot of folders with weird names,
but everyone of them has a README file with a phrase in french. When starting
clicking on subfolders it became evident that the flag couldn't be retrieved
manually, so it was developed a script to extract the texts of each of the
README files and output into a file.

More than 5200 files were read, and in the end, the text was found:
Hey, here is your flag : d5eec3ec36cf80dce44a896f961c1831a05526ec215693c8f2c39543497d4466

Do not allow access from external sources to folders with sensitive information
or that shouldn't be exposed at all.

It doesn't matter if the folder just contains recipes from grandma, don't expose
it if it's not necessary for your application.