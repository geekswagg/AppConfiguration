# Azure App Configuration JavaScript Provider

[Source code][source_code] | [Package (npm)][package] | [Samples][samples]

## 1.0.0-preview.2 - December 15, 2023
### Breaking Changes
- The label filter in a selector is restricted to a single label. An error will be thrown if a label filter contains `*` or `,`. This change is to avoid the ambiguity when multiple values are loaded for the same key. Key-values with different labels can still be loaded using separate selectors for proper configuration composition. [#22](https://github.com/Azure/AppConfiguration-JavaScriptProvider/pull/22)
- Fixed a bug where the last selector may not take precedence if multiple selectors with the same key and label filters are provided. After applying the fix, the resulting configuration of an application may change. To ensure the intended configuration composition, remove any duplicated selectors.[#23](https://github.com/Azure/AppConfiguration-JavaScriptProvider/issues/23)

### Bug Fixes
- Updated the reference of `@azure/core-rest-pipeline` to `1.12.2`, which added retry for DNS resolution of App Configuration endpoints. [Azure/azure-sdk-for-js#27037](https://github.com/Azure/azure-sdk-for-js/issues/27037)

## 1.0.0-preview.1 - October 24, 2023
### Bug fixes
- Updated the reference of `@azure/identity` to `3.3.2`, addressing [CVE-2023-36415](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2023-36415)

## 1.0.0-preview - October 11, 2023
Added support for
- authentication with connection string or Microsoft Entra
- loading and composing configuration with key-value selectors
- key prefix trimming
- Key Vault reference resolution
- Key-value with JSON content-type

[package]: https://www.npmjs.com/package/@azure/app-configuration-provider
[samples]: https://github.com/Azure/AppConfiguration-JavaScriptProvider/tree/main/examples
[source_code]: https://github.com/Azure/AppConfiguration-JavaScriptProvider
