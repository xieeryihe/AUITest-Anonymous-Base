# GUTA: Towards Automatic Goal-only GUI Testing for Mobile Apps

## Benchmark
We constructed thirty goal-only UI testing tasks on ten popular apps. 
(In our experiment, the descriptions of the first fifteen tasks were in Chinese, and they have been translated here.)

| App           | ID | Task Description                                                                                                      |
|---------------|----|--------------------------------------------------------------------------------------------------------------------|
| Meituan       | 1  | Test whether the location can be changed to Shanghai                                                               |
| Meituan       | 2  | Test whether all my favorites can be deleted                                                                       |
| Meituan       | 3  | Test whether "Elder Mode" can be turned on                                                                         |
| REDnote       | 4  | Test the like function in the tweet, whether the like button turns red after liking it, and whether the number of likes increases by 1 |
| REDnote       | 5  | Test the like function in the comment area of a tweet. After clicking the like button, see if it turns red and if the number of likes increases by 1 |
| REDnote       | 6  | Sequentially verify that the titles of the first through fourth tweets in the tweet list match their respective detail page titles |
| Douban        | 7  | Test whether the number of comments before and after clicking the comment button of any tweet is consistent         |
| Douban        | 8  | Test whether it is possible to mark the first movie in the recent popular movie list as "Wanted"                   |
| Douban        | 9  | After creating "My Movie TOP10" list and checking the publication of the first three films, test whether the films in the list are consistent with the selected ones |
| WeChatRead        | 10 | Test whether the like button turns red and the number of likes increases by 1 after liking the first comment of the third book in the "Hot Search List" |
| WeChatRead        | 11 | Test whether you can enter the book details page of "Those Things in the Ming Dynasty" in the "History" category   |
| WeChatRead        | 12 | Test whether you can enter the reading page of the first book in the bookshelf                                     |
| Keep          | 13 | Test the favorite function of tweet to see if the favorite button turns yellow and the number of favorites increases by 1 |
| Keep          | 14 | Test the profile modification function to see if the profile can be successfully modified to "Keep Moving"         |
| Keep          | 15 | Test the sports function to see if you can select tennis as the sports category                                    |
| Facebook      | 16 | Test whether the content of the second message in the notification list is consistent after viewing its details    |
| Facebook      | 17 | Test whether the post's content is correctly displayed after sending a post with the content "Hello everyone"      |
| Facebook      | 18 | Test whether your personal bio's content is correctly displayed after editing and saving it to "Hello Sky"         |
| Gmail         | 19 | Test whether the favorite button turns blue after marking the first email as a favorite                            |
| Gmail         | 20 | Test if you can send an empty email to {address}                                                                   |
| Gmail         | 21 | Check whether the recipient, subject, and body are correctly displayed when sending an email to {address1} and {address2} with the subject "Test" and the body "Hello" |
| LinkedIn      | 22 | Check whether the user's introduction and name are consistent after entering the homepage of the user who posted the first tweet |
| LinkedIn      | 23 | Check whether the notification's content is consistent by viewing the detail page of the first notification in the notifications list |
| LinkedIn      | 24 | Check whether the job's name and location are consistent by searching for QA Engineer and view the details of any job in the "Jobs" section |
| Google Play   | 25 | Check whether the rating of the first online marketplace app in the top chart is consistent on the chart page and its detail page |
| Google Play   | 26 | Test whether the download function by downloading WhatsApp                                                         |
| Google Play   | 27 | Check whether the rating of the first e-book is consistent on its detail page and ratings and reviews section      |
| YouTube Music | 28 | Test if you can check out the "New releases" section and enter the corresponding pages after each click           |
| YouTube Music | 29 | Test whether the search results of searching for singer Jay Chou all belong to him                                 |
| YouTube Music | 30 | Test the song playback function by searching for "Hello World" and playing any song from the search list           |



## RQ1

RQ1 evaluates GUTA's design in **decomposing UI testing goals** into interaction command and verification oracle. The **ground truth** for RQ1 is provided below.

GUTA fails to decompose the task with ID 6, as described in the paper.

