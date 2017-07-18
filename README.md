# HearingAid
Drop a notes field in any form and send the responses to a Google Sheet and/or email.

Having conversations with visitors is everything to unlocking scale and quality as they move through your forms. The hard part is, while we know there is a human on the other side of the screen, we operate "funnels" that are really only a one way experience for your users. The key is to turn your "funnels" into "conversations" by making it a two way experience.

A powerful way we have converted our funnels into conversations is by strategically placing free form notes fields into forms a percentage of the time. You always need to be careful with adding fields like this to a form process. However, we have seen cases where simply having the field actually increases frontend conversion! 

We put this tool together so that anyone can:

1. Place a small snippet of javascript wherever they would like to capture user data.
2. Configure the display to only be a percentage of the time.
3. Put the responses into a Google Sheet and/or get emailed to you.

# Here's How It Works

Place the following snippet of code on any page/any form wherever you would like to capture user questions/comments/notes/etc.

```javascript
<script type="text/javascript" src="https://www.envoymediagroup.com/track/nimble/messenger.js"></script>
<script type="text/javascript">
    Nimble_Messenger_Config = {
        textarea: {
            style: 'width: 300px; height: 100px',
            class: null,
            id: null,
            name: null,
            placeholder: 'Do you have any questions so we may further assist you? (optional)',
            prepend_html: null,
            append_html: null
        },
        //comma separated emails (optional)
        mail_message_to: '',
        //google sheet url with edit access to nimble@envoymediagroup.com (optional)
        google_sheet_url: '',
        //order of google sheet columns (if google sheet is used)
        google_sheet_columns: [
            'ID', //do not change, must be first
            'DateTime', //Ex: 2017-07-17 16:09:13
            'Message',
            'URL',
            'Country Code', //Ex: US
            'Region', //Ex: CA
            'City', //Ex: Los Angeles
            'Postal Code', //Ex: 91324
            'Latitude', //Ex: 39.04809952
            'Longitude', //Ex: -77.47280121
            'Area Code', //Ex: 818
            'Device Type', //Desktop or Tablet or Phone
            'Is Touch Enabled', //0 or 1
            'Operating System', //Ex: OSX
            'Operating System Version', //Ex: 10.10
            'Browser Type', //Ex: Chrome
            'Browser Version', //Ex: 58
            'IP', //Ex: 34.198.92.14
            'User Agent' //Ex: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36
        ],
        extra: {
            //Any extra key/value data you want stored.
            //Remember to add the key to google_sheet_columns if you are using the sheet feature.
        },
        id: null
    };
    nimble_messenger_percent_show = 100;

    nimbleMessengerShow();
</script>
```
There are a lot of configuration options here and many have examples but you need to make sure you set either set a mail_message_to email or a google_sheet_url. If you decide to use a Google Sheet. You need to:

1. Make a Google Sheet
2. Give nimble@envoymediagroup.com Edit access
3. Paste the sheet url in the google_sheet_url variable
4. (Optional) Adjust the columns you would like in the report. The google_sheet_columns array above has all of the default columns we will append to the report. You can remove them, reorder them or even add your own by adding key/value data to the "extra" object and adding the extra column key to the google_sheet_columns array.
5. (Optional) Change the id from null to something that uniquely identifies your user. If you leave it as null, the script will automatically create a unique id for you.
6. (Optional) Change the nimble_messenger_percent_show variable from 1 to 100. This controls the percentage of the time that the field will even show. It defaults to 100 percent.
    
Feel free to use this tool whenever you need to grab information from users quickly and don't want to go through all the trouble of setting up databases/reports/etc. The information that comes from your actual visitors and customers is priceless and something that a focus group simply can't match. If you feel like you've hit a wall with optimization, maybe you just need to gather some user input to help guide what your next optimizations should be.

Enjoy!
