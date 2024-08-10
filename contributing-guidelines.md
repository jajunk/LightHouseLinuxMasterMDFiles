# Contributing to LinuxLightHouseMasterMDFiles :house_with_garden:

We're :smile: excited :smile: you're interested in contributing to the Linux Lighthouse Project! This document outlines the process for contributing to our project.

## Code of Conduct :book:

By participating in this project, you agree to abide by our [Code of Conduct](code-of-conduct.md).

## How Can I Contribute? :raising_hand:

### Reporting Bugs :beetle:

- Before creating bug reports, please check the issue list as you might find out that you don't need to create one.
- When you are creating a bug report, please include as many details as possible and follow the issue template.

### Suggesting Enhancements :bulb:

- Before creating enhancement suggestions, please check the issue list as you might find out that you don't need to create one.
- When you are creating an enhancement suggestion, please include as many details as possible.

### Your First Code Contribution :first_place_medal:

1. Fork the repo
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Styleguides :pencil2:

### Git Commit Messages :speech_balloon:

- Use the present tense ("Add feature" not "Added feature")
- Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
- Limit the first line to 72 characters or less.

### Documentation Styleguide :notebook:

- Use [Markdown](LightHouseMarkDownStyleGuide.md) for documentation.

### Issue and Pull Request Labels :label:

- `bug` - Something isn't working
- `duplicate` - This issue or pull request already exists
- `enhancement` - New feature or request
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention needed
- `invalid` - Doesn't seem right
- `question` - Further information is requested
- `wontfix` - This won't be fixed

## Branching Strategy
- We follow the `GitFlow` branching strategy:

`main` branch contains the stable, released version
`dev` branch is for ongoing development
`Feature` branches should be created for new content or significant changes

### Use pull requests to merge changes into `develop`

## Release Cycle

Pull requests are merged into the `dev` branch on a weekly basis
The `main` branch is updated with stable releases on a monthly basis
`Hotfixes` for critical issues may be applied directly to `main` and then merged back into `dev`

Contributors can expect their approved changes to appear in the `dev` branch within a week of approval, and in a stable release within 1-2 months, depending on the release schedule.

## Thank you for contributing to Linux Lighthouse! :tada::clap: