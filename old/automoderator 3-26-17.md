    # Approve all submissions that get caught in the spam-filter
    type: submission
    action: approve
    action_reason: Auto-approve

---

    # Send an alert to modmail if anything gets 2+ reports
    reports: 2
    modmail: The above item has received 2+ reports, please investigate.

---

    # Automatically remove anything that gets 4+ reports and send modmail
    reports: 3
    action: filter
    action_reason: 3+ reports
    modmail: The above item was automatically removed due to receiving 3+ reports. Please verify that this action was correct.

---

    # No throwaways
    author:
        account_age: "< 7 days"
    action: filter
    action_reason: New account, post filtered
    moderators_exempt: true
    message: Because of the recent spam epidemic, we've had to put spam mitigation measures in place. As a result of you account being very newly created, your submission was automatically removed. Once your account is old enough, you will be able to post successfully. You may **[message the mods](https://www.reddit.com/message/compose?to=%2Fr%2FTropicalWeather&subject=Please%20Approve%20My%20Comment&message=%23***Put%20the%20URL%20to%20your%20comment%20in%20this%20message!***)** with the link to your comment ({{permalink}}) and we will approve it. We thank you for your understanding. 

---

    # Set suggested sort to 'new'
    type: any
    set_suggested_sort: "new"

---

    # hello spam 
    type: any
    body (ends-with): "hello"
    action: filter
    action_reason: Hello bot spam

---

    # hello spam 
    type: any
    author: ["ColleenReeves", "JoannaTran1","core13","meatandtater","Liibowow","wolf_king245","fryedaddy99","flaming_luge","cowpat_90","plumby4321","fatboy123eva","llamachic87","wakebord23","exod678","de_dragons25","RetroBrit","Juliannegneu"]
    action: filter
    action_reason: Hello bot spam

---

    # hello spam 
    type: any
    body+title (includes): ["sex","sexy","dating"]
    action: filter
    action_reason: Hello bot spam