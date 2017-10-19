Instructions

Hint: If you just want to use Google Sheets' own JSONP generator, just try a link like this, where 18fLI7k8yU7t9bGGUqGfwm2RJWrVVwKjnm5pg9gtJ0ac is the sheet ID:

https://spreadsheets.google.com/feeds/list/18fLI7k8yU7t9bGGUqGfwm2RJWrVVwKjnm5pg9gtJ0ac/od6/public/values?&alt=json

Otherwise, for traditionally-formatted JSON, try this:

1.) Start a new Google Sheet

2.) Give it a name and add some data

3.) Tools > Script editor...

4.) Paste the contents of sheetsasjson.sj into the Code.gs file and save

5.) Publish > Deploy as web app...

6.) Execute the app as: your username

7.) Who has access to the app: Anyone, even anonymous

8.) Project version: 1

9.) Update/Publish

10.) Run the script. It will probably give an error, but that's okay.

11.) Copy the Google Sheet ID (the string that goes here in the URL: https://docs.google.com/spreadsheets/d/<THE SHEET KEY>/edit#gid=0)

13. Combine into this URL format: https://script.google.com/macros/s/<THE SCRIPT KEY>/exec?id=<THE SHEET KEY>&sheet=Sheet1

e.g. https://script.google.com/macros/s/AKfycbw_cqdXZADky_zHS3pi9aBL2S3-514vlxJkcnv5TJ1z9sxCqPY/exec?id=1MrdiPvoMBzgfSGyF_DpDQPvs2ZFFJpD5_YYttKqtKQ0&sheet=Sheet1

14. When you go to that URL in your browser, provided you are still logged into Google, it will ask you for permissions to run the script under your account. Grant the permissions.

15. The page should redirect to a page of JSON strings, meaning the script is successfully serving the live data.
16. Copy the URL that's currently in the address bar (it will be a different, redirected one from what you typed. It should look something like this: https://script.googleusercontent.com/macros/echo?user_content_key=_Z3_Z1xcr4Em2FKimBCQlGm9csKsOxIBx3TdNHRxiNPUO9dNup6vBocTtvwc1LKcFillx7gbRCuOJn8eFv5AagS1keUfA4jDOJmA1Yb3SEsKFZqtv3DaNYcMrmhZHmUMWojr9NvTBuBLhyHCd5hHa3HMflvAE5oEneTLZU5s79KARkcyFDMjX0ewt5-cuI2hRHouKSPCrKRcgufhrII6-M3MleihyRS6Yxs7ziheq_kx8s3fq8FhcV7V45FBz4fadfh_z-4qMMEa0mO-EXf9WyjPuXlbvplVwqJbeTowOR_fVIgxkfofiQ&lib=Mpc9sEUZubx48Zop7g8xYBjbZ7jG6IkQL).

You can use this URL in jQuery or D3 JSON calls so you can use the live data on your webpage for visualizations, DataTables and stuff.


Also see this for further instructions if you have troubles: http://pipetree.com/qmacro/blog/2013/10/sheetasjson-google-spreadsheet-data-as-json/


To import data straight from another CSV via URL, to then translate into JSON using the method above, use =IMPORTDATA("URL") in a Google Sheet. So for example:

=IMPORTDATA("https://docs.google.com/spreadsheets/d/1eGWgtyT4ouwi6DKZF8rE8eTlOjTeBrk3KozImcCFNyA/pub?output=csv") 