| App           | ID | Task Description                                                                                                      | Interaction Command                                                       | Verification Oracle                                                                                         |
|---------------|----|--------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| Meituan       | 1  | Test whether the location can be changed to Shanghai                                                               | Change the location to Shanghai                                        | Check whether the location is successfully changed to Shanghai                                   |
| Meituan       | 2  | Test whether all my favorites can be deleted                                                                       | Delete all my favorites                                                | Check if my favorites have been deleted successfully                                              |
| Meituan       | 3  | Test whether "Elder Mode" can be turned on                                                                         | Turn on "Elder Mode" of the App                                        | Check if "Elder Mode" has been turned on                                                          |
| REDnote       | 4  | Test the like function in the tweet, whether the like button turns red after liking it, and whether the number of likes increases by 1 | Like any tweet                                                         | Check if the like button turns red and the number of likes increases by 1 after clicking it       |
| REDnote       | 5  | Test the like function in the comment area of a tweet. After clicking the like button, see if it turns red and if the number of likes increases by 1 | Like any comment in the comment section of any tweet                   | Check if the like button turns red and the number of likes increases by 1 after clicking it       |
| REDnote       | 6  | Sequentially verify that the titles of the first through fourth tweets in the tweet list match their respective detail page titles | Iterate through the first four tweets                                  | Check that the title of each tweet is consistent on the home page and detail page                 |
| Douban        | 7  | Test whether the number of comments before and after clicking the comment button of any tweet is consistent         | Click the Comment button on any Tweet                                  | Check if the like button turns red and the number of likes increases by 1 after clicking it       |
| Douban        | 8  | Test whether it is possible to mark the first movie in the recent popular movie list as "Wanted"                   | Mark the first movie in the recent popular movie list as "Wanted"      | Check if the first movie becomes "Wanted" after marking                                           |
| Douban        | 9  | After creating "My Movie TOP10" list and checking the publication of the first three films, test whether the films in the list are consistent with the selected ones | Create "My Movie TOP10" list, check the top 3 films and publish it     | Check whether the movies in "My Movie TOP10" list are the same as the movies you selected after publishing |
| WeChatRead        | 10 | Test whether the like button turns red and the number of likes increases by 1 after liking the first comment of the third book in the "Hot Search List" | Check out the third book on the "Hot List" and like the first comment  | Check if the like button turns red and the number of likes increases by 1 after clicking the like button |
| WeChatRead        | 11 | Test whether you can enter the book details page of "Those Things in the Ming Dynasty" in the "History" category   | Go to the "History" category and enter the book details page of "Those Things in the Ming Dynasty" | Check whether you have successfully entered the book details page of "Those Things in the Ming Dynasty" |
| WeChatRead        | 12 | Test whether you can enter the reading page of the first book in the bookshelf                                     | Read the first book on the shelf                                       | Check whether you have successfully entered the reading page of the first book                    |
| Keep          | 13 | Test the favorite function of tweet to see if the favorite button turns yellow and the number of favorites increases by 1 | Favorite any tweet on the homepage                                     | Check if the button turns yellow and the number of favorites increases by 1 after clicking the favorites button |
| Keep          | 14 | Test the profile modification function to see if the profile can be successfully modified to "Keep Moving"         | Edit my profile to "Keep Moving" and save                              | Check if the profile has been successfully modified to "Keep Moving"                              |
| Keep          | 15 | Test the sports function to see if you can select tennis as the sports category                                    | Start a sport and select the sport category as Tennis                  | Check if the sport category is successfully selected as tennis                                    |
| Facebook      | 16 | Test whether the content of the second message in the notification list is consistent after viewing its details    | View the details of the second message in the notification list        | Check whether the message's content is consistent before and after viewing its details            |
| Facebook      | 17 | Test whether the post's content is correctly displayed after sending a post with the content "Hello everyone"      | Send a post with the content "Hello everyone"                          | Check whether the post's content is correctly displayed after sending it                          |
| Facebook      | 18 | Test whether your personal bio's content is correctly displayed after editing and saving it to "Hello Sky"         | Edit your personal bio to "Hello Sky", and save the changes            | Check whether your personal bio's content is correctly displayed after saving                     |
| Gmail         | 19 | Test whether the favorite button turns blue after marking the first email as a favorite                            | Mark the first email as a favorite                                     | Check whether the favorite button turns blue after clicking it                                    |
| Gmail         | 20 | Test if you can send an empty email to {address}                                                                   | Send an empty email to {address}                                       | Check whether the email is successfully sent                                                      |
| Gmail         | 21 | Check whether the recipient, subject, and body are correctly displayed when sending an email to {address1} and {address2} with the subject "Test" and the body "Hello" | Send an email to {address1} and {address2} with the subject "Test" and the body "Hello" | Check on the email editing page whether the recipient, email subject, and email body are correctly displayed after typing |
| LinkedIn      | 22 | Check whether the user's introduction and name are consistent after entering the homepage of the user who posted the first tweet | Enter the homepage of the user who posted the first tweet              | Check whether the introduction and name of the user who posted the first tweet are consistent before and after clicking |
| LinkedIn      | 23 | Check whether the notification's content is consistent by viewing the detail page of the first notification in the notifications list | View the detail page of the first notification in the notifications list | Check whether the content of the first notification is consistent after viewing its details        |
| LinkedIn      | 24 | Check whether the job's name and location are consistent by searching for QA Engineer and view the details of any job in the "Jobs" section | Search for QA Engineer and view the details of any job from the search results in the "Jobs" section | Check whether the selected job's name and location are consistent across pages                    |
| Google Play   | 25 | Check whether the rating of the first online marketplace app in the top chart is consistent on the chart page and its detail page | View the details of the first online marketplace app in the top chart  | Check whether the rating of the online marketplace app is consistent on the chart page and its detail page |
| Google Play   | 26 | Test whether the download function by downloading WhatsApp                                                         | Download WhatsApp                                                      | Check whether the download successfully starts                                                    |
| Google Play   | 27 | Check whether the rating of the first e-book is consistent on its detail page and ratings and reviews section      | Enter the ratings and reviews section of the first e-book              | Check whether the rating of the e-book is consistent on its detail page and ratings and reviews section |
| YouTube Music | 28 | Test if you can check out the "New releases" section and enter the corresponding pages after each click           | Check out the "New releases" section                                   | Check whether you enter the corresponding pages after each click                                  |
| YouTube Music | 29 | Test whether the search results of searching for singer Jay Chou all belong to him                                 | Search singer Jay Chou                                                 | Check whether the search results all belong to Jay Chou                                           |
| YouTube Music | 30 | Test the song playback function by searching for "Hello World" and playing any song from the search list           | Search for "Hello World" and then play any song from the search list   | Check whether the song "Hello World" is successfully played                                       |

