---
title: Help een Handje...

form:
    name: contact

    fields:
        name:
          label: Name (optional, anonymous tips welcome!)
          placeholder: Name (optional, anonymous tips welcome!)
          autocomplete: on
          type: text
          validate:
            required: false

        email:
          label: Contact Detail (optional, anonymous tips welcome!)
          placeholder: email, phone, whatever
          type: email
          validate:
            required: false

        message:
          label: Where is this place?
          placeholder: Give us an address
          type: textarea
          validate:
            required: true

        description:
          label: Further Description (how long has it been empty? Who owns it? How many floors?)
          placeholder: Got anything to add?
          type: textarea
          validate:
            required: false

        my_files:
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

# Help een Handje...

...kraak een Pandje. For a school project of a friend we are very interested in buildings in Amsterdam that have been empty for a while! Why don't you help us collect some :)
