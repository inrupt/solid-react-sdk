# Contributing to the Solid React SDK

Thank you for contributing to the Solid React SDK! The following is a set of community guidelines designed to help the contribution process work as smoothly as possible.

#### Table of Contents
  - [Code of Conduct](#code-of-conduct)
  - [Getting Started](#getting-started)
    - [What is the React Solid SDK?](#what-is-the-solid-react-sdk)
    - [Further Reading](#further-reading)
  - [How do I report bugs or other issues?](#how-do-i-report-bugs-or-other-issues)
  - [How do I request new features?](#how-do-i-request-new-features)
  - [How do I contribute a new feature or bug fix?](#how-do-i-contribute)
    - [First steps](#first-steps)
    - [Branching Conventions](#branching-conventions)
      - [What do I name my branch?](#what-do-i-name-my-branch)
      - [How do I open a Pull Request?](#how-do-i-open-a-pull-request)
    - [What makes a good Pull Request?](#what-makes-a-good-pull-request)
    - [What happens if my Pull Request is rejected? What next?](#what-happens-if-my-pull-request-is-declined-what-next)
    
  
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
  
  The first step with any bug fix or enhancement is to make sure there's an issue opened for it. If there isn't, you may create it yourself. Once you've found the issue, if it is unassigned, you may assign it to yourself.
  
  Once you have an issue assigned, you can begin coding.
  
  When coding is complete, the next step is to open a Pull Request to the `develop` branch. This is our integration branch and contains the features and fixes going into the next release.
  
  After your Pull Request is approved, it will be merged into the branch and released.    
  
  #### Branching Conventions
  
  ##### What do I name my branch?
  To make it easier on reviews, we ask that you use the format:
  
  `issue-type/feature-name`
  
  The feature name is a friendly name of the bug or feature you're working on. The issue-type is a prefix from the following list:
  
  | Issue Type          | Description                                               |
  | -----------         | --------------                                            |
  | bug                 | The fix included in the branch is a bug fix               |
  | feature             | The code included in the branch is a new feature          |
  | docs                | The fix included in the branch is purely documentation    |
  
  For example, if I was fixing a bug where a save button was red but should be green, I would name the branch:
  
  `bug/save-button-color`
  
  ##### How do I open a Pull Request?
  To open a Pull Request, the simplest way is to use the github interface. Simply click on the `Pull Request` tab, and then on `New Pull Request`. 
  
  Once the `New Pull Request` form is open, make sure your Pull Request is targeting the correct branch. It should be merging from your branch into the `develop` branch. A Pull Request merging into `master` will be rejected.
  
  Then, simply fill in the form with a title and description, and submit the Pull Request. Someone will review it and either approve and merge, or request changes be made.
      
  #### What makes a good Pull Request?
  A good Pull Request will contain the following:
  
  * A descriptive title.
  * A descriptive description, including what changes were made and why they were made, if applicable.
  * No merge errors with the `develop` branch. If there are merge errors, please fix them and resubmit.
  * Well commented code. For example, comment blocks for each non-standard function, or any complicated logical pieces.
  * Additional documentation (such as adding new components to a README), if applicable.
  * A set of unit tests, if it's a new feature, or updated tests if it's a bug fix (where applicable).
  * Existing tests must remain unbroken.
  * If new libraries or dependencies are added, please link to them in the description and explain why they were necessary.
  
  
  #### What happens if my Pull Request is declined? What next?
  If some of the above rules are broken, then it's possible the Pull Request will not be approved. For most issues, the reviewer will simply request changes be made and wait for them to be addressed by the original author.
  
  In case of a major issue, such as a duplicate feature, security risk, or other serious problems, we may simply decline the Pull Request. Feel free to use the github comments to discuss the reasons for rejection. If it's something that can be remediated, you may fix the problem and re-submit the Pull Request at a later time.
  
 
