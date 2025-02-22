<h2 id="table">Contribution Guidelines</h2>
When contributing to `Digital-Envision/express-services`, whether on Github or in other community spaces:
- Be respectful, civil, and open-minded.
- Before opening a new pull request, try searching through the [issue tracker](https://github.com/Digital-Envision/express-services/issues) for known issues or fixes.
- If you want to make code changes based on your personal opinion(s), make sure you open an issue first describing the changes you want to make, and open a pull request only when your suggestions get approved by maintainers.

<h2 id="contribute">How to Contribute</h2>
### Prerequisites
In order to not waste your time implementing a change that has already been declined, or is generally not needed, start by [opening an issue](https://github.com/Digital-Envision/express-services/issues/new/choose) describing the problem you would like to solve.

### Setup your environment locally

_Some commands will assume you have the Github CLI installed, if you haven't, consider [installing it](https://github.com/cli/cli#installation), but you can always use the Web UI if you prefer that instead._

In order to contribute to this project, you will need to fork the repository:

```bash
gh repo fork Digital-Envision/express-services
```

then, clone it to your local machine:

```bash
gh repo clone <your-github-name>/express-services
```

This project uses [pnpm](https://pnpm.io/) as its package manager. Install it if you haven't already:

```bash
npm i -g pnpm
```

Install all the required dependencies:

```bash
pnpm install
```

### Implement your changes

All the following services in this monorepo is required to follow the following code structures:

```bash
├── SERVICE-NAME
│ ├── actions # contains all the actions of the services
│ ├── models # contains all the database model of the service if exists
│ ├── utils # contains all the utilities for the services
│ ├── index.(js,ts) # the starting point of the services
```

In case you want to add your own folder to the services, keep everything on the same services folder. For example you want to add an email template, you use the following structures:

```bash
├── SERVICE-NAME
│ ├── actions # contains all the actions of the services
│ ├── models # contains all the database model of the service if exists
│ ├── templates # contains all the template for the email template
│ ├── utils # contains all the utilities for the services
│ ├── index.(js,ts) # the starting point of the services
```

### When you're done

Check that your code follows the project's style guidelines by running:

```bash
pnpm check
```

If your change should appear in the changelog, i.e. it changes some behavior of either the CLI or the outputted application, it must be captured by changeset which is done by running

```bash
pnpm changeset
```

and filling out the form with the appropriate information. Then, add the generated changeset to git:

```bash
git add .changeset/*.md && git commit -m "chore: add changeset"
```

When all that's done, it's time to file a pull request to upstream:

```bash
gh pr create --web
```

and fill out the title and body appropriately. Again, make sure to follow the [conventional commit](https://www.conventionalcommits.org/en/v1.0.0/) guidelines for your title.

### Credits

This documented was inspired by the contributing guidelines for [cloudflare/wrangler2](https://github.com/cloudflare/wrangler2/blob/main/CONTRIBUTING.md).
