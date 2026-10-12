# Kameleoon Google Tag Manager Template

A tag template for Google Tag Manager web containers that loads the Kameleoon
engine to run experiments and personalizations on your website.

The template loads the following script asynchronously:

```text
https://<siteCode>.<domain>/engine.js
```

## Installation

### From the Community Template Gallery

Once this template is published in the gallery:

1. Open your Google Tag Manager web container.
2. Go to **Templates > Tag Templates > Search Gallery**.
3. Find **Kameleoon - Main tag** and add it to your workspace.
4. Create a tag using the template and configure it as described below.

### Import from this repository

1. Download [template.tpl](template.tpl).
2. In your Google Tag Manager web container, go to **Templates > Tag Templates > New**.
3. Open the Template Editor menu, select **Import**, and choose `template.tpl`.
4. Review the template permissions and save the template.
5. Create a tag using **Kameleoon - Main tag**.

## Configuration

| Field | Required | Value |
| --- | --- | --- |
| Enter sitecode | Yes | Your Kameleoon project site code. Find it in the Kameleoon app under **Admin > Projects**. Enter only the code, without a URL or domain. |
| Select domain | Yes | `kameleoon.io` or `kameleoon.eu`, matching your project's Kameleoon installation URL. |

For example, site code `test123` and domain `kameleoon.io` load
`https://test123.kameleoon.io/engine.js`.

Choose a trigger that loads Kameleoon on the intended pages at the appropriate
time for your installation. Before publishing the container, use GTM Preview to
verify that the tag succeeds and that the browser loads the expected `engine.js`
URL. Avoid installing the same engine through both this tag and an existing
installation snippet.

This template loads the engine only. Configure any required anti-flicker code,
cross-domain setup, and consent behavior separately according to your Kameleoon
installation requirements. See the [Kameleoon documentation](https://docs.kameleoon.com).

## Permissions and behavior

- **Inject scripts:** allows script loading from `https://*.kameleoon.io/*` and
  `https://*.kameleoon.eu/*`.
- **Logging:** allows diagnostic messages in GTM debug mode.

The tag reports success when the script loads. Missing configuration, denied
script injection permission, or a script loading error causes the tag to report
failure. The script URL is also used as the `injectScript` cache token, allowing
GTM to reuse a load for the same URL.

## Testing

Import `template.tpl` into the GTM Template Editor and run the tests in the
**Tests** tab. The exported template includes five scenarios: successful loading,
the EU domain, a loading error, denied permissions, and a missing site code.

Also use GTM Preview with a real project to check the network request and
Kameleoon behavior on your website before publishing.

## Publishing to the Community Template Gallery

Follow Google's [submission requirements](https://developers.google.com/tag-platform/tag-manager/templates/gallery)
and [template style guide](https://developers.google.com/tag-platform/tag-manager/templates/style).

Before the first submission:

- Keep `template.tpl`, `metadata.yaml`, and `LICENSE` at the repository root on
  the `main` branch. Keep only one `template.tpl` in the repository.
- Run the Template Editor tests and verify the tag in GTM Preview.
- In the Template Editor's **Info** tab, confirm agreement to the Community
  Template Gallery Terms of Service.
- Verify the homepage and documentation links in `metadata.yaml` and ensure its
  release SHA references the intended committed `template.tpl`.
- Push the files to [this GitHub repository](https://github.com/Kameleoon-new/gtm-engine-script)
  and make sure the repository is public.
- Enable GitHub Issues and email notifications for review feedback and bug reports.
- Sign in with a GitHub account that has access to this repository, open the
  [Community Template Gallery](https://tagmanager.google.com/gallery/), select
  **Submit Template** from the menu, and submit the repository URL.

For subsequent releases, commit the updated `template.tpl` first. Add that
commit's full SHA and release notes at the top of `versions` in `metadata.yaml`,
then commit and push the metadata update. Keep previous published versions in
the list, newest first. Documentation-only changes do not require a new template
version. Gallery versions are tracked through `metadata.yaml`; a GitHub release
or tag is not required by the submission process.

## Support

Report template bugs through [GitHub Issues](https://github.com/Kameleoon-new/gtm-engine-script/issues).
Include the selected domain, reproduction steps, and relevant GTM Preview
messages. For Kameleoon product documentation, visit
[docs.kameleoon.com](https://docs.kameleoon.com).

## License

Copyright 2026 Kameleoon. Licensed under [Apache License 2.0](LICENSE).
