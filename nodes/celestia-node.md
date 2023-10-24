---
description: Learn to build and install celestia-node.
---

# Install celestia-node

<!-- markdownlint-disable MD033 -->
<script setup>
import constants from '/.vitepress/constants/constants.js'
import arabicaVersions from '/.vitepress/constants/arabica_versions.js'
import mochaVersions from '/.vitepress/constants/mocha_versions.js'
import coffeeVersions from '/.vitepress/constants/coffee_versions.js'
</script>

This tutorial goes over building and installing celestia-node. This
tutorial assumes you completed the steps in
[setting up your development environment](./environment.md).

Install the celestia-node binary by running the following
commands:

1. Remove any existing copy of celestia-node, clone the repository,
   and change into the directory:

   ```bash
   cd $HOME
   rm -rf celestia-node
   git clone https://github.com/celestiaorg/celestia-node.git
   cd celestia-node/
   ```

2. Check out to the desired version, based on the network you will use:

   ::: code-group

   ```bash-vue [Mocha]
   git checkout tags/{{mochaVersions['node-latest-tag']}}
   ```

   ```bash-vue [Arabica]
   git checkout tags/{{arabicaVersions['node-latest-tag']}}
   ```

   :::

3. Build the `celestia` binary:

   ```bash
   make build
   ```

4. Install the binary:

   ::: code-group

   ```bash [Ubuntu]
   make install
   ```

   ```bash [Mac]
   make go-install
   ```

   :::

5. Build the `cel-key` utility:

   ```bash
   make cel-key
   ```

6. Verify that the binary is working and check the version:

   ```bash
   celestia version
   ```

The output will show the semantic version of celestia-node,
commit hash, build date, system version, and Golang version.

## Next steps

First, we recommend [reading the overview](./overview.md)
of our node types, if you haven't yet.

Now that you've installed Celestia Node, it's time to
[pick your node type](./decide-node.md) and run your node!

If you're planning to run a light node,
we recommend the [node RPC CLI tutorial](../developers/node-tutorial.md).

## Upgrading your binary

To upgrade your binary, you can install the latest version from the
instructions above and restart your node. If you run into any issues,
Refer to the [troubleshooting section](./celestia-node-troubleshooting.md).