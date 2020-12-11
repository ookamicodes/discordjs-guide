# Update Node on Linux

Some problem of debbuging your bot or other node application can be that you have the false node version on your Linux device. Here an easy and fast guide how to update the node version.

1. Clean the npm cache: `npm cache clean -f`

2. Install the node version manager: `npm install -g n`

Now you can update Nodejs with `n stable` for the stable version, n latest
for the latest version or `n [version]` if you want a specific version.