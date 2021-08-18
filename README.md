# maui-workload-pinning

This is an example of installing .NET MAUI Preview 7 and using RC1 packs.

CI does:

```dotnetcli
dotnet workload update --from-rollback-file workload.json --verbosity diag
dotnet workload install maui --skip-manifest-update --verbosity diag
```

Which should install .NET Maui for Preview 7.

Next, we can add the MSBuild properties:

```xml
<MicrosoftMauiSdkVersion>6.0.100-rc.1.1351</MicrosoftMauiSdkVersion>
<RestoreAdditionalProjectSources>https://aka.ms/maui-preview/index.json</RestoreAdditionalProjectSources>
```

Since RC1 is not released yet, we need to add another feed here.
