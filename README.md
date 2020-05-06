# {{PLUGIN_NAME}}

{{PLUGIN_DESC}}

## Plugin Development Process

1. Plugin Git repo setup:
    1. Clone repository ui-plugin-template and create new repo name starting with `ui-plugin-{{PLUGIN_NAME}}`
2. Dev Env setup:
    1. Install node js with npm (10.15.3 version)
    2. Install and setup local git
    3. Create branch of `ui-plugin-{{PLUGIN_NAME}}` repository in local system
    4. Find and replace {{PLUGIN_NAME}} token to your plugin’s unique name
    5. Find and replace {{PLUGIN_DESC}} token with small description of plugin functionality
    6. Execute `npm install` at your plugin folder
    7. Update Env Settings file at `/config/default.json`:
        1. serverUrl - dev url of tenant you want to deploy and test plugin
        2. Headers - update client id, tenant id, user id, user roles, auth client id and auth client secret fields
3. Develop plugin:
    1. Create plugin element or plugin function following guide at: dev guide link
    2. Create base config for plugin element under `/src/plugin-config`, if any by following guide at: plugin config guide link
    3. Add docking point config under `/src/docking-host-config` following guide at: docking-host-config guide link
    4. Ensure plugin logic is testable
    5. Lint plugin logic by running `npm run lint`
    6. Write and run unit test by running `npm run test` for plugin (R2)
4. Dev test:
    1. Run `npm run compile-and-deploy` command to create artifact and deploy plugin into configured dev env.
        1. Run `npm run compile-and-deploy —- —-DEPLOY_CONFIG` to deploy config changes as needed
    2. Open browser in dev mode(using query string **dev=true**), login and navigate to app where plugin is docked(through docking-host-config)
    3. Verify the plugin and recent changes made in plugin logic
    4. If app is already loaded, just refresh the page to verify recent plugin logic changes5
    5. Ensure query string dev=true is present all the time
5. Git update:
    1. Once changes are verified, keep pushing changes to plugin git repo
6. Production deployment:
    1. Once plugin is ready with all testing done, submit the plugin to Riversand App Management team following process at : provide guide link here (R2)