## RQ2

RQ2 assesses GUTA's performance in completing goal-only UI interaction tasks. The input for RQ2 is the 'Interaction Command' column from the RQ1 table.

GUTA's results are shown in the table below, and logs for task *i* can be found in the `/RQ2/i/auto` folder. For failed cases, we have also provided manual interaction traces as ground truth in the `/RQ2/i/manual` folder.

| ID     | TC      | # Correct Steps | # Total Steps | # Ideal Steps | TCR  | SER  |
|--------|---------|-----------------|---------------|---------------|------|------|
| 1      | ✔       | 2               | 2             | 2             | 1.00 | 1.00 |
| 2      | ✔       | 6               | 6             | 6             | 1.00 | 1.00 |
| 3      | ✔       | 4               | 4             | 4             | 1.00 | 1.00 |
| 4      | ✔       | 1               | 1             | 1             | 1.00 | 1.00 |
| 5      | ✔       | 3               | 3             | 3             | 1.00 | 1.00 |
| 6      | ✖       | 4               | 8             | 7             | 0.50 | -    |
| 7      | ✔       | 1               | 1             | 1             | 1.00 | 1.00 |
| 8      | ✔       | 4               | 4             | 4             | 1.00 | 1.00 |
| 9      | ✖       | 6               | 7             | 8             | 0.86 | -    |
| 10     | ✔       | 4               | 4             | 4             | 1.00 | 1.00 |
| 11     | ✔       | 3               | 3             | 3             | 1.00 | 1.00 |
| 12     | ✔       | 2               | 2             | 2             | 1.00 | 1.00 |
| 13     | ✔       | 2               | 2             | 2             | 1.00 | 1.00 |
| 14     | ✖       | 4               | 4             | 7             | 1.00 | -    |
| 15     | ✔       | 4               | 4             | 4             | 1.00 | 1.00 |
| 16     | ✔       | 2               | 3             | 2             | 0.67 | 1.50 |
| 17     | ✔       | 4               | 4             | 4             | 1.00 | 1.00 |
| 18     | ✖       | 5               | 8             | 9             | 0.63 | -    |
| 19     | ✔       | 1               | 1             | 1             | 1.00 | 1.00 |
| 20     | ✔       | 3               | 3             | 3             | 1.00 | 1.00 |
| 21     | ✖       | 2               | 8             | 7             | 0.25 | -    |
| 22     | ✔       | 1               | 1             | 1             | 1.00 | 1.00 |
| 23     | ✔       | 2               | 2             | 2             | 1.00 | 1.00 |
| 24     | ✖       | 3               | 4             | 6             | 0.75 | -    |
| 25     | ✔       | 3               | 5             | 3             | 0.60 | 1.67 |
| 26     | ✔       | 4               | 4             | 4             | 1.00 | 1.00 |
| 27     | ✖       | 3               | 3             | 4             | 1.00 | -    |
| 28     | ✖       | 1               | 1             | 2             | 1.00 | -    |
| 29     | ✔       | 3               | 3             | 3             | 1.00 | 1.00 |
| 30     | ✔       | 3               | 3             | 3             | 1.00 | 1.00 |
| Avg.   | 0.73    | -               | -             | 3.73          | 0.91 | 1.05 |


