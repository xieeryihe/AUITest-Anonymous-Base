# AUITestAgent: Automatic Requirements Oriented GUI Function Testing

## RQ1 & RQ2    
### Benchmark
We constructed thirty interaction tasks on eight popular apps. (In our experiment, the descriptions of the first fifteen tasks were in Chinese, and they have been translated here.)

| **App**           |      | **Task Description**                                                 | **$len(Trace^{ma})$** | **$Com_{R}$** | **Complexity Levels** |
| ----------------- | ---- | -------------------------------------------------------------------- | --------------------- | ------------- | --------------------- |
| **Meituan**       | 1    | Click the "Takeout" button                                                                                     | 1        | 1.90         | L1       |
|                   | 2    | Click on "Mine", click to enter the settings page                                                              | 2        | 3.80         | L1       |
|                   | 3    | Click on the location information in the upper left corner, modify the location to Beijing                     | 2        | 3.80         | L1       |
|                   | 4    | Click the "Takeout" button, click the "Food" section, click to enter the first shop in the shop list           | 3        | 5.70         | L2       |
|                   | 5    | Click the "Movie Show" button, select the first movie under "Now Showing" and click the "Want to Watch" button | 3        | 5.70         | L2       |
|                   | 6    | Click the "Buy Medicine" button, click "Cold and fever", click the second medicine in the list, click the medication prompt | 4        | 7.60      | L2       |
|                   | 7    | Turn on the "Elderly Mode"                                                                                     | 4        | 11.40        | L3       |
|                   | 8    | Delete all my favorites                                                                                        | 6        | 16.16        | L3       |
|                   | 9    | Click "Mine", click settings, add a new shipping address, click to choose the shipping address, choose the first address in the list at the bottom of the screen, then fill in the door number {number}, name {name}, phone number {phone_number}, and finally save the address                                                                                   | 12       | 18.04        | L3       |
| **Little Red Book**        | 10   | Click the first tweet, click the like button                                                          | 2        | 3.80         | L1       |
|                   | 11   | Click "Mine", click the settings button, click "Privacy Settings", click "Online Status", and change it to "Public" | 5        | 9.50         | L2       |
|                   | 12   | Click the "Shopping" button on the navigation bar, click a product card's product, add it to the shopping cart according to the default configuration, then go to the shopping cart page, delete all the products in the shopping cart                                                                                                                           | 8        | 19.00        | L3       |
| **Douban**          | 13   | Click the like button of the first tweet                                                                     | 1        | 1.90         | L1       |
|                   | 14   | Click the "Book, Film and Music" tab, click Douban List, click the recently popular movie Top20 list, click the "want to Watch" of the first movie in the list | 4        | 7.60         | L2       |
|                   | 15   | Click the "Mine" tab, click "Create My Book, Film and Music", swipe left in the center of the screen, click Create My Book TOP10, check the first three books in the list in turn, click OK, click Publish                                                                                                                                     | 9        | 20.42        | L3       |
| **Facebook**      | 16   | Click the Like button on the first post                                                                        | 1        | 1.90         | L1       |
|                   | 17   | Click the "What's on your mind?" input box, then send a post with the content "Hello everyone"                 | 4        | 10.92        | L2       |
|                   | 18   | Click the top Profile tab, click Edit Profile, scroll until you find the Bio section, click the Add button in the Bio section, click "Describe yourself", edit the content to "Hello Sky" and save                                                                                                                                        | 7        | 16.14        | L3       |
| **Gmail**         | 19   | Click to view the first email, then mark it as a favorite                                                      | 2        | 3.80         | L1       |
|                   | 20   | Send an empty email to {address}                                                                               | 3        | 9.02         | L2       |
|                   | 21   | Send an email to {address1} and {address2} with the subject "Test" and the body "Hello"                        | 7        | 18.54        | L3       |
| **LinkedIn**      | 22   | Click the avatar of the user who posted the first tweet                                                        | 1        | 1.90         | L1       |
|                   | 23   | View the detail page of the first notification in the notifications list                                       | 2        | 6.64         | L2       |
|                   | 24   | Click the "Jobs" tab, search for QA Engineer in the search bar, click to view the details of any job from the search results, and then click Save | 6        | 17.08       | L3       |
| **Google Play**   | 25   | Click the Top Charts tab, then click to view the detail of "Honor of Kings"                                    | 2        | 3.80         | L1       |
|                   | 26   | Click the Books tab, then enter the ratings and reviews section of the first book                              | 3        | 8.54         | L2       |
|                   | 27   | Download WhatsApp                                                                                              | 4        | 11.40        | L3       |
| **YouTube Music** | 28   | Click the "Explore" tap, then click the "New releases"                                                         | 2        | 3.80         | L1       |
|                   | 29   | Search singer Jay Chou                                                                                         | 3        | 9.02         | L2       |
|                   | 30   | Search for "Hello World" and then play any song from the search list                                           | 4        | 11.40        | L3       |

