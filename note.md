For this to work when accessed via jeyjeyemem.github.io/resume, you need to do:

1. Configure pathPrefix in gatsby-config:
    ```
    module.exports = {
        pathPrefix: `/resume`,
    }
    ```

2. Add --prefix-paths option to package.json **serve** and **deploy** scripts:
    ```
    "scripts": {
        "build": "gatsby build",
        "develop": "gatsby develop",
        "format": "prettier --write \"**/*.{js,jsx,ts,tsx,json,md}\"",
        "start": "npm run develop",
        "serve": "gatsby serve --prefix-paths",
        "clean": "gatsby clean",
        "test": "echo \"Write tests! -> https://gatsby.dev/unit-testing\" && exit 1", 
        "deploy": "gatsby build --prefix-paths && gh-pages -d public" 
    }
    ```