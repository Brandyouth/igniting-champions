---
title: Contact Us
menu: Contact Us


form:
    name: contact-form
    fields:
        - name: name
          label: Name
          placeholder: Enter your name
          autocomplete: false
          type: text
          validate:
              required: true

        - name: email
          label: Email
          placeholder: Enter your email address
          type: email
          validate:
              required: true

        - name: message
          label: Message
          placeholder: Enter your message
          type: textarea
          validate:
              required: true

    buttons:
        - type: submit
          value: Submit

    process:
        - email:
            from: "{{ config.plugins.email.from }}"
            to:
                - "{{ config.plugins.email.to }}"
            subject: "[Contact] {{ form.value.name|e }}"
            body: "{% include 'forms/data.html.twig' %}"
        - message: Thank you for your message!
        - display: thankyou
---
## Contact Us

Please fill out the form below to get in touch with us.
