# VS Code Packs

Extension packs are a type of extension that simply bundles other extensions that are typically installed together.

## Introduction

Extension Packs in Visual Studio Code are useful when you want to install a collection of related extensions. In this project, I create Extension Packs so I can share my collection of extensions with other developers.

## Installing the Tools

If you have never built an extension before, you will need to set up your development environment. You will need to install:

- [Node.js](https://nodejs.org/en/), a JavaScript runtime that powers VS Code extensions.

- [Yeoman](https://yeoman.io/) scaffolding CLI tools as well as the code generator for VS Code.

    You can install Yeoman with the following command:

    ```bash
    npm install -g yo
    ```

- [Visual Studio Code Extension Generator](https://github.com/Microsoft/vscode-generator-code), the Yeoman generator that will help you build your extension.

    You can install the code generator tools for VS Code extensions by running the following command:
    ```bash
    npm install -g generator-code
    ```

## Generating a New Extension Project

Once you have these three tools installed, open up your terminal, navigate to your project directory, and run:

```bash
cd /to_project_path
yo code
```

You will quickly be prompted to choose what type of extension you are creating. In this case, choose `New Extension Pack`.

After that, you will be asked several different questions about your extension such as the name, identifier, and description. After answering all of the questions, you will receive confirmation that your project has been generated.

After opening the new project in VS Code, you’ll want to take a look at the `package.json` file. Pay specific attention to the `extensionPack` property.

Inside of this property is where you will list each of the extensions that should be included in your Extension Pack. For each extension, you’ll need to include the publisher and the name of the extension in the following format:

```text
<author>.<extension-name>
```

Once you’ve added the unique identifiers, you're almost done! Let’s make a few final touches to make your extension pack extra polished for your fans.

### Link to a GitHub repository

First initialize a Git repository with git init in your extension folder and push the project to GitHub. In package.json add a link to the repository:

```json
"repository": {
    "type": "git",
    "url": "https://github.com/username/extension-repo"
}
```

### Design an eye-catching icon

You should also add an icon to your extension pack that will help others identify your extension in their editors and in the marketplace.

```json
"icon": "icon.png"
```

### Write a descriptive README and changelog

Your README will be displayed in the extension marketplace, so it is a great way to describe what problem your extension pack solves, your inspiration for creating it, and the extensions that are included.

Similarly, updating the changelog is also helpful for you and the developers that download your pack. You can show which extensions you have added to the current version.

### Tidy up your project

Lastly, you should delete vsc-extension-quickstart.md and any other extraneous files before publishing.

## Publishing your extension pack

To publish your extension, you’ll need to install [Visual Studio Code Extensions](https://github.com/Microsoft/vscode-vsce), a command line tool for packaging, publishing, and managing extensions. Open up your terminal again and run:

```bash
npm install -g vsce
```

Then you can check the version of the extension, and see its commands by:
```bask
vsce --version
vsce --help
vsce command --help
```

If you want to export the extension pack directly from the command line, use the following command:
```bash
cd /to_project_path
vsce package
```

You well get a file with `.vsix` extension, now you can go to the **VS Code** and install extension package from `VSIX` file.

## References

- [How to Create an Extension Pack for Visual Studio Code](https://www.software.com/src/how-to-create-an-extension-pack-for-visual-studio-code).
- [How To Create an Extension Pack for Visual Studio Code](https://www.digitalocean.com/community/tutorials/how-to-create-an-extension-pack-for-visual-studio-code).