### Evaluation Results
Below are the evaluation results of AUITestAgent on the interaction benchmark, logs can be found in `interaction_results`.

| **App**        | **ID** | **Task Completion** | **$LCP(Trace, Trace^{ma})$** | **$len(Trace)$** | **$len(Trace^{ma})$** | **$CR$** | **$CD$** | **$SE$** |
|----------------|--------|---------------------|------------------------------|------------------|-----------------------|----------|----------|----------|
| **Meituan**        | 1      | √                   | 1                            | 1                | 1                     | 1.00     | 1.00     | 1.00     |
|         | 2      | √                   | 2                            | 2                | 2                     | 1.00     | 1.00     | 1.00     |
|         | 3      | √                   | 2                            | 2                | 2                     | 1.00     | 1.00     | 1.00     |
|         | 4      | √                   | 3                            | 3                | 3                     | 1.00     | 1.00     | 1.00     |
|         | 5      | √                   | 3                            | 3                | 3                     | 1.00     | 1.00     | 1.00     |
|         | 6      | √                   | 4                            | 4                | 4                     | 1.00     | 1.00     | 1.00     |
|         | 7      | ×                   | 3                            | 3                | 4                     | 1.00     | 0.75     | -        |
|         | 8      | ×                   | 5                            | 5                | 6                     | 1.00     | 0.83     | -        |
|         | 9      | √                   | 12                           | 12               | 12                    | 1.00     | 1.00     | 1.00     |
| **Little Red Book** | 10     | √                   | 2                            | 2                | 2                     | 1.00     | 1.00     | 1.00     |
|           | 11     | √                   | 5                            | 5                | 5                     | 1.00     | 1.00     | 1.00     |
| | 12     | ×                   | 4                            | 7                | 8                     | 0.57     | 0.50     | -        |
| **Douban**   | 13     | √                   | 1                            | 1                | 1                     | 1.00     | 1.00     | 1.00     |
|          | 14     | √                   | 4                            | 4                | 4                     | 1.00     | 1.00     | 1.00     |
|          | 15     | ×                   | 6                            | 6                | 9                     | 1.00     | 0.67     | -        |
| **Facebook**       | 16     | √                   | 1                            | 1                | 1                     | 1.00     | 1.00     | 1.00     |
|        | 17     | √                   | 4                            | 4                | 4                     | 1.00     | 1.00     | 1.00     |
|        | 18     | √                   | 7                            | 7                | 7                     | 1.00     | 1.00     | 1.00     |
| **Gmail**          | 19     | √                   | 2                            | 2                | 2                     | 1.00     | 1.00     | 1.00     |
|           | 20     | √                   | 3                            | 4                | 3                     | 0.75     | 1.00     | 0.75     |
|           | 21     | √                   | 7                            | 7                | 7                     | 1.00     | 1.00     | 1.00     |
| **LinkedIn**       | 22     | √                   | 1                            | 1                | 1                     | 1.00     | 1.00     | 1.00     |
|        | 23     | √                   | 3                            | 3                | 2                     | 1.00     | 1.00     | 1.00     |
|        | 24     | ×                   | 5                            | 5                | 6                     | 1.00     | 0.83     | -        |
| **Google Play**    | 25     | √                   | 2                            | 3                | 2                     | 0.67     | 1.00     | 0.67     |
|  | 26     | ×                   | 2                            | 5                | 3                     | 0.40     | 0.67     | -        |
|  | 27     | √                   | 4                            | 4                | 4                     | 1.00     | 1.00     | 1.00     |
| **YouTube Music**  | 28     | √                   | 2                            | 2                | 2                     | 1.00     | 1.00     | 1.00     |
|   | 29     | ×                   | 2                            | 3                | 3                     | 0.67     | 0.67     | -        |
|   | 30     | √                   | 4                            | 4                | 4                     | 1.00     | 1.00     | 1.00     |