## RQ3

RQ3 evaluates GUTA's effectiveness in performing oracle verification. The input for RQ3 consists of the successfully completed interaction traces from RQ2, totaling 22 interactions.

The verification oracle and the injected bug for each verification task are shown in the table below.

| App           | ID | Test Task                                                                                                                | ID | Injected Bug                         | Bug Description                                                               |
|---------------|----|--------------------------------------------------------------------------------------------------------------------------|----|----------------------------------|-------------------------------------------------------------------------------|
| Meituan       | 1  | Check whether the location is successfully changed to Shanghai                                                           | 23 | Interaction No Response          | The positioning did not change after modification                             |
| Meituan       | 2  | Check if my favorites have been deleted successfully                                                                     | 24 | Illogic Response                 | Content still exists in my collection after deletion                          |
| Meituan       | 3  | Check if "Elder Mode" has been turned on                                                                                 | 25 | Interaction No Response          | Failed to start the "Elder Mode"                                              |
| REDnote       | 4  | Check if the like button turns red and the number of likes increases by 1 after clicking it                              | 26 | Illogic Response                 | The number of likes remains unchanged after clicking a like                   |
| REDnote       | 5  | Check if the like button turns red and the number of likes increases by 1 after clicking it                              | 27 | Illogic Response                 | The like button color does not change after clicking like                     |
| Douban        | 6  | Check if the number of comments on a tweet is consistent before and after clicking on it                                 | 28 | Interaction Irrelevant Anomaly   | The number of comments on detail page tweets is inconsistent                  |
| Douban        | 7  | Check if the first movie becomes "Wanted" after marking                                                                  | 29 | Interaction No Response          | After clicking the button, it still says "Want To Watch"                      |
| WeRead        | 8  | Check if the like button turns red and the number of likes increases by 1 after clicking the like button                 | 30 | Illogic Response                 | The like button turns blue                                                    |
| WeRead        | 9  | Check whether you have successfully entered the book details page of "Those Things in the Ming Dynasty"                  | 31 | Interaction No Response          | Failed to access the book details page                                        |
| WeRead        | 10 | Check whether you have successfully entered the reading page of the first book                                           | 32 | Interaction No Response          | Failed to access the book details page                                        |
| Keep          | 11 | Check if the button turns yellow and the number of favorites increases by 1 after clicking the favorites button          | 33 | Illogic Response                 | The number of favorites changed abnormally to 79                              |
| Keep          | 12 | Check if the sport category is successfully selected as tennis                                                           | 34 | Interaction No Response          | The page remains on the sport category selection page after selecting tennis  |
| Facebook      | 13 | Check whether the message's content is consistent before and after viewing its details                                   | 35 | Interaction Irrelevant Anomaly   | The recommended friends have changed on the details page                      |
| Facebook      | 14 | Check whether the post's content is correctly displayed after sending it                                                 | 36 | Illogic Response                 | The content of the post sent has changed                                      |
| Gmail         | 15 | Check whether the favorite button turns blue after clicking it                                                           | 37 | Interaction No Response          | The favorites button does not change after clicking                           |
| Gmail         | 16 | Check whether the email is successfully sent                                                                             | 38 | Interaction No Response          | The page stay on the email editing page after clicking the send button        |
| LinkedIn      | 17 | Check whether the introduction and name of the user who posted the first tweet are consistent before and after clicking  | 39 | Interaction Irrelevant Anomaly   | The user's name has changed                                                   |
| LinkedIn      | 18 | Check whether the content of the first notification is consistent after viewing its details                              | 40 | Interaction No Response          | The page does not change after clicking the first message                     |
| Google Play   | 19 | Check whether the rating of the online marketplace app is consistent on the chart page and its detail page               | 41 | Interaction Irrelevant Anomaly   | The rating on the detail page is inconsistent with the listing page           |
| Google Play   | 20 | Check whether the download successfully starts                                                                           | 42 | Interaction No Response          | The page does not respond after clicking the download button                  |
| YouTube Music | 21 | Check whether the search results all belong to Jay Chou                                                                  | 43 | Interaction Irrelevant Anomaly   | Content that does not belong to Jay Chou appeared in the search content       |
| YouTube Music | 32 | Check whether the song "Hello World" is successfully played                                                              | 44 | Interaction No Response          | The song does not play after clicking    

