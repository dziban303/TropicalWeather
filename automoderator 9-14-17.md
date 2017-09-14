    # Approve all submissions that get caught in the spam-filter
    type: submission
    action: approve
    action_reason: Auto-approve

---

    # subreddit stats
    type: submission
    title (starts-with): "Subreddit Stats"
    author: HereComeStatBoi
    set_flair: ["Meta - Stats","mod2"]
    
---

    # Send an alert to modmail if anything gets 2+ reports
    reports: 2
    modmail: This item ({{permalink}}) by /u/{{author}} has received 2+ reports, please investigate.

---

    # Automatically remove anything that gets 3+ reports and send modmail
    reports: 3
    action: filter
    action_reason: 3+ reports
    modmail: This item ({{permalink}}) by /u/{{author}} was automatically removed due to receiving 3+ reports. Please verify that this action was correct.

---

    # No throwaways
    author:
        account_age: "< 24 hours"
    action: filter
    action_reason: New account, post filtered
    moderators_exempt: true

---

    # Set suggested sort to 'new'
    type: any
    set_suggested_sort: "new"

---

    # hello spam 
    type: any
    body (ends-with): "hello"
    action: spam
    action_reason: Hello bot spam

---

    # hello spam 
    type: any
    author: ["ColleenReeves", "JoannaTran1","core13","meatandtater","Liibowow","maxravenclaw","wolf_king245","fryedaddy99","flaming_luge","cowpat_90","plumby4321","fatboy123eva","llamachic87","wakebord23","exod678","de_dragons25","RetroBrit","Juliannegneu","TooBigToFailReddit","dsal1829","dolphinwail","fallout4please","Drum_Stick_Ninja","wrestlingfan001","mrplinko"]
    action: spam
    action_reason: Hello bot spam

---

    # spam 
    type: any
    body+title (includes): ["sex","sexy","dating"]
    action: spam
    action_reason: Sex spam
    
---

    # Spam domain blacklist
    moderators_exempt: false
    domain: [mother-earth.net, mother-earth.com]
    action: spam
    action_reason: Spam -- {{match}}
    modmail: /u/{{author}} has made a submission matching our custom spam domain blacklist ({{match}}).

---

    # troll remover
    Author:
        comment_karma: "< -8"
    action: filter
    action_reason: /u/{{author}} has less than -5 comment karma.
    modmail: From TropicalWeather- /u/{{author}}, a user with less than -8 karma, made a comment ({{permalink}}) and it was automatically filtered. Check if its trollish. If it is not, approve it.

---

    # good bot shit
    type: comment
    body: ["good bot", "bad bot"]
    action: remove
    action_reason: Good-Bad Bot
    message_subject: Warning. 
    message: | 
       Please don't make these good bot or bad bot comments in this subreddit. It just clutters up the comments.

---

    # donation shit
    type: any
    body (includes): ["hurricaneharveyfreedonation"]
    action: spam
    action_reason: hurricane donation scam
#    modmail_subject: Spam
#    modmail: This post by /u/{{author}} seems to be the donation scam. Spammed. {{permalink}}

---    