## RQ3
### Benchmark
We constructed twenty verification tasks on eight popular apps, with thirty-two verification points. (In our experiment, the descriptions of the first ten tasks were in Chinese, and they have been translated here.)
For each task, we injected an anomaly so there are forty interaction traces.

| **App**           |      | **Interaction Task/Trace**                                         | **Verification Task**                                        | **Injected Anomaly**                                | **Number of Verification Points** |
| ----------------- | ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------ | --------------------------------- |
| **Meituan**       | 1    |  Click the "Takeout" button                                  | Check whether you enter the takeout page after clicking the "Takeout" button.  | （Interaction No Response）No response after clicking the button  | 1              |
|                   | 2    | Click on the location information in the upper left corner, modify the location to Beijing | Check whether the homepage location is Beijing after modifying the location. | （Illogical Response）The homepage location has not changed after modification  | 1              |
|                   | 3    | Click the "Takeout" button, click the "Food" section, click to enter the first shop in the shop list  | Check whether the name and rating of the first shop in the food section list page are consistent with these data on the shop details page. | （Interaction Irrelevant Anomaly）Inconsistent rating | 2              |
|                   | 4    | Click the "Movie Show" button, select the first movie under "Now Showing" and click the "Want to Watch" button   | Check whether the button turns gray and the text changes to "Already want to watch" after clicking the button. | （Interaction No Response）No response after clicking the button | 2              |
|                   | 5    | Search for "tickets", click on "Scenic Spot Tickets Channel" in search recommendations, click the "Scenic Spots" button, click the first scenic spot in the scenic spot list, and click to view the rating of the scenic spot | Check whether the rating of Disney is consistent across different pages.                         | （Interaction Irrelevant Anomaly）Inconsistent rating on the scenic spot details page             | 1              |
|                   | 6    | Click "Mine", click settings, add a new shipping address, click to choose the shipping address, choose the first address in the list at the bottom of the screen, then fill in the door number {number}, name {name}, phone number {phone_number}, and finally save the address  | Check whether the location and name of the shipping address are equal to the input values after saving the address.           | （Interaction Irrelevant Anomaly）Inconsistent name in the shipping address             | 2              |
| **Little Red Book**        | 7    | Click the first tweet, click the like button                                 | Check whether the button turns red and the like count increases by 1 after clicking the like button.                | （Illogical Response）Like count decreased by 1                    | 2              |
|                   | 8    | Click "Mine", click the settings button, click "Privacy Settings", click "Online Status", and change it to "Public" | Check whether the online status becomes public after changing to "Public".                     | （Interaction No Response）The online status did not change after checking         | 1              |
| **Douban**          | 9    | Click the "Book, Film and Music" tab, click Douban List, click the recently popular movie Top20 list, click the "want to Watch" of the first movie in the list | Check whether it changes to "Already want to watch" after clicking the want to watch button.                        | （Interaction No Response）No response after clicking the want to see button             | 1              |
|                   | 10   | Click the comment button of the first tweet                                     | Check whether the number of comments on the first tweet is consistent before and after clicking.                     | （Interaction Irrelevant Anomaly）Inconsistent number of comments before and after clicking             | 1              |
| **Facebook**      | 11   | Click the "What's on your mind?" input box, then send a post with the content "Hello everyone" | Check whether the post's content("Hello everyone") is correctly displayed on the homepage after sending it | （Illogical Response）The content of the Post has changed           | 1              |
|                   | 12   | Click the top Profile tab, click Edit Profile, scroll until you find the Bio section, click the Add button in the Bio section, click "Describe yourself", edit the content to "Hello Sky" and save | Check that the Bio's content is correctly displayed after clicking the Save button | （Illogical Response）The content of the Bio has changed            | 1              |
| **Gmail**         | 13   | Click to view the first email, then mark it as a favorite    | Check whether the favorite button turns blue after clicking it | （Interaction No Response）No response after clicking the favorite button                | 1              |
|                   | 14   | Send an email to {address1} and {address2} with the subject "Test" and the body "Hello" | Check on the email editing page whether the recipient, email subject, and email body are correctly displayed after typing, and check whether the email is sent after clicking send | （Illogical Response）After typing the email content, the email title abnormally becomes empty | 4              |
| **LinkedIn**      | 15   | Click the avatar of the user who posted the first tweet      | Check whether entered the user's homepage after clicking, whether the user's introduction and name are consistent before and after clicking | （Illogical Response）The introduction changes after clicking             | 3              |
|                   | 16   | View the detail page of the first notification in the notifications list | Check that the title of the first notification in the notification list is consistent after clicking it | （Illogical Response）The title changes after clicking             | 1              |
| **Google Play**   | 17   | Click the Top Charts tab, then click to view the detail of "Honor of Kings" | Check whether the name and rating of Honor of Kings are consistent on the list page and the details page; Check whether the game tags are in [new, Action, Strategy, MOBA, Casual, multi-player] | （Interaction Irrelevant Anomaly）Inconsistent game tags                  | 3              |
|                   | 18   | Download WhatsApp                                            | Check whether the download starts after clicking install     | （Interaction No Response）No response after clicking install                 | 1              |
| **YouTube Music** | 19   | Click the "Explore" tap, then click the "New releases"       | Check whether you enter the corresponding pages respectively after clicking explore and new releases | （Illogical Response）Enter the style page after clicking new releases | 2              |
|                   | 20   | Search for "Hello World" and then play any song from the search list | Check that after clicking the play button, whether the play button showing the song is playing | （Illogical Response）Enter the comment area after clicking the play button       | 1              |

