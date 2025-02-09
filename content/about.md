---
title: About
type: landing

sections:
  - block: markdown
    content:
      title: About SNAIL
      subtitle: 
      text: We are the Software Normalization Assessment and Improvement Lab, a team of researchers from the [Computer Science Faculty of the University of Namur](https://www.unamur.be/info) and the [PReCISE research group of the Namur Digital Institute](https://nadi.unamur.be/research-centers/precise) of the University of Namur. Our team seeks to advance the state-of-the-art and practice of software engineering to improve software reliability by considering quality assessment and testing in both their human and technical contexts.

        
          We know a thing or two about research but are also very aware of the importance of keeping in touch with practitioners in a field such as Software Engineering. We therefore aim to collaborate with the industry to capture actual needs and provide practical solutions to practical issues. 

          
          Check out our [research](/research) and [MSc thesis](/mscthesis) to get an idea of what we do.
    design:
      # See Page Builder docs for all section customization options.
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '2'
  - block: features
    content:
      title: Our topics of interest include 
      subtitle: (but are far from limited to)
      text: 
      items:
        - name: Agile Methods
          description: 
          icon: people-group
          icon_pack: fas
        - name: Software Quality Improvement 
          description:
          icon: arrows-spin
          icon_pack: fas
        - name: Software Testing
          description:
          icon: bug
          icon_pack: fas
        - name: Developer Experience
          description:
          icon: laptop-code
          icon_pack: fas
        - name: AI for Software Engineering 
          description:
          icon: robot
          icon_pack: fas
        - name: Socio-technical Aspects
          description:
          icon: universal-access
          icon_pack: fas
  - block: contact
    id: contact
    content:
      title: Contact
      subtitle: ''
      text: ''
      # Contact details - edit or remove options as needed
      email: snail.info@unamur.be
      #phone: 888 888 88 88
      #appointment_url: 'https://calendly.com'
      address:
        street: rue Grandgagnage 21
        city: Namur
        #region: CA
        postcode: 'BE-5000'
        country: Belgium
        country_code: BE
      #directions: Enter Building 1 and take the stairs to Office 200 on Floor 2
      # office_hours:
      #   - 'Monday 10:00 to 13:00'
      #   - 'Wednesday 09:00 to 10:00'
      contact_links:
          - icon: github
            icon_pack: fab
            name: 'Find us on GitHub'
            link: 'http://github.com/snail-unamur'
          - icon: linkedin
            icon_pack: fab
            name: 'Find us on LinkedIn'
            link: 'https://www.linkedin.com/showcase/snail-team/'
      # Automatically link email and phone or display them just as text?
      autolink: true
      # Choose an email form provider (netlify/formspree)
      form:
        provider: netlify
        formspree:
          # If using Formspree, enter your Formspree form ID
          id: ''
        netlify:
          # Enable CAPTCHA challenge to reduce spam?
          captcha: true
      # Coordinates to display a map - set your map provider in `params.yaml`
      coordinates:
        latitude: '50.46584411773904'
        longitude: '4.857874265493509'
    design:
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '2'
---