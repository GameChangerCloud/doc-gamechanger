---
title: Contact
permalink: /contactt
---
{% include header.html position="top" %}

Get in touch!

<form action="/ma-page-de-traitement" method="post">
    <div>
        <label for="name">Name :</label>
        <input type="text" id="name" name="user_name">
    </div>
    <div>
        <label for="mail">E-mail :</label>
        <input type="email" id="mail" name="user_mail">
    </div>
    <div>
        <label for="msg">Message :</label>
        <textarea id="msg" name="user_message"></textarea>
    </div>
</form>

{% include footer.html position="bottom" %}