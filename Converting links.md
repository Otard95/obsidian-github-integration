# Converting from wiki to md links

Converting links shoulnt be difficult as both [[Wiki Links]] and [[MD Links]] are fairly simple, and containg all the same components. A simple `js` script should suffice.

## Steps to convert

Wiki Links syntax `[[<the Linked file>#<header>|<link text>]]`

MD Links syntax `[<Link text>](<link path>#<header>)`

1. Get all `.md` files in the vault(repo) and create a map from `name` -> `path`
2. Find all Wiki Links with RegEx. Somethin like `/\[\[(.+)\]\]/g`
3. Extract the components Split on `|` to get the link and text seperated. Then parse the link to split the file name from the header target.
4. Find the link path with the map from step 1
5. Create the new link by constructing the relative path between the file you are converting to the target.
6. Assemle the new Markdown link
