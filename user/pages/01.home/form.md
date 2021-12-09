---
title: Help een Handje...

form:
    name: contact

    fields:
        name:
          label: Name (optional, anonymous tips welcome!)
          placeholder: Femke Halsema
          autocomplete: on
          type: text
          validate:
            required: false

        email:
          label: Contact Details (optional, anonymous tips welcome!)
          placeholder: Email, phone, whatever
          type: text
          validate:
            required: false

        message:
          label: Where is this place?
          placeholder: Address, as detailed as possible pls
          type: textarea
          validate:
            required: true

        description:
          label: Additional Details (optional)
          placeholder: How long has it been empty? Who owns it? How many floors?
          type: textarea
          validate:
            required: false

        honeypot:
          type: honeypot

        my_files:
          label: upload images :-)
          type: file
          multiple: true
          destination: 'user/data/contact/images'
          filesize: 5
          accept:
            - image/*

    buttons:
        submit:
          type: submit
          value: Submit
        reset:
          type: reset
          value: Reset

    process:
        captcha: false
        email:
            subject: "[Site Contact Form] {{ form.value.name|e }}"
            body: "{% include 'forms/data.html.twig' %}"
            attachments: my_files
        save:
            fileprefix: contact-
            dateformat: Ymd-His-u
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        message: Thank you for getting in touch!
        display: thankyou
---

<div class="main-content">

<span class="icon">😶</span>
<h1>Help een Handje...</h1>

<p><span class="lang">NL</span> ...something something Pandje. Voor een schoolproject van een vriend, zijn wij zéééér geïnteresseerd in gebouwen die al een tijd leegstaan. Dat is natuurlijk een groot probleem – zeker in deze tijden. Onze vriend werkt aan een database – het idee is om die confidentieel te delen met de wereld. Je kan alleen met hen in het echt afspreken. Er zijn jammer genoeg veel pottenkijkers. Natuurlijk mag geen plagiaat gepleegd worden bij het schoolproject. Een onvoldoende is zo zonde!</p>

<p><span class="lang">EN</span> For a schoolproject of a friend, we are reaaaally interested in buildings that have been empty for a long time. That is, of course, a big problem—especially in these times. Our friend is working on a database—the idea is to share it confidentially with the world. Though you can only meet with them in real life. Unfortunately, there are many snoopers. And it’s not allowed to commit plagiarism with a school project—an F would be a shame!</p>

<p class="bye"><i>—Yours truly, Hotel Mokum </i>🏠</p>

</div>

<div class="disclaimer">

<b>🔒Disclaimer</b>

<p><span class="lang">NL</span> Deze website is beveiligd – daar is veel moeite ingestopt. Controleer of https in de url staat – dan weet je zeker dat niemand meekijkt. De e-mail is versleuteld. Je mag direct mailen naar <a href="mailto:helpeenhandje@protonmail.com">helpeenhandje@protonmail.com</a>, als je dat liever hebt.</p>

<p><span class="lang">EN</span> This website is secure—we took a lot of measures to make this happen. Check whether https is written in your url—then you are confident that no one is spying along. The e-mail is encrypted. If people prefer, they could send an email directly to <a href="mailto:helpeenhandje@protonmail.com">helpeenhandje@protonmail.com</a></p>

</div>

<hr>

<h2>So, tell us about this place of yours!</h2>
