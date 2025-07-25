---
title: Educational resources
# Page type - we want a landing page (such as a homepage)
type: landing

# Your landing page sections - add as many different content blocks as you like
sections:
  - block: markdown
    id: education-intro
    content:
      title: Educational resources
      text: This page contains educational resources built by the SNAIL team. Feel free to use them or to [contact us](/about/#contact) if you want more information. Discover our [online resources](/course).
  - block: collection
    id: education-posts
    content:
      title: News
      subtitle: ''
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 3
      # Filter on criteria
      filters:
        # The folders to display content from
        folders:
          - post
        author: ""
        category: ""
        tag: "Education"
        publication_type: ""
        featured_only: false
        exclude_featured: false
        exclude_future: false
        exclude_past: false
      # Choose how many pages you would like to offset by
      # Useful if you wish to show the first item in the Featured widget
      offset: 0
      # Field to sort by, such as Date or Title
      sort_by: 'Date'
      sort_ascending: false
    design:
      # Choose a listing view
      view: compact
      # Choose single or dual column layout
      columns: '2'
  - block: collection
    id: education-courses
    content:
      title: Online resources
      subtitle: ''
      text: ''
      # Choose how many pages you would like to display (0 = all pages)
      count: 5
      # Filter on criteria
      filters:
        # The folders to display content from
        folders:
          - course
        author: ""
        category: ""
        tag: ""
        publication_type: ""
        featured_only: false
        exclude_featured: false
        exclude_future: false
        exclude_past: false
      # Choose how many pages you would like to offset by
      # Useful if you wish to show the first item in the Featured widget
      offset: 0
      # Field to sort by, such as Date or Title
      sort_by: 'Date'
      sort_ascending: false
    design:
      # Choose a listing view
      view: compact
      # Choose single or dual column layout
      columns: '2'
---