### Evaluation Results
Below are the evaluation results of AUITestAgent on the verification benchmark, logs can be found in `verification_results`.

| App          | ID | Task Success | Correct Point Number | Correct Reasoning Number | Verification Point Number | Completion Tokens | Prompt Tokens | Point Acc. | Reasoning Acc. |
|--------------|-----|---------|---------------|-------------------|--------------|-------------------|---------------|-----------|---------------|
| **Meituan**  | 1   | √       | 1             | 1                 | 1            | 583               | 9621          | 1.00      | 1.00          |
|              | 2   | √       | 1             | 1                 | 1            | 724               | 9910          | 1.00      | 1.00          |
|              | 3   | √       | 1             | 1                 | 1            | 420               | 13576         | 1.00      | 1.00          |
|              | 4   | √       | 1             | 1                 | 1            | 433               | 13670         | 1.00      | 1.00          |
|              | 5   | √       | 2             | 2                 | 2            | 1615              | 40312         | 1.00      | 1.00          |
|              | 6   | √       | 2             | 2                 | 2            | 1539              | 39033         | 1.00      | 1.00          |
|              | 7   | √       | 2             | 2                 | 2            | 981               | 35706         | 1.00      | 1.00          |
|              | 8   | √       | 2             | 2                 | 2            | 884               | 35392         | 1.00      | 1.00          |
|              | 9   | √       | 1             | 1                 | 1            | 1047              | 29814         | 1.00      | 1.00          |
|              | 10  | √       | 1             | 1                 | 1            | 1022              | 30149         | 1.00      | 1.00          |
|              | 11  | √       | 2             | 1                 | 2            | 6651              | 123602        | 1.00      | 0.50          |
|              | 12  | ×       | 1             | 0                 | 2            | 6625              | 123173        | 0.50      | 0.00          |
| **Little Red Book** | 13  | √       | 2             | 2                 | 2            | 1150              | 26119         | 1.00      | 1.00          |
|              | 14  | √       | 2             | 2                 | 2            | 881               | 24447         | 1.00      | 1.00          |
|              | 15  | √       | 1             | 1                 | 1            | 643               | 23298         | 1.00      | 1.00          |
|              | 16  | √       | 1             | 1                 | 1            | 698               | 23756         | 1.00      | 1.00          |
| **Douban**   | 17  | √       | 1             | 1                 | 1            | 595               | 21147         | 1.00      | 1.00          |
|              | 18  | √       | 1             | 1                 | 1            | 603               | 21391         | 1.00      | 1.00          |
|              | 19  | √       | 1             | 1                 | 1            | 301               | 9097          | 1.00      | 1.00          |
|              | 20  | √       | 1             | 1                 | 1            | 295               | 9097          | 1.00      | 0.00          |
| **Facebook** | 21  | √       | 1             | 1                 | 1            | 1938              | 52223         | 1.00      | 1.00          |
|              | 22  | √       | 1             | 1                 | 1            | 1304              | 35488         | 1.00      | 1.00          |
|              | 23  | √       | 1             | 1                 | 1            | 814               | 31173         | 1.00      | 1.00          |
|              | 24  | √       | 1             | 1                 | 1            | 914               | 31659         | 1.00      | 1.00          |
| **Gmail**    | 25  | √       | 1             | 1                 | 1            | 474               | 17343         | 1.00      | 1.00          |
|              | 26  | √       | 1             | 1                 | 1            | 453               | 16766         | 1.00      | 1.00          |
|              | 27  | √       | 4             | 4                 | 4            | 3296              | 104559        | 1.00      | 1.00          |
|              | 28  | √       | 4             | 4                 | 4            | 2452              | 94151         | 1.00      | 1.00          |
| **LinkedIn** | 29  | √       | 3             | 3                 | 3            | 2007              | 36225         | 1.00      | 1.00          |
|              | 30  | √       | 3             | 3                 | 3            | 2120              | 37622         | 1.00      | 1.00          |
|              | 31  | ×       | 0             | 0                 | 1            | 366               | 14212         | 0.00      | 0.00          |
|              | 32  | √       | 1             | 0                 | 1            | 471               | 15344         | 1.00      | 0.00          |
| **Google Play** | 33 | √   | 3             | 3                 | 3            | 2175              | 44133         | 1.00      | 1.00          |
|              | 34  | ×       | 2             | 2                 | 3            | 2561              | 45393         | 0.67      | 0.67          |
|              | 35  | √       | 1             | 1                 | 1            | 498               | 20393         | 1.00      | 1.00          |
|              | 36  | √       | 1             | 1                 | 1            | 510               | 20220         | 1.00      | 1.00          |
| **YouTube Music** | 37  | √ | 2             | 1                 | 2            | 744               | 24031         | 1.00      | 0.50          |
|              | 38  | ×       | 1             | 1                 | 2            | 688               | 23707         | 0.50      | 0.50          |
|              | 39  | √       | 1             | 1                 | 1            | 603               | 23161         | 1.00      | 1.00          |
|              | 40  | √       | 1             | 1                 | 1            | 582               | 23924         | 1.00      | 1.00          |

