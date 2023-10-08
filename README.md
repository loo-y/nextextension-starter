[中文](./README.zh.md)


# NextExtension-Starter
This is a chrome extension starter based on Next.js. The extension manifest version is set as v3.

## Instructions
### Modifying Files
|Code Directory|Generated File|
|--|--|
|[```app/(pages)/options```](./app/(pages)/options/)|options.html|
|[```app/(pages)/popup```](./app/(pages)/popup/)|popup.html|
|[```app/scripts/content```](./app/scripts/content)|content-script.js|
|[```app/scripts/inject```](./app/scripts/inject)|inject-script.js|


### How to Build
1. Install dependencies
    ```bash
    npm i
    ```
2. Build extension
    ```bash
    npm run build:extension
    ```

### NPM Script Descriptions
- **```pack:extensionscript```:**  Generates the actual content-script.js and inject-script.js.

- **```afterbuild```:**  Extracts inline scripts from the packaged HTML files and includes them using the src attribute. The reason is Chrome extensions do not support inline scripts.

- **```zip:extension```:**  Generates a packaged file for the extension, making it easier for distribution. The zip file can be included in the project release.

### Configuration Details
- **```extension.next.config.js```:**  Contains the actual Next.js configuration for the extension. The original ```next.config.js``` is preserved for debugging HTML styles locally using ```npm run dev```.

- **```extension.webpack.config.js```:**  Corresponds to the npm script ```pack:extensionscript```, used for packaging the two script files. You can also add additional scripts as needed.
