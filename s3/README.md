# Create a static website using S3
1. Dowload the index.html file from this directory to your local machine
2. Navigate to Services | S37
3. Click "+ Create Bucket"
4. Enter a name of [UserName]-site
5. Be sure the Region is set toyour class default Region
6. Click "Next"
7. Examine Options but leave at defaults. Click "Next"
8. Un-check "Block all public access" and clik "Next"
9. Click "Create bucket"
10. Find your bucket and click on the buket name (not the checkbox).
11. Click "Upload"
12. Drap and drop the downloaded index.html file to the landing zone titled "Drag and drop files and folders here"
13. Click Next
14. In the "Manage public permissions section", change the drop-down to "Grant public read access to this object(s)" and click "Next"
15. Examine Properties but leave at defaults. Click "Upload" and wait for the upload to complete.
16. Click the Properties tab.
17. Click the "Static website hosting" tile
18. Click the "Endpoint:" link provided
   - Notice that you will get an error. Leave the tab with the error open.
19. Click the "Use this bucket to host a website" radio button.
20. Enter index.html in the index document field.
   - Yes, it looks like it's already there... but that's just a "serving suggestion," you must type in a value.
21. Click "Save"
22. Go back to the tab with the error from earlier and refresh the page, or,
click the "Static website hosting" tile again to re-open and click the Endpoint: link again.
