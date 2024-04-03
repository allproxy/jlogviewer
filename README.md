<h1 align="center" style="border-bottom: none;">jlogviewer: JSON Log Viewer</h1>
JSON Log Viewer is a UI development tool that makes JSON logs human readable.
<p></p>
JSON fields can be automatically or manually annotated.  Filtering makes it easy to find relevant log records.
<p></p>
Source Code: [github.com/allproxy/jlogviewer](https://github.com/allproxy/jlogviewer)
<p></p>

![Alt text](image-1.png)

![image](https://img.shields.io/badge/mac%20os-000000?style=for-the-badge&logo=apple&logoColor=white)
![image](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![image](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)

## JLogViewer Online

* Click [https://allproxy.github.io/jlogviewer/](https://allproxy.github.io/jlogviewer/)
* Click **?** in the upper right and click the **Edit JavaScript** button to define JavaScript code to extract the Date, App Name, Message from your log records.

### Install NPM Package
> 1. `npm install -g jlogviewer`
> 2. Run `jlogviewer`

### Build Package

> 1. Clone repo.
> 2. `npm install` # The production build may take a minute...
> 3. `npm start`

> Open `JSON Log Viewer` in browser;
>    * [localhost:8888/jlogviewer](http://localhost:8888/jlogviewer)

### Updating

The JSON Log Viewer uses the [allproxy](https://github.com/allproxy/allproxy) package.

To update the `allproxy` npm package run:
> **npm update**

*NOTE**:
It is recommended that `Use hardware acceleration when available` is disabled on Chrome.

## Filtering

Advanced JSON field and boolean filters can be used to find relevant log records.

Example filters:
* Filter `response:>=400` shows responses with status greater than or equal to 400
* Filter `response:403` shows 403 responses
* Filter `agent:wget` shows `wget` clients
* Filter `bytes:>1000` shows responses that are greater than 1000 bytes
* Filter `remote_ip:*` can be used to sort remote IP addresses in ascending order
* Filter `-request:GET` shows non-GET requests

**Filter `response:>=400` shows responses with status**
![Alt text](image.png)

**Filter `response:403` shows 403 responses**
![Alt text](image-2.png)

**Filter `agent:wget` shows `wget` clients**
![Alt text](image-3.png)

**Filter `bytes:>1000` shows responses that are greater**
![Alt text](image-4.png)

**Filter `remote_ip:*` can be used to sort remote IP addresses in ascending order**
![Alt text](image-5.png)

**Filter `-request:GET` shows non-GET requests**
![Alt text](image-6.png)

## Documentation

User documentation is integrated into the app.  Click **?** in upper right corner.
![Alt text](image-7.png)

# Development Notes

### Updating Version

To update the Log Viewer version to the latest:
1. npm update # this update the allproxy package
2. ./copyBuildFromAllProxy.sh <allproxy repo path>
3. Create branch matching the allproxy version.

The **docs/index.html** needs to be modified so the GitHub Pages app will render properly:

1. These lines must be added to the start of the <header> tag:
    ```
        <link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
    ```

2. Remove '/' from href and src properties.

### Updating Configuration

1. Modify any of these config files:
    * jsonQueries.json
    * queries
    * briefJsonFields.json
    * jsonFields
    * jsonSubQueries.json
    * jsonLogScript
2. Run **node createApFileSystemJson.js** to build a new docs **apFileSystem.json** file.

## License

This code is licensed under the [MIT License](https://opensource.org/licenses/MIT).

![image](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
