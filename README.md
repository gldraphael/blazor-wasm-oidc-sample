# Blazor WASM + Keycloak OIDC example

This is a sample to demonstrate that long user sessions for Blazor WASM applications.

## Running this sample

```sh
docker compose build
docker compose up
```

This will expose the following services:

Service    | Port
-----------|-------
`postgres` | `7571`
`keycloak` | `7572`
`wasmapp`  | `7573`

Wait for the logs to settle down before proceeding.

## Setting up a keycloak user

1. **Login:** Log into keycloak with username `keycloak` & password `keycloak`.
1. **Switch realm:** Use the dropdown at the top-left corner to switch from the `master` realm to the `example` realm.
1. **Create user:** Click on Users &rarr; Add user and follow the steps to create a user.
1. **Create password:** Switch to the Credentials tab, click on Set Password, set a password.

## Testing the sample

1. Go to wasm-app at `http://localhost:7573`.
1. Click on the Login link, and login with the user created in the previous step.
1. Open developer tools and clear session storage, and refresh the page. 

You will still remain logged in, as expected.
