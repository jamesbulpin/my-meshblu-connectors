# James Bulpin's Octoblu Connectors

This is a collection of experimental/prototype Meshblu/Octoblu connectors that aren't yet ready for the official or community repositories.

## Using this repository

To use this repository you need to add it your account. See https://meshblu-connectors.readme.io/docs/custom-registry for full details, however the quick method is:

1. Find your Octoblu account UUID and token (click the settings gear wheel in the Octoblu web app then click "Profile").
2. On a system with node.js and npm installed, ensure that the meshblu-utils package is installed (e.g. `npm install -g meshblu-utils`).
3. In an empty directory create a file named `meshblu.json` containing your UUID and token. It will look like this (but using your own UUID and token of course):

```
{
  "uuid": "90a332b0-62a6-4008-ac29-62237196629e",
  "token": "c15f5bc965a94027a897fdbaff71af3695f123a5",
  "protocol": "https",
  "hostname": "meshblu.octoblu.com",
  "port": 443
}
```

4. In the same directory create a file named `custom-registry-update.json`:

```
{
  "$set": {
    "octoblu.registries.connectors.my-custom-registry.uri": "https://raw.githubusercontent.com/jamesbulpin/my-meshblu-connectors/master/jamesbu-custom-repo.txt"
  }
}
```

5. Run `meshblu-util update -p -f ./custom-registry-update.json`
6. Optionally check this worked by running `meshblu-util get` and inspecting the output to look for the URL above
7. You may need to log out of, then back into the Octoblu web app to see the new connectors. Navigate to the "Things" => "All Things" page and look for the new connectors.

