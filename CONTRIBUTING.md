# Contributing to the Solid React SDK

Thank you for contributing to the Solid React SDK! The following is a set of community guidelines designed to help the contribution process work as smoothly as possible.

#### Table of Contents
  - Code of Conduct
  - Getting Started
    - What is Solid?
    - What is the React Solid SDK?
    - Further Reading
  - How do I report issues?
  - How do I request new features?
  - How do I contribute a new feature or bug fix?
    - First steps
    - Naming Conventions
    - Branching Conventions
      - What do I name my branch?
      - How do I open a Pull Request?
    - What should be included in my Pull Request?
    - What happens if my Pull Request is rejected? What next?
  - FAQ
    
  
  ## Code of Conduct
  The Solid Community has adopted a [Code of Conduct](https://github.com/solid/community/blob/master/code-of-conduct.md) that all contributors must adhere to. Please read and review before contributing.
  
  ## Getting Started
  
  #### What is the Solid React SDK?
  The [Solid React SDK](https://github.com/Inrupt-inc/solid-react-sdk) is a set of tools and documentation designed to streamline Solid application development in React. The repository serves as a gateway to the rest of our tools, and helps give a birds-eye view of all the available React libraries for Solid.
  

  #### Further Reading
  For more information, you can consult the following resources:
  * [Introduction to Solid](https://solid.inrupt.com/how-it-works)
  * [Solid Technical Documentation](https://solid.inrupt.com/docs/getting-started)
  * [Solid React SDK](https://github.com/Inrupt-inc/solid-react-sdk)
  * [Solid Community](https://solid.inrupt.com/community)
  
    
  ## How do I report bugs or other issues?
  To report a bug or issue in a repository, please open a github issue labeled as a `bug`. A good issue has the following information:
  
  | Item                    | Description                                               |
  | -----------             | -----------                                               |
  | Title                   | A descriptive title                                       |
  | Steps to Reproduce      | A list of all steps to reproduce this issue               |
  | Behavior                | What happened that you didn't expect                      |
  | Expected Behavior       | What you expected to happen                               |
  | Browser or Environment  | The browser or environment you discovered the issue with  |
  | Error Message or Code   | Any encountered error or error code                       |
  
  Once your issue is open, it will be reviewed and triaged. If more information is requested, please provide as much as you can. The more information, the easier it will be to find the root cause.
  
  ## How do I request new features?
  To request a new feature in a repository, please open a github issue labeled as `enhancement`. A good feature request has the following information:
  
  | Item                        | Description                                                       |
  | -------------               | ---------------                                                   |
  | Feature name / title        | A descriptive title                                               |
  | Feature description         | A detailed description of the requested feature                   |
  | Suggested implementation    | If you have a suggested way to approach the feature, list it here | 
  
  ## How do I contribute?
  
  #### First steps
  First of all, thank you for your interest in contributing!
  
  The first step with any bug fix or enhancement is to make sure there's an Issue opened for it. If there isn't, you may create it yourself. Once you've found the issue, if it is unassigned, you may assign it to yourself.
  
  Once you have an Issue assigned, you can begin coding.
  
  When coding is complete, the next step is to open a Pull Request to the `develop` branch. This is our integration branch and contains the features and fixes going into the next release.
  
  After your Pull Request is approved, it will be merged into the branch and released.    
  
  #### Branching Conventions
  
  ##### What do I name my branch?
  To make it easier on reviews, we ask that you use the format:
  
  issue-type/feature-name
  
  The feature name is a friendly name of the bug or feature you're working on. The issue-type is a prefix from the following list:
  
  | Issue Type          | Description                                               |
  | -----------         | --------------                                            |
  | bug                 | The fix included in the branch is a bug fix               |
  | feature             | The code included in the branch is a new feature          |
  | docs                | The fix included in the branch is purely documentation    |
  
  For example, if I was fixing a bug where a save button was red but should be green, I would name the branch:
  
  `bug/save-button-color`
  
  ##### How do I open a Pull Request?
  [define PR process]
  
  #### What should be included in my Pull Request?
  [define good PR practice]
  
  #### What happens if my Pull Request is defined? What next?
  [define remediation steps for rejected PRs]