GUTA's results are shown in the table below, and logs for task *i* with LLM *llm* can be found in the `/RQ3/llm/i` folder.

Tasks 1 to 22 are categorized as "Correctness Verification," while tasks 23 to 44 fall under "Anomaly Detection."

### GUTA (GPT-based)

| App           | ID | Acc. | Reasoning Acc. | Token_p | Token_c | ID | Acc. | Reasoning Acc. | Token_p | Token_c |
| ------------- | -- | ---- | -------------- | ------- | ------- | -- | ---- | -------------- | ------- | ------- |
| Meituan       | 1  | 1    | 1              | 12416   | 1126    | 23 | 1    | 1              | 12290   | 474     |
| Meituan       | 2  | 1    | 1              | 27560   | 549     | 24 | 1    | 1              | 27699   | 704     |
| Meituan       | 3  | 1    | 1              | 22068   | 729     | 25 | 1    | 1              | 21694   | 672     |
| REDnote       | 4  | 1    | 1              | 6791    | 540     | 26 | 1    | 0              | 6585    | 230     |
| REDnote       | 5  | 1    | 1              | 19721   | 1008    | 27 | 1    | 0              | 20270   | 1183    |
| Douban        | 6  | 1    | 1              | 8622    | 232     | 28 | 1    | 1              | 8637    | 247     |
| Douban        | 7  | 1    | 1              | 22999   | 777     | 29 | 1    | 1              | 29914   | 775     |
| WeRead        | 8  | 1    | 1              | 26547   | 982     | 30 | 1    | 1              | 33877   | 969     |
| WeRead        | 9  | 1    | 1              | 22200   | 1468    | 31 | 0    | 0              | 24573   | 967     |
| WeRead        | 10 | 1    | 1              | 11627   | 597     | 32 | 1    | 1              | 19308   | 639     |
| Keep          | 11 | 1    | 0              | 11921   | 551     | 33 | 1    | 1              | 16287   | 440     |
| Keep          | 12 | 1    | 1              | 20006   | 613     | 34 | 0    | 0              | 25921   | 563     |
| Facebook      | 13 | 1    | 1              | 29763   | 867     | 35 | 1    | 1              | 24547   | 927     |
| Facebook      | 14 | 1    | 1              | 18814   | 472     | 36 | 1    | 1              | 16736   | 486     |
| Gmail         | 15 | 1    | 1              | 14093   | 686     | 37 | 1    | 1              | 13558   | 682     |
| Gmail         | 16 | 1    | 1              | 21665   | 276     | 38 | 1    | 1              | 22894   | 293     |
| LinkedIn      | 17 | 1    | 1              | 14635   | 1553    | 39 | 1    | 1              | 10492   | 457     |
| LinkedIn      | 18 | 0    | 0              | 17079   | 583     | 40 | 1    | 1              | 17771   | 778     |
| Google Play   | 19 | 0    | 0              | 27721   | 983     | 41 | 1    | 1              | 28209   | 1035    |
| Google Play   | 20 | 1    | 1              | 17987   | 410     | 42 | 0    | 0              | 16475   | 420     |
| YouTube Music | 21 | 1    | 1              | 22343   | 818     | 43 | 1    | 1              | 21828   | 832     |
| YouTube Music | 22 | 1    | 1              | 20374   | 599     | 44 | 1    | 1              | 22119   | 534     |
| Avg.          | -  | 0.91 | 0.86           | 18952.36| 746.32  | -  | 0.86 | 0.78           | 20076.55| 650.32  |

