---
title: Meet the Team
type: landing

sections:
  - block: people
    content:
      title: Meet the Team
      # Choose which groups/teams of users to display.
      #   Edit `user_groups` in each user's profile to add them to one or more of these groups.
      user_groups:
        - Faculty
        - Researchers
        - PhD Students
        - MSc Students
        - Visitors
      sort_by: Params.last_name
      sort_ascending: true
    design:
      # Show user's social networking links? (true/false)
      show_social: true
      # Show user's interests? (true/false)
      show_interests: true
      # Show user's role?
      show_role: true
      # Show user's organizations/affiliations?
      show_organizations: false
  - block: people
    content:
      title: Former Members
      subtitle: ''
      # Choose which groups/teams of users to display.
      #   Edit `user_groups` in each user's profile to add them to one or more of these groups.
      user_groups:
        - Alumni
      sort_by: Params.last_name
      sort_ascending: true
    design:
      # Show user's social networking links? (true/false)
      show_social: true
      # Show user's interests? (true/false)
      show_interests: false
      # Show user's role?
      show_role: true
      # Show user's organizations/affiliations?
      show_organizations: false
---