### GUTA (Claude-based)

| App           | ID  | Acc. | Reasoning Acc. | Token_p | Token_c | ID  | Acc. | Reasoning Acc. | Token_p | Token_c |
| ------------- | --- | ---- | -------------- | ------- | ------- | --- | ---- | -------------- | ------- | ------- |
| Meituan       | 1   | 1    | 1              | 14887   | 911     | 23  | 1    | 1              | 14692   | 907     |
| Meituan       | 2   | 1    | 1              | 45293   | 7629    | 24  | 1    | 1              | 43027   | 6258    |
| Meituan       | 3   | 0    | 0              | 25930   | 913     | 25  | 1    | 1              | 25025   | 1172    |
| REDnote       | 4   | 1    | 1              | 9019    | 1205    | 26  | 1    | 1              | 8949    | 1278    |
| REDnote       | 5   | 1    | 1              | 20906   | 2829    | 27  | 1    | 1              | 22234   | 3734    |
| Douban        | 6   | 1    | 1              | 8842    | 641     | 28  | 1    | 1              | 8773    | 534     |
| Douban        | 7   | 1    | 1              | 29859   | 2130    | 29  | 1    | 1              | 34467   | 4183    |
| WeRead        | 8   | 1    | 1              | 29874   | 839     | 30  | 1    | 1              | 29898   | 972     |
| WeRead        | 9   | 1    | 1              | 21594   | 869     | 31  | 1    | 1              | 20541   | 890     |
| WeRead        | 10  | 1    | 1              | 12642   | 919     | 32  | 1    | 1              | 12997   | 1031    |
| Keep          | 11  | 1    | 1              | 14265   | 1162    | 33  | 1    | 1              | 14245   | 1060    |
| Keep          | 12  | 1    | 1              | 25234   | 1142    | 34  | 1    | 1              | 26062   | 1208    |
| Facebook      | 13  | 1    | 1              | 27103   | 2393    | 35  | 1    | 1              | 27212   | 2345    |
| Facebook      | 14  | 1    | 1              | 19797   | 952     | 36  | 1    | 1              | 19768   | 874     |
| Gmail         | 15  | 1    | 1              | 11401   | 963     | 37  | 1    | 1              | 10502   | 569     |
| Gmail         | 16  | 1    | 1              | 26461   | 760     | 38  | 1    | 1              | 27510   | 542     |
| LinkedIn      | 17  | 1    | 1              | 12233   | 1761    | 39  | 1    | 1              | 12483   | 2015    |
| LinkedIn      | 18  | 0    | 0              | 19597   | 949     | 40  | 0    | 0              | 24108   | 3489    |
| Google Play   | 19  | 1    | 1              | 33921   | 2605    | 41  | 0    | 0              | 33970   | 2674    |
| Google Play   | 20  | 1    | 1              | 24565   | 502     | 42  | 1    | 1              | 25529   | 437     |
| YouTube Music | 21  | 1    | 1              | 24868   | 2232    | 43  | 1    | 1              | 24656   | 2020    |
| YouTube Music | 22  | 1    | 1              | 23555   | 1522    | 44  | 1    | 1              | 24807   | 1173    |
| Avg.          | -   | 0.91 | 0.91           | 21902.10| 1628.55 | -   | 0.91 | 0.91           | 22338.86| 1789.32 |

